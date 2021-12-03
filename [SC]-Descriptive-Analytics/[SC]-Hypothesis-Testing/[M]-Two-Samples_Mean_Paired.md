### Two-sample Hypothesis Test for Mean (Paired Samples)

DIFFERENT FROM LECTURE NOTES (, VS ~)

Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
```
**_Sample Hypotheses:</br>
H0: Mean sepal length == mean petal length.</br>
H1: Mean sepal length != mean petal length._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, paired = TRUE)
```
**_Sample Hypotheses:</br>
H0: Mean sepal length >= mean petal length.</br>
H1: Mean sepal length < mean petal length._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "less", paired = TRUE)
```
**_Sample Hypotheses:</br>
H0: Mean sepal length <= mean petal length.</br>
H1: Mean sepal length > mean petal length._**</br>

**Actual Code**
```
t.test(setosa$Sepal.Length, setosa$Petal.Length, alternative = "greater", paired = TRUE)
```
