### Scatterplot
Preparation Code
```
# Functions
library(dplyr)
library(knitr)
library(glue)

# Sample Data
library(wooldridge)
CS <- ceosal1
```
**Actual Code**
```
plot(CS$lsalary, CS$lsales)
```
