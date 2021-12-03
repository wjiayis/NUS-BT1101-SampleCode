### Linear Regression with Principal Components
Preparation Code
```
# Sample Data
library(dplyr)
M <- mtcars %>% select("cyl", "disp", "hp", "drat", "wt", "qsec", "gear", "carb")
pca1 <- prcomp(M, center=T, scale=T)
summary(pca1)

M <- M %>% mutate(
  pc1 = pca1$x[,"PC1"],
  pc2 = pca1$x[,"PC2"],
  pc3 = pca1$x[,"PC3"],
  pc4 = pca1$x[,"PC4"])
```
**Actual Code**
```
summary(lm(cyl ~ pc1+pc2+pc3+pc4, M))
```
