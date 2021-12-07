## Confidence Interval for Mean
### For known population standard deviation
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Confidence-Interval_Mean_Known-Population-sd.md)
##### Actual Code
###### Sample Task
>The distribution for volume is normal with sample mean = 796 and population standard deviation = 15.</br>Compute the 95% confidence interval for the mean volume for population.
```r
margin_of_error <- qnorm(0.975)*15/sqrt(25)
lCI <- 796 - margin_of_error
uCI <- 796 + margin_of_error
cbind(lCI, uCI)
```
### For unknown population standard deviation
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Confidence-Interval_Mean_Unknown-Population-sd.md)
###### Sample Task
>Compute the 95% confidence interval for `mtcars$mpg`.
##### Manual Method
###### Actual Code
```r
mpg.n <- nrow(mtcars)
mpg.mean <- mean(mtcars$mpg)
mpg.sd <- sd(mtcars$mpg)
mpg.se <- mpg.sd/sqrt(mpg.n)

mpg.margin_of_error <- qt(0.975, df = (mpg.n-1))*mpg.se
mpg.lCI <- mpg.mean - mpg.margin_of_error
mpg.uCI <- mpg.mean + mpg.margin_of_error
cbind(mpg.lCI, mpg.uCI)
```
##### Rmisc Method
###### Preparation Code
```r
library(Rmisc)
```
###### Actual Code
```r
mpg.ci <- CI(mtcars$mpg, ci = 0.95)
mpg.ci <- cbind(mpg.ci[3],mpg.ci[1])
colnames(mpg.ci) <- c("lCI", "uCI")
rownames(mpg.ci) <- NULL
print(mpg.ci, digits = 4)
```
