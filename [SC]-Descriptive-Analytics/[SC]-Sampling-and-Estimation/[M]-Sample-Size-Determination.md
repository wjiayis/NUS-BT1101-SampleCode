## Sample Size Determination
### Mean
##### Actual Code
###### Sample Task
>The distribution for volume is normal with sample mean = 796ml and population standard deviation = 15ml.</br>
What sample size is needed to reduce the margin of error to at most 3ml, when developing a 95% confidence interval for the mean volume for population?
```
ceiling(qnorm(0.975)^2*(15^2)/(3^2))
```
### Proportion
##### Actual Code
###### Sample Task
>Determine number of voters to poll to ensure a sampling error of at most ± 2%.
```
# With no additional information on unbiased estimator of a population proportion (π), π=0.5 is used.
ceiling(qnorm(0.975)^2*((0.5)*(1-0.5))/(0.02)^2)
```
