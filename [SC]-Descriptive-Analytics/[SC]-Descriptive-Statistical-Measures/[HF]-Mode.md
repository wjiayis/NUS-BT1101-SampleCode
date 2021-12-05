## [HF] Mode
##### Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(vcd)
A <- Arthritis
```
##### Actual Code
1. Helper Function. (Must be included. Do not edit.)
```
calculate.Mode <- function(x){which.max(tabulate(x))}
```
2. Inputs. (Must be included. Edit this.)
###### Sample Task 1
>Compute mode age.
```
calculate.Mode(A$Age)
```
###### Sample Task 2
>Compute mode age for each gender.
```
A %>% group_by(Sex) %>% summarise(Mode = calculate.Mode(Age))
```
###### Sample Task 3
>Compute mode age, grouping primarily by mode of treatment, and secondarily by gender.
```
A %>% group_by(Treatment, Sex) %>% summarise(Mode = calculate.Mode(Age))
```
