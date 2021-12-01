### Mode
Preparation Code
```
# Sample Data
library(wooldridge)
G <- gpa2
```
#### **_Sample Task: Compute mode._**
**Actual Code**
```
names(table(G$sat))[table(G$sat) == max(table(G$sat))]
```
