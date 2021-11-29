### Vertical Barplot
Preparation Code
```
# Functions
library(dplyr)
# Data
data(HairEyeColor)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
**Actual Code**
```
hair_colour.barplot <- barplot(HEC$Freq,
        ylim = c(0,330),
        main = "Barplot of Frequency of Hair Colour",
        names.arg = c("Black", "Brown", "Red", "Blond"),
        col="pink")

text(y = HEC$Freq, x = hair_colour.barplot, label = HEC$Freq, pos = 3, cex = 1)
```
Additional Notes:
1. Structure of data frame `HEC`

| Discrete Variable* | Continuous Variable* |
| :---: | :---: |
| ... | ... |

\*Variable Name as Column Name
