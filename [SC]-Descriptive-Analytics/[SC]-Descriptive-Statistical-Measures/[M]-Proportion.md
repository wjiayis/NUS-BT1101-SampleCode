## Proportion
###### Preparation Code
```r
# Functions
library(psych)

# Sample Data
library(wooldridge)
HEC <- as.data.frame(HairEyeColor)
```

###### Actual Code
```r
length(HEC$Hair[HEC$Hair == "Brown"])/nrow(HEC)
```
