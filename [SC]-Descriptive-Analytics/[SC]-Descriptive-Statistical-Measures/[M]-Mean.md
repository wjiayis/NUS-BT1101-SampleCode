### Mean
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(vcd)
A <- Arthritis
```

**Actual Code**
###### Sample Task: Compute mean age.
```
mean(A$Age)
```
###### Sample Task: Compute mean age for each gender.
```
A %>% group_by(Sex) %>% summarise(Mean = mean(Age))
```
###### Sample Task: Compute mean age for each mode of treatment, for each gender. (CHECK WORDING)
```
A %>% group_by(Treatment, Sex) %>% summarise(Mean = mean(Age)) # group by `Treatment`, then group by `Sex`
