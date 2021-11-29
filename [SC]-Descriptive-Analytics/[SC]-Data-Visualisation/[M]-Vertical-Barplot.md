### Vertical Barplot
```{r Vertical Barplot, echo=TRUE}
#################################################################################
#################################################################################
# Functions
library(dplyr)
# Data
data(HairEyeColor)
sample_df <- HairEyeColor %>% as.data.frame()
sample_df <- sample_df[c("Hair", "Freq")]
sample_df <- aggregate(Freq~Hair, sample_df, sum)
#################################################################################
#################################################################################

bar <- barplot(sample_df$Freq,
        ylim = c(0,330),
        main = "Barplot of Frequency of Hair Colour",
        names.arg = c("Black", "Brown", "Red", "Blond"),
        col="pink")

text(y = sample_df$Freq, x = bar, label = sample_df$Freq, pos = 3, cex = 1)
     
# Notes:
##### Structure of sample_df ######
#    [Discrete Variable]    [Continuous Variable] ---- Column Names
#            ...                     ...
```
