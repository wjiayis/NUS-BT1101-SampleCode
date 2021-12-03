### Two-sample Hypothesis Test for Mean
#### _Independent Samples, Equal Variance Assumption Assumption, Numeric on Numeric_</br></br>
Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
virginica <- iris %>% filter(Species == "virginica")
```
</br>**Actual Code**
###### Sample Hypotheses 1:
>H0: Mean sepal length of (setosa = virginica).</br>
>H1: Mean sepal length of (setosa ≠ virginica).
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length)
```

###### Sample Hypotheses 2:
>H0: Mean sepal length of (setosa ≥ virginica).</br>
>H1: Mean sepal length of (setosa < virginica).
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "less")
```

###### Sample Hypotheses 3:
>H0: Mean sepal length of (setosa ≤ virginica).</br>
>H1: Mean sepal length of (setosa > virginica).
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "greater")
```
