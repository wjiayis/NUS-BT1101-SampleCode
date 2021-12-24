## \[Frequency\] Histogram & Frequency Table
### Base R Graphic
###### Preparation Code
```r
# Functions
library(knitr)

# Sample Data
library(dplyr)
library(wooldridge)
CS <- ceosal1 %>% filter(salary < 1000)
```
###### Actual Code
```r
# Graph
histogram <- hist(CS$salary,
     ylim = c(0,28), # Range of y-values
     main = "Histogram of Frequency of CEOs' Salary", # Title
     xlab = "Salary",
     ylab = "Number of CEOs",
     label = TRUE, # Value labels
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
###### Actual Code
```r
ggplot(CS, aes(x = salary)) +
      geom_histogram(fill = "pink", color = "black") +
      labs(title = "Histogram of Frequency of CEOs' Salary")
```
