## Summary Statistics
##### Preparation Code
```r
# Functions
library(dplyr)
library(knitr)
library(psych)

# Sample Data
library(vcd)
A <- Arthritis
```
##### Actual Code
###### \[`describe`\] Sample Task 1.1
>Compute median, skew and interquartile range.
```r
# Obtain "n", "mean", "sd", "median", "trimmed", "mad", "min", "max", "skew", "kurtosis", "se", "IQR"
describe(A$Age, IQR = TRUE) %>%
  mutate(vars = "Age") %>%
  select(c(vars, median, skew, IQR)) %>% # (a) Filter by inclusion
  #select(-c(n, mean, sd, trimmed, mad, min, max, kurtosis, se)) %>% # (b) Filter by deletion
  mutate(across(where(is.double), round, 2)) %>% # Round numbers to 2d.p.
  kable(row.names = FALSE, caption = "Descriptive Statistics for Age")
```
###### \[`summary`\] Sample Task 2.1
>Compute the first quartile (Q1) and the third quartile (Q3).
```r
# Obtain "1st Qu.", "3rd Qu."
summary(A$Age)[c("1st Qu.", "3rd Qu.")] %>%
  as.array() %>% t() %>%
  kable(caption = "Additional Descriptive Statistics for Age",
    col.names = c("First Quartile (Q1)", "Third Quartile (Q3)"))
```
###### \[`describeBy`\] Sample Task 3.1
>Compute the mean and median age, grouped by degree of improvement.
```r
age.summary <- A$Age %>% describeBy(group = A$Improved, IQR = TRUE,
                                    mat = TRUE) # Output as matrix

age.summary <- age.summary[,c("group1", "mean","median")] # (a) Filter by inclusion
#age.summary <- age.summary[,-c(1, 3, 4, 6, 8:16)] # (b) Filter by deletion

kable(age.summary, caption = "Descriptive Statistics for Age")
```
###### \[`describeBy`\] Sample Task 3.2
>Compute the mean and median age, grouped primarily by mode of treatment and secondarily by gender.
```r
age.summary <- describeBy(Age ~ Treatment + Sex, data = A, IQR = TRUE,
                                    mat = TRUE) # Output as matrix
age.summary <- age.summary[,c("group1", "min","max")] # (a) Filter by inclusion
#age.summary <- age.summary[,-c(1, 4:10, 13:17)] # (b) Filter by deletion

kable(age.summary, caption = "Descriptive Statistics for Age")
```
###### \[`summarise`\] Sample Task 4.1
>Compute count, skew and kurtosis.
```r
A %>% summarise(
        vars = "Age",
        n = n(),
        skew = skew(Age),
        kurtosis = kurtosi(Age))
```
###### \[`summarise`\] Sample Task 4.2
>Compute the mean and median age, grouped by degree of improvement.
```r
A %>% group_by(Improved) %>%summarise(
        vars = "Age",
        n = n(),
        mean = mean(Age),
        median = median(Age))
```
###### \[`summarise`\] Sample Task 4.3
>Compute the mean and median age, grouped primarily by mode of treatment and secondarily by gender.
```r
A %>% group_by(Improved, Sex) %>%summarise(
        vars = "Age",
        n = n(),
        mean = mean(Age),
        median = median(Age))
```
