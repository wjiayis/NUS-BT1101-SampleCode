## \[Independent\]\[Numeric on Numeric\] Two-sample Hypothesis Test for Mean
##### Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
virginica <- iris %>% filter(Species == "virginica")
```
##### Actual Code
1. Enter the first 2-3 arguments.
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
2. If equal variance assumption is present, add a keyword argument `var.equal = TRUE`.
3. If samples are paired, add a keyword argument `paired = TRUE`.
