## One-Sample Hypothesis Test for Proportion
##### Preparation Code
```r
library(dplyr)
```
##### Actual Code
###### Sample Hypotheses:
>H0: Population proportion of (Miles/(US) gallon > 17) ≥ 0.18.</br>
>H1: Population proportion of (Miles/(US) gallon > 17) < 0.18.</br>
>Note: Confidence level is assumed to be 95% unless otherwise specified.
```r
# z-statistic
mpg.17 <- mtcars %>% filter(mpg > 17)
mpg.p17 <- nrow(mpg.17) / nrow(mtcars)
z <- (mpg.p17 - 0.18) / sqrt(0.18*(1-0.18)/nrow(mtcars))
z

# Critical Value
mpg.17.cv <- qnorm(0.05)
mpg.17.cv

z < mpg.17.cv
```
