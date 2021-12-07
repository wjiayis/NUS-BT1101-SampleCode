## Contingency Table
##### Preparation Code
```r
# Functions
library(rpivotTable)

# Sample Data
library(wooldridge)
G <- gpa2
G$ethnicity <- ifelse(G$black == 1, "Black",
                 ifelse(G$white ==1, "White",
                   ifelse(G$black ==0 & G$white == 0, "Others", -1)))
```
##### Actual Code
###### Sample Task 1
>Produce an rpivotTable of count.
```r
rpivotTable(G,
            cols = c("female", "ethnicity"),
            rows = "athlete",
            aggregatorName = "Count")
```
###### Sample Task 2
>Produce an rpivotTable of count as a fraction of total.
```r
rpivotTable(G,
            cols = c("female", "ethnicity"),
            rows = "athlete",
            aggregatorName = "Count as Fraction of Total")
```
