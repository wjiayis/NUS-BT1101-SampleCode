## Logistic Regression
| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable either a factor with 2 levels or numeric with values 0 and 1 only. |

##### Preparation Code
```r
library(titanic)
```
##### Actual Code
1. Run the logistic regression model.
```r
fit <- glm(Survived ~ Sex + Age, family = "binomial", titanic_train)
summary(fit)
```
2. If required, perform prediction.
##### Sample Task 1
>Perform prediction on 1 new observation.
```r
predict(fit, newdata = data.frame(Sex = "male", Age = 35))
```
##### Sample Task 2
>Perform prediction on a test set.
```r
predict(fit, newdata = titanic_test)
```
