## \[Numeric on Numeric\] Two-sample Hypothesis Test for Mean
### Unpaired Samples
##### Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
virginica <- iris %>% filter(Species == "virginica")
```
##### Actual Code
- If equal variance assumption is present, include an additional keyword argument `var.equal = TRUE`.
###### Sample Hypotheses 1.1:
>H0: Mean sepal length of (setosa = virginica).</br>
>H1: Mean sepal length of (setosa ≠ virginica).
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length)
```
###### Sample Hypotheses 1.2:
>H0: Mean sepal length of (setosa ≥ virginica).</br>
>H1: Mean sepal length of (setosa < virginica).
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "less")
```
###### Sample Hypotheses 1.3:
>H0: Mean sepal length of (setosa ≤ virginica).</br>
>H1: Mean sepal length of (setosa > virginica).
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length, alternative = "greater")
```
### Paired Samples
##### Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
```
##### Actual Code
- If equal variance assumption is present, include an additional keyword argument `var.equal = TRUE`.
###### Sample Hypotheses 2.1:
>H0: Mean sepal length = mean petal length.</br>
>H1: Mean sepal length ≠ mean petal length.
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, paired = TRUE)
```
###### Sample Hypotheses 2.2:
>H0: Mean sepal length ≥ mean petal length.</br>
>H1: Mean sepal length < mean petal length.
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "less", paired = TRUE)
```
###### Sample Hypotheses 2.3:
>H0: Mean sepal length ≤ mean petal length.</br>
>H1: Mean sepal length > mean petal length.
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "greater", paired = TRUE)
```
