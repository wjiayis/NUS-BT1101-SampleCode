### Two-sample Hypothesis Test for Equality of Mean (Independent Samples)
Preparation Code
```
# Sample Data
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
virginica <- iris %>% filter(Species == "virginica")
```
**Actual Code**
```
t.test(setosa$Sepal.Length, virginica$Sepal.Length)
```
