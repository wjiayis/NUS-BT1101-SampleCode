### Mean
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(vcd)
A <- Arthritis
```
#### **_Sample Task: Compute mean age._**
**Actual Code**
```
mean(A$Age)
```
#### **_Sample Task: Compute mean age for each gender._**
**Actual Code**
```
A %>% group_by(Sex) %>% summarise(Mean = mean(Age))
```
#### **_Sample Task: Compute mean age for each mode of treatment, for each gender._** (CHECK WORDING)
**Actual Code**
```
A %>% group_by(Treatment, Sex) %>% summarise(Mean = mean(Age)) # group by `Treatment`, then group by `Sex`
