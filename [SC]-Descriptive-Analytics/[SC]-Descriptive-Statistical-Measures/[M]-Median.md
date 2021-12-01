### Median
Preparation Code
```
library(dplyr)
```
#### **_Sample Task: Compute mean age._**
**Actual Code**
```
median(A$Age)
```
#### **_Sample Task: Compute mean age for each gender._**
```
A %>% group_by(Sex) %>% summarise(Median = median(Age))
```
