## One-Sample Hypothesis Test for Mean
##### Actual Code
###### Sample Hypotheses 1:
>At 95% confidence level,</br>
>H0: Mean population mpg = 19.</br>
>H1: Mean population mpg ≠ 19.
```
t.test(mtcars$mpg,
       alternative = "two.sided",
       mu = 19,
       conf.level = 0.95)
```
###### Sample Hypotheses 2:
>At 90% confidence level,</br>
>H0: Mean population mpg ≥ 19.</br>
>H1: Mean population mpg < 19.
```
t.test(mtcars$mpg,
       alternative = "less",
       mu = 19,
       conf.level = 0.90)
```
###### Sample Hypotheses 3:
> At 99% confidence level,</br>
>H0: Mean population mpg ≤ 15.</br>
>H1: Mean population mpg > 15.
```
t.test(mtcars$mpg,
       alternative = "greater",
       mu = 15,
       conf.level = 0.99)
```
