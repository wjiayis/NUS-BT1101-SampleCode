### Two-sample Hypothesis Test for Mean (Independent Samples, No Equal Variance Assumption)
Preparation Code
```
# Sample Data
library(dplyr)
# For M1
setosa <- iris %>% filter(Species == "setosa")
virginica <- iris %>% filter(Species == "virginica")
# For M2
setosa_and_vesicolor <- iris %>% filter(Species != "virginica")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa == virginica).</br>
H1: Mean sepal length of (setosa != virginica)._**</br>

\[M1\] **Actual Code**
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length)
```
\[M2\] **Actual Code**</br>
Note: `setosa_and_vesicolor$Species` is a factor.
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species)
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa >= virginica).</br>
H1: Mean sepal length of (setosa < virginica)._**</br>

\[M1\] **Actual Code**
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "less")
```
\[M2\] **Actual Code**</br>
Note: `setosa_and_vesicolor$Species` is a factor.
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "less")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa <= virginica).</br>
H1: Mean sepal length of (setosa > virginica)._**</br>

\[M1\] **Actual Code**
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "greater")
```
\[M2\] **Actual Code**</br>
Note: `setosa_and_vesicolor$Species` is a factor.
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "greater")
```
