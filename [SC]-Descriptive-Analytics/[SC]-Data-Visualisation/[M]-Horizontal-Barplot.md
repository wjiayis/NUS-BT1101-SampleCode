### Horizontal Barplot
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
data(HairEyeColor)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
**Actual Code**
```
hair_colour.barplot <- barplot(HEC$Freq,
        horiz = TRUE,
        xlim = c(0,340),
        main = "Barplot of Frequency of Hair Colour",
        names.arg = c("Black", "Brown", "Red", "Blond"),
        las = 1,
        cex.names = 0.9,
        col="pink")

text(y = hair_colour.barplot, x = HEC$Freq, label = HEC$Freq, pos = 4, cex = 1)
```
Additional Notes:
1. Structure of data frame `HEC`

| Discrete Variable* | Continuous Variable* |
| :---: | :---: |
| ... | ... |

\*Variable Name as Column Name
