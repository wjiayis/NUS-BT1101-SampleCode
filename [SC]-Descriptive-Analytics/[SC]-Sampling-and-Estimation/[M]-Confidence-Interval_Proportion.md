### Confidence Interval for Proportion

Preparation Code
```
library(dplyr)
```
**Actual Code**
##### Sample Task: Develop 95% confidence interval for proportion of mpg > 25.
```
mpg.n <- nrow(mtcars)
mpg.25 <- mtcars %>% filter(mpg>25)
mpg.p25 <- nrow(mpg.25)/mpg.n
mpg.lCI <- mpg.p25 + (qnorm(0.025)*sqrt(mpg.p25*(1-mpg.p25)/mpg.n))
mpg.uCI <- mpg.p25 - (qnorm(0.025)*sqrt(mpg.p25*(1-mpg.p25)/mpg.n))
print(cbind(mpg.lCI, mpg.uCI),digits=3)
```
