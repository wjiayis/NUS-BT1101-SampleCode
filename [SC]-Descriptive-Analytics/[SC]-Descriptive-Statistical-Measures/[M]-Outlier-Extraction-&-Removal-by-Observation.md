### Extract / Remove Outlier by Observation
1. Plot a graph of the data.
2. Identify outliers from the graph.
3. Remove outliers.

Preparation Code
```
# Functions
library(dplyr)
```
###### Sample Task: Extract observations of `mtcars$hp` above 300 (outliers).
**Actual Code**</br>
```
M.age.outliers <- mtcars %>% filter(mtcars$hp > 300)
```
###### Sample Task: Remove observations of `mtcars$hp` above 300 (outliers).
**Actual Code**</br>
```
M.age.wo <- mtcars %>% filter(mtcars$hp <= 300)
```
