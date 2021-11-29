### Horizontal Barplot
Preparation Code
```
# Functions
library(dplyr)
# Data
data(HairEyeColor)
sample_df <- HairEyeColor %>% as.data.frame()
sample_df <- sample_df[c("Hair", "Freq")]
sample_df <- aggregate(Freq~Hair, sample_df, sum)
```
Actual Code
```
bar <- barplot(sample_df$Freq,
        horiz = TRUE,
        xlim = c(0,340),
        main = "Barplot of Frequency of Hair Colour",
        names.arg = c("Black", "Brown", "Red", "Blond"),
        las = 1,
        cex.names = 0.9,
        col="pink")

text(y = bar, x = sample_df$Freq, label = sample_df$Freq, pos = 4, cex = 1)
```
Additional Notes:
1. Structure of `sample_df`

| Discrete Variable* | Continuous Variable* |
| :---: | :---: |
| ... | ... |

\*Variable Name as Column Name
