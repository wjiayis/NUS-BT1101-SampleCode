### Percentile
#### **Sample Task: Compute the 32% and 78% percentile.**
Preparation Code
```
# Sample Data
library(wooldridge)
data(gpa2)
```
**Actual Code**
```
quantile(gpa2$sat, c(.32,.78))
```
