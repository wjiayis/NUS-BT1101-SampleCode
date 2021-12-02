### Confidence Interval (Unknown Population sd)
:white_heart: [_Helper Function Available_](../../[SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Confidence-Interval_Mean_Unknown-Population-sd.md)

Preparation Code
```
library(Rmisc)
```
**Actual Code**
```
mpg.ci <- CI(mtcars$mpg, ci = 0.95)
mpg.ci <- cbind(mpg.ci[3],mpg.ci[1])
colnames(mpg.ci) <- c("lCI", "uCI")
rownames(mpg.ci) <- NULL
print(mpg.ci, digits = 4)
```
