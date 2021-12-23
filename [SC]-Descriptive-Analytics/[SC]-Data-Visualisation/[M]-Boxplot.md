## Boxplot
### Base R Graphic
##### Preparation Code
```r
# Sample Data
library(wooldridge)
G <- gpa2
```
##### Actual Code
###### Sample Task 1
>Identify extreme and moderate outliers (outside 3 IQR and 1.5 IQR respectively).
```r
verbmath.extreme_outliers <- boxplot(G$verbmath, range = 3, main = "Boxplot to Examine Distribution of Extreme Outliers (outside 3 IQR)")
verbmath.extreme_outliers$out

verbmath.moderate_outliers <- boxplot(G$verbmath, range = 1.5, main = "Boxplot to Examine Distribution of Moderate Outliers (outside 1.5 IQR)")
verbmath.moderate_outliers$out
```
###### Sample Task 2
>Remove extreme outliers (outside 3 IQR).[^1]
```r
G.wo_extreme_outliers_verbmath <- G[-which(G$verbmath %in% verbmath.extreme_outliers$out),]
```
### ggplot2 Graphic
##### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(wooldridge)
G <- gpa2
G$ethnicity <- ifelse(gpa2$black == 1, "Black",
                 ifelse(gpa2$white == 1, "White",
                   ifelse(gpa2$black == 0 & gpa2$white == 0, "Others", -1)))
```
##### Actual Code
###### Sample Task 1
>Identify moderate outliers (outside 1 IQR) for `verbmath`.
```r
ggplot(G, aes(y = verbmath)) + 
  geom_boxplot() +
  labs(title = "Boxplot to Examine Distribution of Moderate Outliers (outside 1.5 IQR)")
```
###### Sample Task 2
> Identify moderate outliers (outside 1 IQR) for `verbmath` for each `ethnicity`.
```r
ggplot(G, aes(x = ethnicity, y = verbmath)) + 
  geom_boxplot() +
  labs(title = "Boxplot to Examine Distribution of Moderate Outliers (outside 1.5 IQR)")
```
[^1]: This is one of the many ways to handle outliers.
