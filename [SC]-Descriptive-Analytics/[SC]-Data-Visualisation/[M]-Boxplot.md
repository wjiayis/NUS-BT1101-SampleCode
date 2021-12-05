## Boxplot
##### Preparation Code
```
# Sample Data
library(wooldridge)
G <- gpa2
```
##### Actual Code
###### Sample Task 1
>Identify extreme and moderate outliers (outside 3 IQR and 1.5 IQR respectively).
```
verbmath.extreme_outliers <- boxplot(G$verbmath, range = 3, main = "Boxplot to Examine Distribution of Extreme Outliers (outside 3 IQR)")
verbmath.extreme_outliers$out

verbmath.moderate_outliers <- boxplot(G$verbmath, range = 1.5, main = "Boxplot to Examine Distribution of Moderate Outliers (outside 1.5 IQR)")
verbmath.moderate_outliers$out
```
###### Sample Task 2
>Remove extreme outliers (outside 3 IQR).[^1]
```
G.wo_extreme_outliers_verbmath <- G[-which(G$verbmath %in% verbmath.extreme_outliers$out),]
```
[^1]: This is one of the many ways to handle outliers.
