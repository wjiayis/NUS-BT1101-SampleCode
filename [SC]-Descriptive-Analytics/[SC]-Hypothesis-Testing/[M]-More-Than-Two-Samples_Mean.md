## >2-Sample Hypothesis Test for Mean
### ANOVA
###### Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
G <- gpa2
G$ethnicity <- ifelse(G$black == 1, "Black",
                  ifelse(G$white ==1, "White",
                         ifelse(G$black ==0 & G$white == 0, "Others", -1)))
```
Note: Check for the 3 ANOVA assumptions before proceeding.
###### Actual Code
1. ANOVA Test GROUPING VARIABLE - FACTOR OR NUMERICS FROM 0?
```
sat.aov <- aov(sat ~ ethnicity, G)
summary(sat.aov)
```
2. Post-hoc Test
```
TukeyHSD(sat.aov)
```
### Welch-ANOVA
###### Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(vcd)
```
###### Actual Code
1. Welch-ANOVA Test
```
Arthritis %>% welch_anova_test(Age ~ Improved)  %>% # `Improved` is a factor.
  summary()
```
2. Post-hoc Test
```
games_howell_test(Arthritis, Age ~ Improved)
```
