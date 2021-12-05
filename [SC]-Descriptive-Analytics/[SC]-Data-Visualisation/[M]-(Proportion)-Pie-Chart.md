## Pie Chart for Proportion
### Base R Graphic
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-(Proportion)-Pie-Chart-&-Frequency-Table.md)
###### Preparation Code
```
# Functions
library(dplyr)
library(glue)

# Sample Data
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
###### Actual Code
```
pie(HEC$Freq,
    labels = glue::glue("{HEC$Hair}, {round(100 * HEC$Freq/sum(HEC$Freq),2)}%"),
    col = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1"),
    main = "Pie Chart of Frequency of Hair Colour",
    cex.main = 0.9)
```
