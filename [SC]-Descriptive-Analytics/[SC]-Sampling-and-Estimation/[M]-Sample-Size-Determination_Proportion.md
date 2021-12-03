### Sample Size Determination for Proportion
**Actual Code**
###### Sample Task:
>Determine number of voters to poll to ensure a sampling error of at most ± 2%.
```
# With no additional information on unbiased estimator of a population proportion (π), π=0.5 is used.
ceiling(qnorm(0.975)^2*((0.5)*(1-0.5))/(0.02)^2)
```
CHECK ACCURACY ON COMMENT ON π
