### Percentile
Preparation Code
```
# Sample Data
library(wooldridge)
data(gpa2)
```
#### **Sample Task: Compute the first quartile.**
**Actual Code**
```
quantile(gpa2$sat, 0.25)
```
#### **Sample Task: Compute the 32% and 78% percentile.**
**Actual Code**
```
quantile(gpa2$sat, c(0.32, 0.78))
```
