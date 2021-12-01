### Proportion
Preparation Code
```
# Functions
library(psych)

# Sample Data
library(wooldridge)
HEC <- as.data.frame(HairEyeColor)
```

**Actual Code**
```
length(HEC$Hair[HEC$Hair == "Brown"])/nrow(HEC)
```
