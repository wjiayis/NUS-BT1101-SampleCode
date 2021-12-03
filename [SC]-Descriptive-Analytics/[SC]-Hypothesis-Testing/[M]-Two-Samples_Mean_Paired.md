### Two-sample Hypothesis Test for Mean (Paired Samples)

DIFFERENT FROM LECTURE NOTES (, VS ~)

Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
```

**Actual Code**
###### Sample Hypotheses 1:
H0: Mean sepal length = mean petal length.</br>
H1: Mean sepal length ≠ mean petal length.
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, paired = TRUE)
```
###### Sample Hypotheses 2:
H0: Mean sepal length ≥ mean petal length.</br>
H1: Mean sepal length < mean petal length.
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "less", paired = TRUE)
```
###### Sample Hypotheses 3:
H0: Mean sepal length ≤ mean petal length.</br>
H1: Mean sepal length > mean petal length.
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "greater", paired = TRUE)
```
