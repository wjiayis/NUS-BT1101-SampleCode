### Two-sample Hypothesis Test for Mean (Independent)
Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
virginica <- iris %>% filter(Species == "virginica")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa == virginica).</br>
H1: Mean sepal length of (setosa != virginica)._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length)
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa >= virginica).</br>
H1: Mean sepal length of (setosa < virginica)._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "less")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa <= virginica).</br>
H1: Mean sepal length of (setosa > virginica)._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "greater")
```
