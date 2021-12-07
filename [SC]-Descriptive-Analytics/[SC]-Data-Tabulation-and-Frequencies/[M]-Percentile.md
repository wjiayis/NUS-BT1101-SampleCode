## Percentile
##### Preparation Code
```r
# Sample Data
library(wooldridge)
```
##### Actual Code
###### Sample Task 1
>Compute the first quartile (Q1).
```r
quantile(gpa2$sat, 0.25)
```
###### Sample Task 2
>Compute the 32% and 78% percentile.
```r
quantile(gpa2$sat, c(0.32, 0.78))
```
