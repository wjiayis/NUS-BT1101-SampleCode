## Prediction Interval
:white_heart:[_Helper_Function_Available]
### For normally distributed data (5% level of significance)
**Actual Code**
```
m <- mean(mtcars$mpg)
sd <- sd(mtcars$mpg)

lPI <<- m - (qt(((1-(1 - 0.95)/2)),
                             df = (nrow(mtcars)-1))*sd*sqrt(1+1/nrow(mtcars)))
uPI <<- m + (qt(((1-(1 - 0.95)/2)),
                             df = (nrow(mtcars)-1))*sd*sqrt(1+1/nrow(mtcars)))
cbind(lPI, uPI)
```
