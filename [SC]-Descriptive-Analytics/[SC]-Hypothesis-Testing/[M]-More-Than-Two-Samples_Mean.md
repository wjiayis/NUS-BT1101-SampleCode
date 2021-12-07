## More Than Two Samples Hypothesis Test for Mean
### ANOVA
###### Preparation Code
```r
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
G <- gpa2
G$ethnicity <- ifelse(G$black == 1, "Black",
                 ifelse(G$white == 1, "White",
                   ifelse(G$black == 0 & G$white == 0, "Others", -1)))
```
Note: Check for the 3 ANOVA assumptions before proceeding.
###### Actual Code
1. ANOVA Test
```r
sat.aov <- aov(sat ~ ethnicity, G)
summary(sat.aov)
```
2. Post-hoc Test
```r
TukeyHSD(sat.aov)
```
### Welch-ANOVA
###### Preparation Code
```r
# Functions
library(dplyr)

# Sample Data
library(vcd)
```
###### Actual Code
1. Welch-ANOVA Test
```r
Arthritis %>% welch_anova_test(Age ~ Improved)  %>% # `Improved` is a factor.
  summary()
```
2. Post-hoc Test
```r
games_howell_test(Arthritis, Age ~ Improved)
```
