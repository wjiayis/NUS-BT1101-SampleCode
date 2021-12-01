### Boxplot
Preparation Code
```
# Sample Data
library(wooldridge)
G <- gpa2
```
#### **_Sample Task: Examine extreme and moderate outliers (outside 3 IQR and 1.5 IQR respectively)._**
**Actual Code**
```
boxplot(G$verbmath, range = 3, main = "Boxplot to Examine Distribution of Extreme Outliers (outside 3 IQR)")
boxplot(G$verbmath, range = 1.5, main = "Boxplot to Examine Distribution of Moderate Outliers (outside 1.5 IQR)")
```
#### **_Sample Task: Remove extreme outliers (outside 3 IQR)._**
```
```
