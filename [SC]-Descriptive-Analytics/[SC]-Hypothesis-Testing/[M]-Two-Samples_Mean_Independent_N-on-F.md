## \[Independent\]\[Numeric on Factor\] Two-sample Hypothesis Test for Mean

| Implicit Assumptions |
| :---: |
| :white_medium_square: Factor variable only 2 levels. |

##### Preparation Code
```
# Sample Data
library(dplyr)
setosa_and_vesicolor <- iris %>% filter(Species != "virginica")
```
##### Actual Code
###### Sample Hypotheses 1:
>H0: Mean sepal length of (setosa = vesicolor).</br>
>H1: Mean sepal length of (setosa ≠ vesicolor).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species)
```
###### Sample Hypotheses 2:
>H0: Mean sepal length of (setosa ≥ vesicolor).</br>
>H1: Mean sepal length of (setosa < vesicolor).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "less")
```
###### Sample Hypotheses 3:
>H0: Mean sepal length of (setosa ≤ vesicolor).</br>
>H1: Mean sepal length of (setosa > vesicolor).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "greater")
```
