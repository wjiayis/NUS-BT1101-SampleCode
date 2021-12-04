## Vertical Barplot
</br>Preparation Code
```
# Functions
library(ggplot2) # For ggplot2 graphic

# Sample Data
library(dplyr)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
</br>**Actual Code**
###### Base R Graphic
```
hair_colour.barplot <- barplot(HEC$Freq, # dataset_variable
        ylim = c(0,340), # Range of y-values
        main = "Barplot of Frequency of Hair Colour", # Title
        cex.main = 1.1, # [Font size] Title
        names.arg = c("Black", "Brown", "Red", "Blond"), # x-axis labels
        las = 1, # [Orientation] x-axis labels
        cex.names = 0.9, # [Font size] x-axis labels
        col="pink") # Colour

text(y = HEC$Freq, x = hair_colour.barplot, label = HEC$Freq, pos = 3, cex = 1)
```
###### ggplot2 Graphic
```
ggplot(data=HEC, aes(x=Hair, y=Freq)) + # dataset_variable
  geom_bar(stat="identity", fill = "pink") + # Colour
  #geom_text(aes(label=Freq), vjust=-0.3, color = "black", size=3.5) # 'Outside-bars' value labels
  geom_text(aes(label=Freq), vjust=1.6, color="black", size=3.5) # 'Within-bars' value labels
```
</br>Additional Notes:
1. Structure of data frame `HEC`

| Discrete Variable[^1] | Continuous Variable[^1] |
| :---: | :---: |
| ... | ... |

[^1]: Variable name as column name
