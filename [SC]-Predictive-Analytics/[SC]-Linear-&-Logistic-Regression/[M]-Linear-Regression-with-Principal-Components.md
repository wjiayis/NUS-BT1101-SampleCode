## Linear Regression with Principal Components
:bulb: The logic is identical to that of regular linear regression.
###### Preparation Code
```r
# Sample Data
library(dplyr)

M <- mtcars %>% select("cyl", "disp", "hp", "drat", "wt", "qsec", "gear", "carb")
pca1 <- prcomp(M, center = TRUE, scale = TRUE)

M <- M %>% mutate(
  pc1 = pca1$x[,"PC1"],
  pc2 = pca1$x[,"PC2"],
  pc3 = pca1$x[,"PC3"],
  pc4 = pca1$x[,"PC4"])
```
###### Actual Code
1. Run the regression model.
```r
fit <- lm(cyl ~ pc1+pc2+pc3+pc4, M)
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
M$predicted <- predict(fit)
M$residuals <- residuals(fit)
```
