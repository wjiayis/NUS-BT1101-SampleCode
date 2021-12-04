### Grouped Barplot</br></br>
Preparation Code
```
# Functions
library(dplyr)
library(ggplot2) # For ggplot2 graphic

# Sample Data (common)
library(wooldridge)
M <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                        ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>% summarise(Satisfaction.Grade_4 = mean(math4, na.rm=TRUE), Satisfaction.Grade_7 = mean(math7, na.rm=TRUE))

# Sample Data (for base R graphic)
satisfaction.base.matrix <- M %>%
  select(c(Satisfaction.Grade_4, Satisfaction.Grade_7)) %>% as.matrix() %>% t()
```
</br>**Actual Code**
##### Base R Graphics
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Grouped-Barplot-&-Frequency-Table.md)
```
satisfaction.grouped_barplot <- barplot(satisfaction.base.df, # dataset_variable
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

text(y = satisfaction.base.df, x = satisfaction.grouped_barplot,
     label = round(satisfaction.base.df, 2), pos = 3, cex = 0.9) # Value labels
```
##### ggplot2 Graphics

</br>Additional Notes:
1. Structure of matrix `satisfaction.base.matrix`

| | (Continuous Variable 1) | (Continuous Variable 2) | ... | 
| :---: | :---: | :---: | :---: |
| Discrete Variable[^1]  | ... | ... | ... |

2. Structuer of 
[^1]: Variable name as column name
