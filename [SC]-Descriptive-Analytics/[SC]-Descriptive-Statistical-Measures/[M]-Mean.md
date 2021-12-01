### Mean
Preparation Code
```
library(dplyr)
```
#### **_Sample Task: Compute mean age._**
**Actual Code**
```
mean(A$Age)
```
#### **_Sample Task: Compute mean age for each gender._**
```
A %>% group_by(Sex) %>% summarise(Mean = mean(Age))
```
