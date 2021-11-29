### Grouped Barplot
Preparation Code
```
# Functions
library(dplyr)
# Data for Sample Inputs
library(wooldridge)
data(mathpnl)
sample_df <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
sample_df$Year <- ifelse(sample_df$y92 == 1, "1992", ifelse(sample_df$y93 == 1, "1993",
                        ifelse(sample_df$y94 == 1, "1994", ifelse(sample_df$y95 == 1, "1995", NA))))
sample_df <- sample_df %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>% summarise(Satisfaction.Grade_4 = mean(math4, na.rm=TRUE), Satisfaction.Grade_7 = mean(math7, na.rm=TRUE))
```
Actual Code
```
grouped_barplot.matrix <- sample_df %>%
  select(c(Satisfaction.Grade_4, Satisfaction.Grade_7)) %>% as.matrix() %>% t()

grouped_barplot <- barplot(grouped_barplot.matrix,
        beside = TRUE,
        ylim = c(0, 70),
        names.arg = c("1992", "1993", "1994", "1995"),
        main = glue::glue("Bar Plot of Mean Satisfaction for Math, By Year of Graduation"),
        ylab = glue::glue("Mean Satisfaction for Math"),
        cex.main = 1,
        cex.names = 0.9,
        col = c("plum2", "lightgoldenrod1"))

legend("topleft",
       fill = c("plum2", "lightgoldenrod1"),
       c("Satisfaction.Grade_4", "Satisfaction.Grade_7"),
       cex = 0.9)

text(y = grouped_barplot.matrix, x = grouped_barplot,
     label = round(grouped_barplot.matrix,2), pos = 3, cex = 0.9)
```
Additional Notes:
1. Structure of `sample_df`

| Discrete Variable* | Continuous Variable 1* | Continuous Variable 2* | ... | 
| :---: | :---: | :---: | :---: |
| ... | ... | ... | ... |
\*Variable Name as Column Name
