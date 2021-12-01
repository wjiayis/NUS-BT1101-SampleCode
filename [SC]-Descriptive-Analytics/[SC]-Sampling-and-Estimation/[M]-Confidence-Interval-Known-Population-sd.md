### Normal Distribution, Sample Mean, Population Standard Deviation &#8594; Confidence Interval
:white_heart: [_Helper Function Available_]([SC]-Descriptive-Analytics/[SC]-Sampling-and-Estimation/[HF]-Confidence-Interval-Known-Population-sd.md)
#### **_Sample Task 1:</br>The distribution for volume is normal with sample mean = 796 and population standard deviation = 15.</br>Compute the 95% confidence interval for the mean volume for population._**
**Actual Code**
```
lCI <- 796+qnorm((1-0.95)/2)*15/sqrt(25)
uCI <- 796-qnorm((1-0.95)/2)*15/sqrt(25)
cbind(lCI, uCI)
```
