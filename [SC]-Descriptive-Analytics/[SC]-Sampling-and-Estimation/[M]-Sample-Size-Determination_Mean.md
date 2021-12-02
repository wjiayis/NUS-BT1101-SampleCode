### Sample Size Determination for Mean
**_Sample Task:</br>
The distribution for volume is normal with sample mean = 796ml and population standard deviation = 15ml.</br>
What sample size is needed to reduce the margin of error to at most 3ml, when developing a 95% confidence interval for the mean volume for population?_**

**Actual Code**
```
ceiling(qnorm(0.975)^2*(15^2)/(3^2))
```
