### Boxplot
Preparation Code
```
# Sample Data
library(wooldridge)
data(gpa2)
G <- gpa2
```
**Actual Code**
```
boxplot(G$verbmath, range = 3, main = "Boxplot to Examine Distribution of Extreme Outliers (outside 3 IQR)")
boxplot(G$verbmath, range = 1.5, main = "Boxplot to Examine Distribution of Moderate Outliers (outside 1.5 IQR)")
```
