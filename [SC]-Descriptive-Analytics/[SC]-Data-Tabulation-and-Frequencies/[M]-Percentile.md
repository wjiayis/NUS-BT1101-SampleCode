### Percentile
Preparation Code
```
# Sample Data
library(wooldridge)
```
</br>**Actual Code**
###### Sample Task 1: Compute the first quartile (Q1).
```
quantile(gpa2$sat, 0.25)
```
###### Sample Task 2: Compute the 32% and 78% percentile.
```
quantile(gpa2$sat, c(0.32, 0.78))
```
