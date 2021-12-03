### Two-sample Hypothesis Test for Mean (Independent Samples, Equal Variance Assumption Present)
Preparation Code
```
# Sample Data
library(dplyr)
setosa_and_vesicolor <- iris %>% filter(Species != "virginica")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa == vesicolor).</br>
H1: Mean sepal length of (setosa != vesicolor)._**</br>

**Actual Code**</br>
Note: `setosa_and_vesicolor$Species` is a factor.
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, var.equal = TRUE)
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa >= vesicolor).</br>
H1: Mean sepal length of (setosa < vesicolor)._**</br>

**Actual Code**</br>
Note: `setosa_and_vesicolor$Species` is a factor.
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "less", var.equal = TRUE)
```
**_Sample Hypotheses:</br>
H0: Mean sepal length of (setosa <= vesicolor).</br>
H1: Mean sepal length of (setosa > vesicolor)._**</br>

**Actual Code**</br>
Note: `setosa_and_vesicolor$Species` is a factor.
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "greater", var.equal = TRUE)
```
