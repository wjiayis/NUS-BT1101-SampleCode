## Pareto Analysis
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Data-Tabulation-and-Frequencies/[HF]-Pareto-Analysis.md)

###### Preparation Code
```
# Sample Data
library(wooldridge)
R <- rdchem
```
###### Actual Code
```
# Sort R$rd in descending order
rd.descending_order <- sort(R$rd, decreasing = TRUE)
# Compute relative frequency
rd.descending_order.percentage <- rd.descending_order / sum(rd.descending_order)
# Compute cumulative relative frequency
rd.descending_order.percentage.cumulative <- cumsum(rd.descending_order.percentage)
# Compute output
output <- which(rd.descending_order.percentage.cumulative > 0.8)[1]
output
output.percentage <- glue::glue("{round((100*output/nrow(R)),3)}%")
output.percentage
```
