## Median
##### Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(vcd)
A <- Arthritis
```
##### Actual Code
###### Sample Task 1
>Compute median age.
```
median(A$Age)
```
###### Sample Task 2
>Compute median age for each gender.
```
A %>% group_by(Sex) %>% summarise(Median = median(Age))
```
###### Sample Task 3
>Compute median age, grouping primarily by mode of treatment, and secondarily by gender.
```
A %>% group_by(Treatment, Sex) %>% summarise(Median = median(Age))
```
