## Scatterplot
### Base R Graphic
###### Preparation Code
```
# Sample Data
library(wooldridge)
CS <- ceosal1
```
###### Actual Code
```
plot(y = CS$lsalary, x = CS$lsales)
```
