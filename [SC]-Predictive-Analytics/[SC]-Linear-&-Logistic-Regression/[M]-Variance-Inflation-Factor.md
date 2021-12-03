### Variance Inflation Factor
Preparation Code
```
# Functions
library(car)

# Sample Data
library(wooldridge)
B <- barium
```
**Actual Code**
```
car::vif(lm(chnimp ~ gas + lgas + spr, B))
```
