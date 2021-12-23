## Logistic Regression with Principal Components
:bulb: The logic is identical to that of regular logistic regression.
###### Preparation Code
```r
# Sample Data
library(tidyverse)
library(titanic)

titanic_train <- titanic_train %>% select(Survived, Age, SibSp, Parch, Fare) %>% drop_na()

pca1 <- prcomp(formula = ~.-Survived, data = titanic_train,
               center = TRUE, scale = TRUE)

titanic_train <- titanic_train %>% mutate(
  pc1 = pca1$x[,"PC1"],
  pc2 = pca1$x[,"PC2"],
  pc3 = pca1$x[,"PC3"])
```
###### Actual Code
1. Run the regression model.
```r
fit <- glm(Survived ~ pc1 + pc2 + pc3, family = "binomial", titanic_train)
summary(fit)
```
2. Examine its residual plots.
```r
plot(fit, 1)
plot(fit, 2)
abline(a = 0, b = 0)
```
3. If required, obtain prediction and/or residuals.
```r
titanic_train$predicted <- predict(fit)
titanic_train$residuals <- residuals(fit)
```
