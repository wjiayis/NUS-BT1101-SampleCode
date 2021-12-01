### [HF] Normal Distribution, Sample Mean, Population Standard Deviation &#8594; Confidence Interval
#### **_Sample Task:</br>The distribution for volume is normal with sample mean = 796 and population standard deviation = 15.</br>Compute the 95% confidence interval for the mean volume for population._**
**Actual Code**
1. Helper function. (Must be included. Do not edit.)
```
calculate.ConfidenceInterval.Known.Population.sd <- function(sample_mean, sample_size, population_sd, confidence_level.decimal){
  lCI <- sample_mean+qnorm((1-confidence_level.decimal)/2)*population_sd/sqrt(sample_size)
  uCI <- sample_mean-qnorm((1-confidence_level.decimal)/2)*population_sd/sqrt(sample_size)
  cbind(lCI, uCI)}
```
2. **Inputs**. (Must be included. Edit this.)
```
calculate.ConfidenceInterval.Known.Population.sd(796, # sample_mean
                                                 25, # sample_size
                                                 15, # population_sd
                                                 0.95) # confidence_level.decimal
```
