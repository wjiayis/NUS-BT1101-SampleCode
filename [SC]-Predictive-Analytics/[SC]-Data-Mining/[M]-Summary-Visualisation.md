## Summary Visualisation
### Base R Graphics
###### Preparation Code
```
library(psych)
```
###### Actual Code
```
pairs.panels(iris, lm=TRUE)
```
### ggplot2 Graphics
###### Preparation Code
```
library(GGally)
```
###### Actual Code
```
ggpairs(iris)
```
