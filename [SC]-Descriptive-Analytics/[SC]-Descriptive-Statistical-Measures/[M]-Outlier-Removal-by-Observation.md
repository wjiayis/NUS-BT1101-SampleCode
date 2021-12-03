### Outlier Removal by Observation
1. Plot a graph of the data.
2. Identify outliers from the graph.
3. Remove outliers.

###### Sample Task: Remove observations of `mtcars$hp` above 350.
Preparation Code
```
# Functions
library(dplyr)
```
**Actual Code**</br>
```
M <- mtcars %>% filter(mtcars$hp <= 350)
```
