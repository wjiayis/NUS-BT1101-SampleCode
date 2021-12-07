## k-means Clustering
###### Preparation Code
```r
# Functions
library(factoextra) # For `fviz_cluster()` (Optional Step 3)

# Sample Data
library(dplyr)
M <- mtcars %>% select("cyl", "disp", "hp", "drat", "wt", "qsec", "gear", "carb")
```
###### Actual Code
1. Using the elbow method, determine the number of clusters.
```r
wss <- rep(NA, 10)
for(k in c(1:10)) {wss[k] = kmeans(M, k, nstart = 10)$tot.withinss}

plot(wss, type = "b",
     xlab = "Number of clusters", ylab = "Total within-cluster sum of squares")
```
2. Perform k-means clustering.
```r
km_obj <- kmeans(M, 2, nstart=10)
```
3. If required, plot the clusters.
```r
fviz_cluster(km_obj, M)
```
