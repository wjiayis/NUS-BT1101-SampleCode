## Grouped Barplot
</br>Preparation Code
```
# Functions
library(dplyr)
library(tidyr) # For ggplot2 graphic
library(ggplot2) # For ggplot2 graphic

# Sample Data
library(wooldridge)
M <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                   ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>% summarise(`Grade 4` = mean(math4, na.rm=TRUE), `Grade 7` = mean(math7, na.rm=TRUE))

M <- M %>%
  select(c(`Grade 4`, `Grade 7`)) %>% as.data.frame()
Year <- c("1992", "1993", "1994", "1995")
M <- cbind(Year, M)
M <- M %>% gather("Grade", "Mean Satisfaction for Math", -Year)
```
</br>**Actual Code**
##### Base R Graphics
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Grouped-Barplot-&-Frequency-Table.md)
```
M.base <- M %>% spread(Year, `Mean Satisfaction for Math`)

satisfaction.grouped_barplot <- barplot(M.base, # dataset_variable
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

text(y = M.base, x = satisfaction.grouped_barplot,
     label = round(M.base, 2), pos = 3, cex = 0.9) # Value labels
```
##### ggplot2 Graphics
```
ggplot(data=M, aes(x=Year, y=`Mean Satisfaction for Math`, fill=Grade)) + # dataset_variable
geom_bar(stat="identity", position=position_dodge()) +
labs(title = "Bar Plot of Mean Satisfaction for Math, By Year of Graduation") + # Title
geom_text(aes(label= round(`Mean Satisfaction for Math`, 2)), vjust=1.6, color="black", position = position_dodge(0.9), size=3.5) + # Value labels
scale_fill_manual(values=c("pink", "lightblue"))# Colours
```
</br>Additional Notes:
1. Structure of data frame `M`

| Bar Groups Discrete Variable[^1] | Legend Discrete Variable[^1] | Continuous Variable[^1] |
| :---: | :---: | :---: |
| ... | ... | ... |

[^1]: Variable name as column name
