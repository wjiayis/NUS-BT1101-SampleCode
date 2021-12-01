### Histogram [(HF Available)](../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Histogram-&-Frequency-Table.md) LINK DOESNT WORK
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
data(ceosal1)
CS <- ceosal1
CS <- CS %>% filter(salary < 1000)
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
