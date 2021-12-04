## [Base R] Histogram
:white_heart: [Helper Function Available](../../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[SC]-Base-R-Graphic/[HF]-Histogram-&-Frequency-Table_Base-R.md)

###### Preparation Code
```
# Sample Data
library(dplyr)
library(wooldridge)
CS <- ceosal1 %>% filter(salary < 1000)
```
###### Actual Code
```
# Graph
histogram <- hist(CS$salary,
     ylim = c(0,28),
     main = "Histogram of Frequency of CEOs' Salary",
     xlab = "Salary",
     ylab = "Number of CEOs",
     label = TRUE,
     col = "pink")

# Frequency Table
Salary.Group <- cut(CS$salary, histogram$breaks, include.lowest = TRUE, right = TRUE)
salary.table <- table(Salary.Group)
kable(salary.table, caption = "Frequency Distribution by Salary Group")
```
