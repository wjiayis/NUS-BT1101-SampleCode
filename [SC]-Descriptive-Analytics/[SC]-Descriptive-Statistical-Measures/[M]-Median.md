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
**Actual Code**
```
A %>% group_by(Sex) %>% summarise(Median = median(Age))
```
#### **_Sample Task: Compute median age for each mode of treatment, for each gender._**
**Actual Code**
```
A %>% group_by(Treatment, Sex) %>% summarise(Median = median(Age)) # group by `Treatment`, then group by `Sex`
```
