### Two-Sample Hypothesis Test for Variance

DIFFERENT FROM LECTURE NOTES (, VS ~)

Preparation Code
```
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
```
**Actual Code**
```
var.test(setosa$Sepal.Length, setosa$Petal.Length)
```
