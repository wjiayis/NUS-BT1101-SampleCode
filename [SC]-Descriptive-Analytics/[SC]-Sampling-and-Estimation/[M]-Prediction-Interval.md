## Prediction Interval
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Prediction-Interval.md)

##### Sample Task 1
>\[Normally Distributed Data\] Compute the 99% prediction interval.
###### Actual Code
```r
mpg.m <- mean(mtcars$mpg)
mpg.sd <- sd(mtcars$mpg)

lPI <- mpg.m - (qt(((1-(1 - 0.99)/2)),
                             df = (nrow(mtcars)-1))*mpg.sd*sqrt(1+1/nrow(mtcars)))
uPI <- mpg.m + (qt(((1-(1 - 0.99)/2)),
                             df = (nrow(mtcars)-1))*mpg.sd*sqrt(1+1/nrow(mtcars)))
cbind(lPI, uPI)
```
</br></br></br>
##### Sample Task 2
>\[lambda > 0\] Compute the 95% prediction interval.
###### Preparation Code
```r
# Functions
library(rcompanion)
```
###### Actual Code
```r
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
</br></br></br>
##### Sample Task 3
>\[lambda < 0\] Compute the 90% prediction interval.
###### Preparation Code
```r
# Functions
library(rcompanion)

# Samples Data
library(wooldridge)
R <- rdchem
```
###### Actual Code
```r
lambda <- transformTukey(R$rd, quiet = TRUE, plotit = FALSE, returnLambda = TRUE)
lambda
R$rd.t <- transformTukey(R$rd)

rd.m.t <- mean(R$rd.t)
rd.sd.t <- sd(R$rd.t)

lPI.t <- rd.m.t - (qt(((1-(1 - 0.90)/2)),
                             df = (nrow(R)-1))*rd.sd.t*sqrt(1+1/nrow(R)))
uPI.t <- rd.m.t + (qt(((1-(1 - 0.90)/2)),
                             df = (nrow(R)-1))*rd.sd.t*sqrt(1+1/nrow(R)))
cbind(lPI.t, uPI.t)

lPI <- lPI.t^(1/-0.05)
uPI <- uPI.t^(1/-0.05)

cbind(lPI, uPI)
```
</br></br></br>
##### Sample Task 4
>\[lambda = 0\] Compute the 90% prediction interval.
###### Preparation Code
```r
# Functions
library(rcompanion)

# Samples Data
library(wooldridge)
R <- rdchem
```
###### Actual Code
```r
lambda <- transformTukey(R$salessq, quiet = TRUE, plotit = FALSE, returnLambda = TRUE)
lambda
R$salessq.t <- transformTukey(R$salessq)

salessq.m.t <- mean(R$salessq.t)
salessq.sd.t <- sd(R$salessq.t)

lPI.t <- salessq.m.t - (qt(((1-(1 - 0.90)/2)),
                             df = (nrow(R)-1))*salessq.sd.t*sqrt(1+1/nrow(R)))
uPI.t <- salessq.m.t + (qt(((1-(1 - 0.90)/2)),
                             df = (nrow(R)-1))*salessq.sd.t*sqrt(1+1/nrow(R)))
cbind(lPI.t, uPI.t)

lPI <- exp(1)^lPI.t
uPI <- exp(1)^uPI.t

cbind(lPI, uPI)
```
