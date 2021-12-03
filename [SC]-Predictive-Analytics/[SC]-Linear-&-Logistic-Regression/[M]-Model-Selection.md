### Model Selection
**Actual Code**
```
fit.full <- lm(Petal.Length ~ Species + Sepal.Length, iris)
fit.restricted <- lm(Petal.Length ~ Species, iris)
anova(fit.full, fit.restricted)
```
