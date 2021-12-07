## Histogram & Frequency Table
### Base R Graphic
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Histogram-&-Frequency-Table.md)
###### Preparation Code
```r
# Functions
library(knitr)

# Sample Data
library(dplyr)
library(wooldridge)
CS <- ceosal1 %>% filter(salary < 1000)
```
##### Histogram of Count
###### Actual Code
```r
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
### ggplot2 Graphic
###### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(dplyr)
library(wooldridge)
CS <- ceosal1 %>% filter(salary < 1000)
```
##### Histogram of Count
###### Actual Code
```r
ggplot(CS, aes(x=salary)) +
  geom_histogram(fill="pink", color = "black") +
  labs(title="Histogram of Frequency of CEOs' Salary")
```
