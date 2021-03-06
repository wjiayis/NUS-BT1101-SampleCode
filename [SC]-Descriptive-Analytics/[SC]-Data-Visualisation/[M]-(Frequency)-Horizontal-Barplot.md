## \[Frequency\] Horizontal Barplot
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
        horiz = TRUE,
        xlim = c(0,340), # Range of x-values
        main = "Barplot of Frequency of Hair Colour", # Title
        cex.main = 1.1, # [Font size] Title
        names.arg = c("Black", "Brown", "Red", "Blond"), # y-axis labels
        las = 1, # [Orientation] y-axis labels
        cex.names = 0.9, # [Font size] y-axis labels
        col = "pink") # Colour

text(y = hair_colour.barplot, x = HEC$Freq, label = HEC$Freq, pos = 4, cex = 1) # Value labels
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
ggplot(data = HEC, aes(x = Freq, y = Hair)) + # dataset_variable
  geom_bar(stat = "identity", fill = "pink") + # Colour
  labs(title = "Barplot of Frequency of Hair Colour") + # Title
  #geom_text(aes(label = Freq), hjust = -0.3, color = "black", size = 3.5) # 'Outside-bars' value labels
  geom_text(aes(label = Freq), hjust = 1.6, color = "black", size = 3.5) # 'Within-bars' value labels
```
