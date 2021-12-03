### Principal Component Analysis [LOGISTIC REGRESSION VERSION UNDONE]
Preparation Code
```
# Functions
library(devtools) # For Sample Task 2
library(ggbiplot) # For Sample Task 2

# Sample Data
library(dplyr)
M <- select(mtcars, "cyl", "disp", "hp", "drat", "wt", "qsec", "gear", "carb")
```
**Actual Code**
1. Run the principal component analysis.
```
pca1 <- prcomp(M, center=T, scale=T)
summary(pca1)
```
2. If required, complete relevant tasks.
###### Sample Task 1: Examine loadings on the first 2 principal components.
```
pca1$rotation[,1:2]
```
###### Sample Task 2: Plot the principal components.
```
ggbiplot(pca1)
```
3. If required, extract the first x principal components.
###### Sample Task 1: Extract the first 4 principal components.
```
M <- M %>% mutate(
  pc1 = pca1$x[,"PC1"],
  pc2 = pca1$x[,"PC2"],
  pc3 = pca1$x[,"PC3"],
  pc4 = pca1$x[,"PC4"])
```
###### Sample Task 2: Extract sufficicient principal components to explain 90% of variance.
```
M <- M %>% mutate(
  pc1 = pca1$x[,"PC1"],
  pc2 = pca1$x[,"PC2"],
  pc3 = pca1$x[,"PC3"])
```
4. [Linear Regression with Principal Components](../../[SC]-Predictive-Analytics/[SC]-Linear-&-Logistic-Regression/[M]-Linear-Regression-with-Principal-Components.md)
