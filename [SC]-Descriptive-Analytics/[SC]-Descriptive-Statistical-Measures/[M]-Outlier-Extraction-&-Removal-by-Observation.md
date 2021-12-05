## Outlier Extraction & Removal by Observation
1. Plot the data.
   - Density Plot
   - [Histogram](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md)
2. Identify outliers from the graph.
3. If required, remove outliers.
##### Preparation Code
```
# Functions
library(dplyr)
```
##### Actual Code
###### Sample Task 1
>Extract observations of `mtcars$hp` above 300 (outliers).
```
M.age.outliers <- mtcars %>% filter(mtcars$hp > 300)
```
###### Sample Task 2
>Remove observations of `mtcars$hp` above 300 (outliers).
```
M.age.wo <- mtcars %>% filter(mtcars$hp <= 300)
```
