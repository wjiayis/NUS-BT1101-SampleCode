## Outlier Extraction & Removal by Observation
1. Plot the data and identify outliers.
   - [Density plot](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Density-Plot.md)
   - [Histogram](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md)
2. If required, remove outliers.
##### Preparation Code
```r
# Functions
library(dplyr)
```
##### Actual Code
###### Sample Task 1
>Extract observations of `mtcars$hp` above 300 (outliers).
```r
M.age.outliers <- mtcars %>% filter(mtcars$hp > 300)
```
###### Sample Task 2
>Remove observations of `mtcars$hp` above 300 (outliers).
```r
M.age.wo <- mtcars %>% filter(mtcars$hp <= 300)
```
