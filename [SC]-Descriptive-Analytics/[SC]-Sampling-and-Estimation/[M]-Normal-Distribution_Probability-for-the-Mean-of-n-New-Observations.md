## \[ND\]\[Pop Sd\] Probability for the Mean of n New Observations
##### Actual Code
###### Sample Task
>The distribution for purchase amounts is normal with mean = $36 and standard deviation = $8.</br>Find the probability that the mean purchase amount for 16 customers exceeds $40.
```
standard_error <- 8 - sqrt(16)
1 − pnorm(40, 36, standard_error)
```
