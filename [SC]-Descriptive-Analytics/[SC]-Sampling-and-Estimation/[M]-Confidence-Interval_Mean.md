## [ND] Confidence Interval for Mean
### For known population standard deviation
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Confidence-Interval_Mean_Known-Population-sd.md)
##### Actual Code
###### Sample Task
>The distribution for volume is normal with sample mean = 796 and population standard deviation = 15.</br>Compute the 95% confidence interval for the mean volume for population.
```
precision <- qnorm(0.975)*15/sqrt(25)
lCI <- 796-precision
uCI <- 796+precision
cbind(lCI, uCI)
```
### For unknown population standard deviation
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Confidence-Interval_Mean_Unknown-Population-sd.md)
##### Preparation Code
```
library(Rmisc)
```
##### Actual Code
```
mpg.ci <- CI(mtcars$mpg, ci = 0.95)
mpg.ci <- cbind(mpg.ci[3],mpg.ci[1])
colnames(mpg.ci) <- c("lCI", "uCI")
rownames(mpg.ci) <- NULL
print(mpg.ci, digits = 4)
```
