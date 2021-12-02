### One Sample Hypothesis Test for Proportion
**_Sample Hypotheses:</br>
H0: Population proportion of (Miles/(US) gallon > 17) >= 0.18.</br>
H1: Population proportion of (Miles/(US) gallon > 17) < 0.18._**

Preparation Code
```
library(dplyr)
```
**Actual Code**
```
# z-statistic
mpg.17 <- mtcars %>% filter(mpg > 17)
mpg.p17 <- nrow(mpg.17)/nrow(mtcars)
z <- (mpg.p17 - 0.18) / sqrt(0.18*(1-0.18)/nrow(mtcars))
z

# Critical Value
# With no additional information on confidence level (α), α=0.05 is used.
mpg.17.cv <- qnorm(0.05)
mpg.17.cv

z < mpg.17.cv
```
