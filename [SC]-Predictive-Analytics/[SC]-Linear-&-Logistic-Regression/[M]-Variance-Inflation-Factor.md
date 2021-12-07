## Variance Inflation Factor
###### Preparation Code
```r
# Functions
library(car)

# Sample Data
library(wooldridge)
B <- barium
```
###### Actual Code
```r
car::vif(lm(chnimp ~ gas + lgas + spr, B))
```
