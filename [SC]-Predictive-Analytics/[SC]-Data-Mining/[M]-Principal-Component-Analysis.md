## Principal Component Analysis
##### Preparation Code
```r
# Functions
library(devtools) # For Sample Task 2.1
library(ggbiplot) # For Sample Task 2.1

# Sample Data
library(dplyr)
M <- select(mtcars, "cyl", "disp", "hp", "drat", "wt", "qsec", "gear", "carb") # Do not include DV
```
##### Actual Code
1.  Run the principal component analysis.
```r
pca1 <- prcomp(M, # For other questions ----- Ensure that it only contains continuous variables
               center = TRUE, scale = TRUE)
summary(pca1)
```
###### Sample Task 2.1
>Plot the principal components.
```r
ggbiplot(pca1)
```
###### Sample Task 3.1
>Examine loadings on the first 2 principal components.
```r
pca1$rotation[,1:2]
```
###### Sample Task 4.1
> Extract the first 4 principal components.
```r
M <- M %>% mutate(
  pc1 = pca1$x[,"PC1"],
  pc2 = pca1$x[,"PC2"],
  pc3 = pca1$x[,"PC3"],
  pc4 = pca1$x[,"PC4"])
```
###### Sample Task 4.2
>Extract sufficicient principal components to explain 90% of variance.
```r
M <- M %>% mutate(
  pc1 = pca1$x[,"PC1"],
  pc2 = pca1$x[,"PC2"],
  pc3 = pca1$x[,"PC3"]) # Cumulative proportion = 0.92094 (in this case)
```
5. Incorporate the principal components into regression models.
- Continuous DV &#8594; [Linear Regression with Principal Components](../../[SC]-Predictive-Analytics/[SC]-Linear-&-Logistic-Regression/[M]-Linear-Regression-with-Principal-Components.md)
- Binary DV &#8594; [Logistic Regression with Principal Components](../../[SC]-Predictive-Analytics/[SC]-Linear-&-Logistic-Regression/[M]-Logistic-Regression-with-Principal-Components.md)
