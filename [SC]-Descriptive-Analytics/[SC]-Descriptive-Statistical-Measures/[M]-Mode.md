### Mode
Preparation Code
```
# Sample Data
library(wooldridge)
G <- gpa2
```
**Actual Code**
```
names(table(G$sat))[table(G$sat) == max(table(G$sat))]
```
