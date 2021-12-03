### Two-sample Hypothesis Test for Mean
#### _Independent Samples, Equal Variance Assumption Assumption, Numeric on Factor_

</br>

| Implicit Assumptions |
| :---: |
| Factor variable only 2 levels. |

</br>

Preparation Code
```
# Sample Data
library(dplyr)
setosa_and_vesicolor <- iris %>% filter(Species != "virginica")
```
</br>**Actual Code**

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
