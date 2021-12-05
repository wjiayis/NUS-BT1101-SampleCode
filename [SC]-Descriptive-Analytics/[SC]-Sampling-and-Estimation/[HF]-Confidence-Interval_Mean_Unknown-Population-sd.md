## \[HF\] Confidence Interval for Mean
##### Actual Code
1. Helper function. (Must be included. Do not edit.)
```
calculate.ConfidenceInterval <- function(dataset_variable, confidence_level.decimal){
m <- mean(dataset_variable)
sd <- sd(dataset_variable)

lCI <- mean(dataset_variable) + qt(((1 - confidence_level.decimal)/2), df=length(dataset_variable)-1)*sd(dataset_variable)/sqrt(length(dataset_variable))

uCI <- mean(dataset_variable) - qt(((1 - confidence_level.decimal)/2), df=length(dataset_variable)-1)*sd(dataset_variable)/sqrt(length(dataset_variable))

cbind(lCI, uCI)}
```
2. Inputs. (Must be included. Edit this.)
```
calculate.ConfidenceInterval(mtcars$mpg, # dataset_variable
  0.95) # confidence_level.decimal
```
