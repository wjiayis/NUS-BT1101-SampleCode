## \[Mean\] Horizontal Barplot
### Base R Graphic
###### Preparation Code
```r
# Functions
library(dplyr)
library(tidyr)
library(ggplot2)

# Sample Data
library(wooldridge)
M <- mathpnl %>% select(c(math4, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                   ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, Year) %>% group_by(Year) %>%
     summarise(Mean = mean(math4, na.rm=TRUE), sd = sd(math4, na.rm=TRUE))
```
###### Actual Code
```r
satisfaction.barplot <- barplot(M$Mean, # dataset_variable
        horiz = TRUE,
        xlim = c(0,80), # Range of x-values
        main = "Barplot of Mean Satisfaction", # Title
        cex.main = 1.1, # [Font size] Title
        xlab = "Mean Satisfaction", # x-axis label
        ylab = "Year", # y-axis label
        names.arg = c("1992","1993","1994","1995"), # y-axis labels
        las = 1, # [Orientation] y-axis labels
        cex.names = 0.9, # [Font size] y-axis labels
        col="pink") # Colour

# Error bars
arrows(y0 = satisfaction.barplot, x0 = M$Mean-M$sd,
       y1 = satisfaction.barplot, x1 = M$Mean+M$sd,
       code = 3, angle = 90, length = 0.1, col = "grey55")

# Value labels
text(x = M$Mean, y = satisfaction.barplot, label = round(M$Mean,3), pos = 4, cex = 1)
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
M <- mathpnl %>% select(c(math4, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                   ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, Year) %>% group_by(Year) %>%
     summarise(Mean = mean(math4, na.rm=TRUE), sd = sd(math4, na.rm=TRUE))
```
###### Actual Code
```r
ggplot(data = M, aes(y = Year, x = Mean)) + # dataset_variable
  geom_bar(stat = "identity",
           fill = "pink") + # Colour
  geom_errorbarh(aes(xmin = Mean - sd, xmax = Mean + sd), height = 0.2, col = "grey55") + # Error bars
  labs(title = "Bar Plot of Mean Satisfaction") + # Title
  #geom_text(aes(label = round(Mean,2)), hjust = -0.3, color = "black", size = 3.5) # 'Outside-bars' value labels
  geom_text(aes(label = round(Mean,2)), hjust = 1.6, color = "black", size = 3.5) # 'Within-bars' value labels
```
