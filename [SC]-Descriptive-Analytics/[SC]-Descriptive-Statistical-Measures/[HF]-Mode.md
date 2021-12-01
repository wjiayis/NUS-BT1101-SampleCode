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
#### **_Sample Task: Compute mode._**
```
calculate.Mode(A$Age)
```
#### **_Sample Task: Compute mode for each gender._**
```
A %>% group_by(Sex) %>% summarise(Mode = calculate.Mode(Age))
```
#### **_Sample Task: Compute mode for for each mode of treatment, for each gender._** (CHECK WORDING)
```
A %>% group_by(Treatment, Sex) %>% summarise(Mode = calculate.Mode(Age)) # group by `Treatment`, then group by `Sex`
```
