## Summary Visualisation
### Base R Graphics
###### Preparation Code
```r
library(psych)
```
###### Actual Code
```r
pairs.panels(iris, lm=TRUE)
```
</br></br>
### ggplot2 Graphics
###### Preparation Code
```r
library(GGally)
```
###### Actual Code
```r
ggpairs(iris)
```
