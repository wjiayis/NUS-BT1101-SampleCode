### One Sample Hypothesis Test for Mean
**_Sample Hypotheses:</br>
H0: Mean Miles/(US) gallon of all automobiles == 19, at 95% confidence level.</br>
H1: Mean Miles/(US) gallon of all automobiles != 19, at 95% confidence level._**</br>

**Actual Code**
```
t.test(mtcars$mpg,
       alternative = "two.sided",
       mu = 19,
       conf.level = 0.95)
```
**_Sample Hypotheses:</br>
H0: Mean Miles/(US) gallon of all automobiles <= 19, at 90% confidence level.</br>
H1: Mean Miles/(US) gallon of all automobiles > 19, at 90% confidence level._**</br>

**Actual Code**
```
t.test(mtcars$mpg,
       alternative = "greater",
       mu = 19,
       conf.level = 0.90)
```
**_Sample Hypotheses:</br>
H0: Mean Miles/(US) gallon of all automobiles >= 23, at 99% confidence level.</br>
H1: Mean Miles/(US) gallon of all automobiles < 23, at 99% confidence level._**</br>

**Actual Code**
```
t.test(mtcars$mpg,
       alternative = "less",
       mu = 23,
       conf.level = 0.99)
```
