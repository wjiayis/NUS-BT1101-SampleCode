### Mode
Preparation Code
```
# Sample Data
library(wooldridge)
data(gpa2)
G <- gpa2
```
**Actual Code**
```
names(table(G$sat))[table(G$sat) == max(table(G$sat))]
```
