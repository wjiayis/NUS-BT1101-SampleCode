### Confidence Interval (Unknown Population sd)
**Actual Code**
1. Helper function. (Must be included. Do not edit.)
```
compute.ConfidenceInterval <- function(dataset_variable, confidence_interval.decimal){
m <- mean(variable)
sd <- sd(variable)

lCI <- mean(dataset_variable) + qt(((1 - confidence_interval.decimal)/2), df=length(dataset_variable)-1)*sd(dataset_variable)/sqrt(length(dataset_variable))

uCI <- mean(dataset_variable) - qt(((1 - confidence_interval.decimal)/2), df=length(dataset_variable)-1)*sd(dataset_variable)/sqrt(length(dataset_variable))

cbind(lCI, uCI)}
```
2. **Inputs**. (Must be included. Edit this.)
```
compute.ConfidenceInterval(mtcars$mpg, # variable
  0.95) # percentage_confidence_decimal
```
