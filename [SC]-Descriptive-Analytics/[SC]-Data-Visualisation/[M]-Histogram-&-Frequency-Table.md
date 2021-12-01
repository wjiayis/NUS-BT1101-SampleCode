### Histogram
:white_heart: [_Helper Function Available_](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Histogram-&-Frequency-Table.md)

Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
CS <- ceosal1 %>% filter(salary < 1000)
```
**Actual Code**
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
