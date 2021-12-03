### Logistic Regression
| Implicit Assumptions |
| :---: |
| :white_medium_square: Dependent variable either a factor with 2 levels or numeric with values 0 and 1 only. |

Preparation Code
```
library(titanic)
```
**Actual Code**
1. Run the logistic regression model.
```
fit <- glm(Survived ~ Sex + Age, family="binomial", titanic_train)
summary(fit)
```
2. If required, perform prediction.
```
predict(fit, newdata = data.frame(Sex="male", Age=35))
```
