### Summary Statistics
Preparation Code
```
# Functions
library(dplyr)
library(knitr)
library(psych)

# Sample Data
library(vcd)
A <- Arthritis
```
#### **_Sample Task: Compute median, skew and interquartile range._**
**Actual Code**
```
# Obtain "n", "mean", "sd", "median", "trimmed", "mad", "min", "max", "skew", "kurtosis", "se", "IQR"
describe(A$Age, IQR=TRUE) %>%
  mutate(vars="Age") %>%
  select(c(vars, median, skew, IQR)) %>% # (a) Filter by inclusion
  #select(-c(n, mean, sd, trimmed, mad, min, max, kurtosis, se)) %>% # (b) Filter by deletion
  mutate(across(where(is.double), round, 2)) %>% # Round numbers to 2d.p.
  kable(row.names = FALSE, caption = "Descriptive Statistics for Age")
```
#### **_Sample Task: Compute the first quartile (Q1) and the third quartile (Q3)._**
**Actual Code**
```
# Obtain "1st Qu.", "3rd Qu."
summary(A$Age)[c("1st Qu.", "3rd Qu.")] %>%
  as.array() %>% t() %>%
  kable(caption = "Additional Descriptive Statistics for Age",
    col.names = c("First Quartile (Q1)", "Third Quartile (Q3)"))
```
#### **_Sample Task: Compute summary statistics for each mode of treatment._** (HOW TO SECTION IT LIKE THE ABOVE SAMPLE TASKS)
**Actual Code**
```
A$Age %>% describeBy(group = A$Treatment, IQR = TRUE)
```
#### **_Sample Task: Compute summary statistics for each gender, for each mode of treatment._** (CHECK WORDING)
**Actual Code**
```
describeBy(Age ~ Treatment + Sex, data = A, IQR = TRUE)
```
