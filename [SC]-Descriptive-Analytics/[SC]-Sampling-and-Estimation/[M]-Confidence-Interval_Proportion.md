## Confidence Interval for Proportion
##### Preparation Code
```r
library(dplyr)
```
##### Actual Code
###### Sample Task
>Develop 95% confidence interval for proportion of mpg > 25.
```r
mpg.n <- nrow(mtcars)
mpg.25 <- mtcars %>% filter(mpg>25)
mpg.p25 <- nrow(mpg.25)/mpg.n

mpg.margin_of_error <- (qnorm(0.975)*sqrt(mpg.p25*(1-mpg.p25)/mpg.n))
mpg.lCI <- mpg.p25 - mpg.margin_of_error
mpg.uCI <- mpg.p25 + mpg.margin_of_error
print(cbind(mpg.lCI, mpg.uCI),digits = 3)
```
