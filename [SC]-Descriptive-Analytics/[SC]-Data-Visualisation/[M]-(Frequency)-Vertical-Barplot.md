## \[Frequency\] Vertical Barplot
### Base R Graphic
###### Preparation Code
```r
# Sample Data
library(dplyr)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
###### Actual Code
```r
hair_colour.barplot <- barplot(HEC$Freq, # dataset_variable
        ylim = c(0,340), # Range of y-values
        main = "Barplot of Frequency of Hair Colour", # Title
        cex.main = 1.1, # [Font size] Title
        ylab = "Frequency of Hair Colour", # y-axis label
        xlab = "Hair Colour", # x-axis label
        names.arg = c("Black", "Brown", "Red", "Blond"), # x-axis labels
        las = 1, # [Orientation] x-axis labels
        cex.names = 0.9, # [Font size] x-axis labels
        col="pink") # Colour

text(y = HEC$Freq, x = hair_colour.barplot, label = HEC$Freq, pos = 3, cex = 1) # Value labels
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
ggplot(data = HEC, aes(x = Hair, y = Freq)) + # dataset_variable
  geom_bar(stat = "identity", fill = "pink") + # Colour
  labs(title = "Barplot of Frequency of Hair Colour") + # Title
  #geom_text(aes(label = Freq), vjust = -0.3, color = "black", size = 3.5) # 'Outside-bars' value labels
  geom_text(aes(label = Freq), vjust = 1.6, color = "black", size = 3.5) # 'Within-bars' value labels
```
