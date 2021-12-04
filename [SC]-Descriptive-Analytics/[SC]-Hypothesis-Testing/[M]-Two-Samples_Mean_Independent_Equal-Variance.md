## \[Independent\]\[Equal Variance\] Two-sample Hypothesis Test for Mean
##### Preparation Code
```
# Sample Data
library(dplyr)
setosa_and_vesicolor <- iris %>% filter(Species != "virginica")
```
Note: `setosa_and_vesicolor$Species` is a factor.
##### Actual Code
###### Sample Hypotheses 1:
>H0: Mean sepal length of (setosa = vesicolor).</br>
>H1: Mean sepal length of (setosa ≠ vesicolor).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, var.equal = TRUE)
```
###### Sample Hypotheses 2:
>H0: Mean sepal length of (setosa ≥ vesicolor).</br>
>H1: Mean sepal length of (setosa < vesicolor).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "less", var.equal = TRUE)
```
###### Sample Hypotheses 3:</br>
>H0: Mean sepal length of (setosa ≤ vesicolor).</br>
>H1: Mean sepal length of (setosa > vesicolor).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "greater", var.equal = TRUE)
```
