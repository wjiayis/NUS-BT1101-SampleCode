### Principal Component Analysis
Preparation Code
```
# Functions
library(devtools) # For Sample Task 2
library(ggbiplot) # For Sample Task 2

# Sample Data
library(dplyr)
mtcars1 <- select(mtcars, "cyl", "disp", "hp", "drat", "wt", "qsec", "gear", "carb")
```
**Actual Code**
1. Run the principal component analysis.
```
pca1 <- prcomp(mtcars1, center=T, scale=T)
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
3. INCOMPLETE
