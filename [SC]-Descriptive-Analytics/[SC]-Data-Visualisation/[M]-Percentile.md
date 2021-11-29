### Percentile
Preparation Code
```
# Sample Data
library(wooldridge)
data(gpa2)
```
#### **_Sample Task: Compute the first quartile (Q1)._**
**Actual Code**
```
quantile(gpa2$sat, 0.25)
```
#### **_Sample Task: Compute the 32% and 78% percentile._**
**Actual Code**
```
quantile(gpa2$sat, c(0.32, 0.78))
```
