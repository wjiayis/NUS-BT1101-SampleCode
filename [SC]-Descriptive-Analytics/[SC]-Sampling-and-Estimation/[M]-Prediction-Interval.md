## Prediction Interval
:white_heart:[Helper_Function_Available]([SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Prediction-Interval_Proportion.md)
### Prediction Interval
#### **_Sample Task: [Normally Distributed Data] Compute the 99% prediction interval._**
**Actual Code**
```
mpg.m <- mean(mtcars$mpg)
mpg.sd <- sd(mtcars$mpg)

lPI <- mpg.m - (qt(((1-(1 - 0.99)/2)),
                             df = (nrow(mtcars)-1))*mpg.sd*sqrt(1+1/nrow(mtcars)))
uPI <- mpg.m + (qt(((1-(1 - 0.99)/2)),
                             df = (nrow(mtcars)-1))*mpg.sd*sqrt(1+1/nrow(mtcars)))
cbind(lPI, uPI)
```
#### **_Sample Task: [lambda > 0] Compute the 95% prediction interval._**
Preparation Code
```
library(rcompanion)
```
**Actual Code**
```
lambda <- transformTukey(mtcars$cyl, quiet = TRUE, plotit = FALSE, returnLambda = TRUE)
lambda
mtcars$cyl.t <- transformTukey(mtcars$cyl)

cyl.m.t <- mean(mtcars$cyl.t)
cyl.sd.t <- sd(mtcars$cyl.t)

lPI.t <- cyl.m.t - (qt(((1-(1 - 0.95)/2)),
                             df = (nrow(mtcars)-1))*cyl.sd.t*sqrt(1+1/nrow(mtcars)))
uPI.t <- cyl.m.t + (qt(((1-(1 - 0.95)/2)),
                             df = (nrow(mtcars)-1))*cyl.sd.t*sqrt(1+1/nrow(mtcars)))
cbind(lPI.t, uPI.t)

lPI <- lPI.t^(1/1.1)
uPI <- uPI.t^(1/1.1)

cbind(lPI, uPI)
```
## LAMBDA == 0 AND LAMBDA < 0 UNDONE
