## Summary Visualisation
### Base R Graphics
###### Preparation Code
```r
# Functions
library(psych)
```
###### Actual Code
```r
pairs.panels(iris, lm = TRUE)
```
</br></br>
### ggplot2 Graphics
###### Preparation Code
```r
# Functions
library(GGally)
```
###### Actual Code
```r
ggpairs(iris)
```
