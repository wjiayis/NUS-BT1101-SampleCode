### Two-sample Hypothesis Test for Mean
#### Independent Samples, Equal Variance Assumption Absent, Numeric on Numeric
Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
virginica <- iris %>% filter(Species == "virginica")
```
**Actual Code**

###### Sample Hypotheses 1:
>H0: Mean sepal length of (setosa == virginica).</br>
>H1: Mean sepal length of (setosa != virginica).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species)
```

###### Sample Hypotheses 2:
>H0: Mean sepal length of (setosa >= virginica).</br>
>H1: Mean sepal length of (setosa < virginica).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "less")
```

###### Sample Hypotheses 3:
>H0: Mean sepal length of (setosa <= virginica).</br>
>H1: Mean sepal length of (setosa > virginica).
```
t.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species, alternative = "greater")
```
