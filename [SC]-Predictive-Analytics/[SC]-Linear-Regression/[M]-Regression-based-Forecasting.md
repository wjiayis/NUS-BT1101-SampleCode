# Regression-based Forecasting

| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable is continuous. |

Preparation Code
```
library(wooldridge)
B <- barium
```
**Actual Code**
1. Run the linear regression model.
###### Autoregression
```
B$gas.lagged <- dplyr::lag(B$gas,1)
fit <- lm(B$gas ~ B$gas.lagged)
summary(fit)
```
###### Simple Linear Regression
```
fit <- lm(B$chnimp ~ B$gas.lagged)
summary(fit)
```
###### Multiple Linear Regression (w/o Interaction)
```
fit <- lm(B$chnimp ~ B$rtwex + B$gas.lagged)
summary(fit)
```
###### Multiple Linear Regression (w Interaction)
```
fit <- lm(B$chnimp ~ B$rtwex * B$gas.lagged + B$spr)
#fit <- lm(B$chnimp ~ B$rtwex * B$gas.lagged)
summary(fit)
```
2. Examine its residual plots.
```
plot(fit, 1)
plot(fit, 2)
abline(a=0, b=0)
```
3. If required, obtain prediction and/or residuals.
```
B$predicted <- predict(fit)
B$residuals <- residuals(fit)
```
