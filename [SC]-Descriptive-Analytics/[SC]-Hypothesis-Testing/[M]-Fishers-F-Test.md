## \[Two-sample\]\[Variance\] Fisher's F Test
### Numeric on numeric
##### Preparation Code
```
library(dplyr)
setosa <- iris %>% filter(Species == "setosa")
```
##### Actual Code
```
var.test(setosa$Sepal.Length, setosa$Petal.Length)
```
### Numeric on factor
##### Preparation Code
```
library(dplyr)
setosa_and_vesicolor <- iris %>% filter(Species != "virginica")
```
##### Actual Code
```
var.test(setosa_and_vesicolor$Sepal.Length ~ setosa_and_vesicolor$Species)
```
