## [Linear Regression] Regression-based Forecasting

| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable is continuous. |

##### Preparation Code
```r
library(wooldridge)
B <- barium
```
##### Actual Code
1. If required, perform lagging.
```r
B$gas.lagged <- dplyr::lag(B$gas,1)
```
2. Run the linear regression model.
###### Autoregression
```r
fit <- lm(B$gas ~ B$gas.lagged)
summary(fit)
```
###### Simple Linear Regression
```r
fit <- lm(B$chnimp ~ B$gas.lagged)
summary(fit)
```
###### Multiple Linear Regression (w/o Interaction)
```r
fit <- lm(B$chnimp ~ B$rtwex + B$gas.lagged)
summary(fit)
```
###### Multiple Linear Regression (w Interaction)
```r
fit <- lm(B$chnimp ~ B$rtwex * B$gas.lagged + B$spr)
#fit <- lm(B$chnimp ~ B$rtwex * B$gas.lagged)
summary(fit)
```
3. Examine its residual plots.
```r
plot(fit, 1)
plot(fit, 2)
abline(a = 0, b = 0)
```
4. If required, obtain prediction and/or residuals.
```r
B$predicted <- predict(fit)
B$residuals <- residuals(fit)
```
