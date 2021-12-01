### Median
Preparation Code
```
# Functions
library(dplyr)
# Sample Data
library(vcd)
A <- Arthritis
```
#### **_Sample Task: Compute median age._**
**Actual Code**
```
median(A$Age)
```
#### **_Sample Task: Compute median age for each gender._**
```
A %>% group_by(Sex) %>% summarise(Median = median(Age))
```
