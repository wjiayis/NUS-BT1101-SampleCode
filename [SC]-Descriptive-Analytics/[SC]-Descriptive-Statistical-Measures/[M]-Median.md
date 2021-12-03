### Median
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(vcd)
A <- Arthritis
```
</br>**Actual Code**
###### Sample Task: Compute median age.
```
median(A$Age)
```
###### Sample Task: Compute median age for each gender.
```
A %>% group_by(Sex) %>% summarise(Median = median(Age))
```
###### Sample Task: Compute median age for each mode of treatment, for each gender. (CHECK WORDING)
```
A %>% group_by(Treatment, Sex) %>% summarise(Median = median(Age)) # group by `Treatment`, then group by `Sex`
```
