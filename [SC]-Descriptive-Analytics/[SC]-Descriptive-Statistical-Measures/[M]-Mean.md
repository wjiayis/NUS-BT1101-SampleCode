## Mean
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
>Compute mean age.
```
mean(A$Age)
```
###### Sample Task 2
>Compute mean age for each gender.
```
A %>% group_by(Sex) %>% summarise(Mean = mean(Age))
```
###### Sample Task 3
>Compute mean age, grouping primarily by mode of treatment, and secondarily by gender.
```
A %>% group_by(Treatment, Sex) %>% summarise(Mean = mean(Age))
```
###### Sample Task 4
>Excluding the most extreme 10% of age data (5% on the lower tail and 5% on the upper tail), compute mean age.
```
mean(A$Age, trim=0.05)
```
