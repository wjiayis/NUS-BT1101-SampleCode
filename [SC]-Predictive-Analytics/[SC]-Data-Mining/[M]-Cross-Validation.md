## Cross Validation
##### Sample Task 1
>Split data randomly into train, valid and test (60:20:20).
###### Preparation Code
```
# Functions
library(dplyr)
```
###### Actual Code
```
set.seed(1) # For reproducibility
mtcars$partitionNum <- sample(1:3, size=nrow(mtcars),
                          prob=c(0.6,0.2,0.2), replace=T)
mtcars$partition <- factor(mtcars$partitionNum, levels=c(1,2,3),
                       labels=c("Train", "Valid", "Test"))
mtcars_train <- mtcars %>% filter(partition=="Train")
mtcars_valid <- mtcars %>% filter(partition=="Valid")
mtcars_test <- mtcars %>% filter(partition=="Test")
```
