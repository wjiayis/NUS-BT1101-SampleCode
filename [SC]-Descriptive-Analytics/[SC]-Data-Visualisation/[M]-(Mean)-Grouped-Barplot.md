## \[Mean\] Grouped Barplot
### Base R Graphic
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Grouped-Barplot-&-Frequency-Table.md)
###### Preparation Code
```r
# Functions
library(dplyr)
library(tidyr)

# Sample Data
library(wooldridge)
M <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                   ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>% summarise(`Grade 4` = mean(math4, na.rm=TRUE), `Grade 7` = mean(math7, na.rm=TRUE))

M.m <- M %>% select(c(`Grade 4`, `Grade 7`)) %>% as.matrix() %>% t()
```
###### Actual Code
```r
satisfaction.grouped_barplot <- barplot(M.m, # dataset_variable
        beside = TRUE,
        ylim = c(0, 70), # Range of y-values
        main = "Bar Plot of Mean Satisfaction for Math, By Year of Graduation", # Title
        cex.main = 1, # [Font size] Title
        ylab = "Mean Satisfaction for Math", # y-axis label
        names.arg = c("1992", "1993", "1994", "1995"), # x-axis labels
        cex.names = 0.9, # [Font size] x-axis labels
        col = c("plum2", "lightgoldenrod1")) # Colours

legend("topleft",
       fill = c("plum2", "lightgoldenrod1"),
       c("Grade 4", "Grade 7"),
       cex = 0.9) # [Font size] Legend

# Value labels
text(y = M.m, x = satisfaction.grouped_barplot,
     label = round(M.m, 2), pos = 3, cex = 0.9)
```
### ggplot2 Graphic
###### Preparation Code
```r
# Functions
library(dplyr)
library(tidyr)
library(ggplot2)

# Sample Data
library(wooldridge)
M <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                   ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>%
       summarise(grade4_mean = mean(math4, na.rm=TRUE), grade7_mean = mean(math7, na.rm=TRUE),
                 grade4_sd = sd(math4, na.rm=TRUE), grade7_sd = sd(math7, na.rm=TRUE))

  # Matrix for mean
M.mean <- M %>% select(c(grade4_mean, grade7_mean)) %>% as.data.frame()
Year <- c("1992", "1993", "1994", "1995")
M.mean <- cbind(Year, M.mean)
M.mean <- M.mean %>% gather("Grade", "Mean", -Year)

  # Matrix for sd
M.sd <- M %>% select(c(grade4_sd, grade7_sd)) %>% as.data.frame()
M.sd <- cbind(Year, M.sd)
M.sd <- M.sd %>% gather("Grade", "sd", -Year)

M <- M.mean %>% mutate(sd = M.sd$sd)
```
###### Actual Code
```r
ggplot(data = M, aes(x = Year, y = Mean, fill = Grade)) + # dataset_variable
  geom_bar(stat = "identity", position = position_dodge()) +
    geom_errorbar(aes(ymin = Mean - sd, ymax = Mean + sd), width = 0.2, col = "grey55", position=position_dodge(0.9)) + # Error bars
  labs(title = "Bar Plot of Mean Satisfaction for Math, By Year of Graduation") + # Title
  geom_text(aes(label = round(Mean, 2)), vjust = 1.6, color = "black", position = position_dodge(0.9), size = 3.5) + # Value labels
  scale_fill_manual(values = c("pink", "lightblue")) # Colours
```
