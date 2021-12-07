## 'X' Correlation
### Correlation Value
###### Preparation Code
```r
# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```r
cor(CS$salary, CS$sales)
```
### Correlation Table
###### Preparation Code
```r
# Functions
library(psych)

# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```r
corr.test(CS[,c("salary", "sales", "roe", "ros")])
```
### Heat Map for Correlation
###### Preparation Code
```r
# Functions
library(GGally)

# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```r
ggcorr(CS[,c("salary", "sales", "roe", "ros")])
```
