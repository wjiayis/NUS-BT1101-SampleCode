### Two-sample Hypothesis Test for Mean (Paired Samples)
Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length == mean petal length.</br>
H1: Mean sepal length != mean petal length._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, setosa$Petal.Length)
```
**_Sample Hypotheses:</br>
H0: Mean sepal length >= mean petal length.</br>
H1: Mean sepal length < mean petal length._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "less")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length <= mean petal length.</br>
H1: Mean sepal length > mean petal length._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "greater")
```
