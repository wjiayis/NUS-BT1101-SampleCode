## Linear Regression

| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable is continuous. |

##### Actual Code
1. Run the linear regression model.
###### [Regression-based Forecasting](../../[SC]-Predictive-Analytics/[SC]-Linear-&-Logistic-Regression/[M]-Regression-based-Forecasting_Linear-Regression.md)
###### [Linear Regression with Principal Components](../../[SC]-Predictive-Analytics/[SC]-Linear-&-Logistic-Regression/[M]-Linear-Regression-with-Principal-Components.md)

###### Simple Linear Regression
```
fit <- lm(mpg ~ hp, mtcars)
summary(fit)
```
###### Multiple Linear Regression (w/o Interaction)
```
fit <- lm(Petal.Length ~ Species + Sepal.Length, iris)
summary(fit)
```
###### Multiple Linear Regression (w Interaction)
```
fit <- lm(Petal.Length ~ Species * Sepal.Length + Sepal.Width, iris)
#fit <- lm(Petal.Length ~ Species * Sepal.Length, iris)
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
iris$predicted <- predict(fit)
iris$residuals <- residuals(fit)
```


