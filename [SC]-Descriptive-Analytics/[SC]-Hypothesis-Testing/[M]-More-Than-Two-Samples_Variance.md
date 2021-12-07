## More Than Two Samples Hypothesis Test for Variance
### If all samples are normally distributed
###### Preparation Code
```r
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
G <- gpa2
G$ethnicity <- ifelse(G$black == 1, "Black",
                 ifelse(G$white == 1, "White",
                   ifelse(G$black == 0 & G$white == 0, "Others", -1)))
```
###### Actual Code
```r
bartlett.test(G$sat, G$ethnicity)
```
### Otherwise
###### Actual Code
```r
fligner.test(iris$Sepal.Length, iris$Species)
```
