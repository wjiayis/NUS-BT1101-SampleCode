### Boxplot
Preparation Code
```
# Sample Data
library(wooldridge)
data(gpa2)
G <- gpa2
```
#### **_Sample Task: Examine extreme outliers (outside 3 IQR)._**
**Actual Code**
```
boxplot(G$verbmath, range = 3, main = "Boxplot to Examine Distribution of Extreme Outliers (outside 3 IQR)")
```
#### **_Sample Task: Examine extreme outliers (outside 1.5 IQR)._**
**Actual Code**
```
boxplot(G$verbmath, range = 1.5, main = "Boxplot to Examine Distribution of Moderate Outliers (outside 1.5 IQR)")
```
