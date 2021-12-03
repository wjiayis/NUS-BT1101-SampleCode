### [HF] Mode
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(vcd)
A <- Arthritis
```
**Actual Code**
1. Helper Function. (Must be included. Do not edit.)
```
calculate.Mode <- function(x){which.max(tabulate(x))}
```
2. **Inputs**. (Must be included. Edit this.)
###### Sample Task: Compute mode age.
```
calculate.Mode(A$Age)
```
###### Sample Task: Compute mode age for each gender.
```
A %>% group_by(Sex) %>% summarise(Mode = calculate.Mode(Age))
```
###### Sample Task: Compute mode age for each mode of treatment, for each gender. (CHECK WORDING)
```
A %>% group_by(Treatment, Sex) %>% summarise(Mode = calculate.Mode(Age)) # group by `Treatment`, then group by `Sex`
```
