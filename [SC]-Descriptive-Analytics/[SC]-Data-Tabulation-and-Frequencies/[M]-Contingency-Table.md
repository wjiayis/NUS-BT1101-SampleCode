### Contingency Table
Preparation Code
```
# Functions
library(rpivotTable)

# Sample Data
library(wooldridge)
G <- gpa2
G$ethnicity <- ifelse(G$black == 1, "Black",
                  ifelse(G$white ==1, "White",
                         ifelse(G$black ==0 & G$white == 0, "Others", -1)))
```
**Actual Code**
```
rpivotTable(G,
            cols = c("female", "ethnicity"),
            rows = "athlete",
            aggregatorName = "Count")
```
