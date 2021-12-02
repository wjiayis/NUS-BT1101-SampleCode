### Normal Distribution, Sample Mean, Population Standard Deviation &#8594; Confidence Interval
:white_heart: [_Helper Function Available_](../../[SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Confidence-Interval-Known-Population-sd.md)
#### **_Sample Task:</br>The distribution for volume is normal with sample mean = 796 and population standard deviation = 15.</br>Compute the 95% confidence interval for the mean volume for population._**
**Actual Code**
```
precision <- qnorm(0.975)*15/sqrt(25)
lCI <- 796-precision
uCI <- 796+precision
cbind(lCI, uCI)
```
