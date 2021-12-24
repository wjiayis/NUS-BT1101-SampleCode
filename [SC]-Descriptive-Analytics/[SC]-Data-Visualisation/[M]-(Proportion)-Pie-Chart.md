## Pie Chart for Proportion
### Base R Graphic
###### Preparation Code
```r
# Functions
library(glue)

# Sample Data
library(dplyr)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
###### Actual Code
```r
pie(HEC$Freq,
    labels = glue::glue("{HEC$Hair}, {round(100 * HEC$Freq/sum(HEC$Freq),2)}%"),
    main = "Pie Chart of Frequency of Hair Colour",
    cex.main = 0.9,
    col = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1"))
```
### ggplot2 Graphic
###### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(dplyr)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
###### Actual Code
```r
ggplot(HEC, aes(x = "", y = Freq, fill = Hair)) +
        geom_bar(width = 1, stat = "identity") +
        coord_polar("y", start = 0) +
        scale_fill_manual(values = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1"))
```
