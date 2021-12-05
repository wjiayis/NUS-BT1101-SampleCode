## 'X' Correlation
### Correlation Value
###### Preparation Code
```
# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```
cor(CS$salary, CS$sales)
```
### Correlation Table
###### Preparation Code
```
# Functions
library(psych)

# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```
corr.test(CS[,c("salary", "sales", "roe", "ros")])
```
### Heat Map for Correlation
###### Preparation Code
```
# Functions
library(GGally)

# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```
ggcorr(CS[,c("salary", "sales", "roe", "ros")])
```
