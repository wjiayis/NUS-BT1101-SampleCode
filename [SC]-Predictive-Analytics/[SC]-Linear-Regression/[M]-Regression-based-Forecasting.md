# Regression-based Forecasting (LOGISTIC REGRESSION VERSION UNDONE)

| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable is continuous. |

Preparation Code
```
library(wooldridge)
B <- barium
```
**Actual Code**
###### Autoregression
```
B$gas.lagged <- dplyr::lag(B$gas,1)
summary(lm(B$gas ~ B$gas.lagged))
```
###### Simple Linear Regression
```
summary(lm(B$chnimp ~ B$gas.lagged))
```
###### Multiple Linear Regression (w/o Interaction)
```
summary(lm(B$chnimp ~ B$rtwex + B$gas.lagged))
```
###### Multiple Linear Regression (w Interaction)
```
summary(lm(B$chnimp ~ B$rtwex * B$gas.lagged))
summary(lm(B$chnimp ~ B$rtwex * B$gas.lagged + B$spr))
```
