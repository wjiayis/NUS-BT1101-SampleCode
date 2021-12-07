## Replacement of Outliers with Mean
###### Preparation Code
```r
# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```r
CS$salary.imp <- CS$salary
CS$salary.imp[CS$salary >= 10000]<- mean(CS$salary)
```
