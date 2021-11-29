### Vertical Barplot
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
        ylim = c(0,330),
        main = "Barplot of Frequency of Hair Colour",
        names.arg = c("Black", "Brown", "Red", "Blond"),
        col="pink")

text(y = sample_df$Freq, x = bar, label = sample_df$Freq, pos = 3, cex = 1)
```
Additional Notes:
1. Structure of `sample_df`

| Discrete Variable (Variable Name as Column Name) | Continuous Variable (Variable Name as Column Name) |
| :---: | :---: |
| ... | ... |
