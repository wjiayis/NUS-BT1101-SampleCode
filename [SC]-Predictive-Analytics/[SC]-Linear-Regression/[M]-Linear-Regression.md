### Simple Linear Regression (w/o Interaction)

| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable is continuous. |

**Actual Code**</br>
1. Run the linear regression model.
```
fit <- lm(mpg ~ hp, mtcars)
summary(fit)
```
2. Examine its residual plots.
```
plot(fit, 1)
plot(fit, 2)
abline(a=0, b=0)
```
3. If required, obtain prediction and/or residuals
```
mtcars$predicted <- predict(fit)
mtcars$residuals <- residuals(fit)
```
### Multiple Linear Regression (w/o Interaction)

| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable is continuous. |

**Actual Code**</br>
1. Run the linear regression model.
```
fit <- lm(Petal.Length ~ Species + Sepal.Length, iris)
summary(fit)
```
2. Examine its residual plots.
```
plot(fit, 1)
plot(fit, 2)
abline(a=0, b=0)
```
3. If required, obtain prediction and/or residuals
```
iris$predicted <- predict(fit)
iris$residuals <- residuals(fit)
```
