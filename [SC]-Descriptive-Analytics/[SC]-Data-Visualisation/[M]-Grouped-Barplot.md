### Grouped Barplot
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
data(mathpnl)
M <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                        ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>% summarise(Satisfaction.Grade_4 = mean(math4, na.rm=TRUE), Satisfaction.Grade_7 = mean(math7, na.rm=TRUE))
```
**Actual Code**
```
satisfaction.grouped_barplot.matrix <- M %>%
  select(c(Satisfaction.Grade_4, Satisfaction.Grade_7)) %>% as.matrix() %>% t()

satisfaction.grouped_barplot <- barplot(satisfaction.grouped_barplot.matrix,
        beside = TRUE,
        ylim = c(0, 70),
        main = "Bar Plot of Mean Satisfaction for Math, By Year of Graduation",
        ylab = "Mean Satisfaction for Math",
        names.arg = c("1992", "1993", "1994", "1995"),
        cex.main = 1,
        cex.names = 0.9,
        col = c("plum2", "lightgoldenrod1"))

legend("topleft",
       fill = c("plum2", "lightgoldenrod1"),
       c("Satisfaction.Grade_4", "Satisfaction.Grade_7"),
       cex = 0.9)

text(y = satisfaction.grouped_barplot.matrix, x = satisfaction.grouped_barplot,
     label = round(satisfaction.grouped_barplot.matrix, 2), pos = 3, cex = 0.9)
```
Additional Notes:
1. Structure of data frame `M`

| Discrete Variable* | Continuous Variable 1* | Continuous Variable 2* | ... | 
| :---: | :---: | :---: | :---: |
| ... | ... | ... | ... |

\*Variable Name as Column Name
