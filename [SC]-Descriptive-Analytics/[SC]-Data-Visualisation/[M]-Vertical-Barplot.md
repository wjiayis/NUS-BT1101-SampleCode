### Vertical Barplot</br></br>
Preparation Code
```
# Functions
library(ggplot2) # For ggplot2 Graphics

# Sample Data
library(dplyr)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
</br>**Actual Code**
##### Base R Graphics
```
hair_colour.barplot <- barplot(HEC$Freq, # dataset_variable
        ylim = c(0,330), # Range of y-values
        main = "Barplot of Frequency of Hair Colour", # Title
        names.arg = c("Black", "Brown", "Red", "Blond"), # x-axis labels
        col="pink") # Colour of bars

text(y = HEC$Freq, x = hair_colour.barplot, label = HEC$Freq, pos = 3, cex = 1)
```
##### ggplot2 Graphics
```
ggplot(data=HEC, aes(x=Hair, y=Freq)) + # dataset_variable
  geom_bar(stat="identity", fill = "pink") + # Colour of bars
  #geom_text(aes(label=Freq), vjust=-0.3, color = "black", size=3.5) # "Outside-bars" label
  geom_text(aes(label=Freq), vjust=1.6, color="black", size=3.5) # "Within-bars" label
```
</br>Additional Notes:
1. Structure of data frame `HEC`

| Discrete Variable[^1] | Continuous Variable[^1] |
| :---: | :---: |
| ... | ... |

[^1]: Variable name as column name
