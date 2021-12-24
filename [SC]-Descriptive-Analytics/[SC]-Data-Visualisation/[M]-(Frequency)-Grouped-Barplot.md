## \[Frequency\] Grouped Barplot
### Base R Graphic
###### Preparation Code
```r
# Functions
library(dplyr)
library(tidyr)
library(knitr)

# Sample Data
library(vcd)
A <- Arthritis
improvement <- A %>% group_by(Treatment, Improved) %>% count()
improvement <- improvement %>% spread(Treatment, n)
improvement.m <- improvement[,2:3] %>% as.matrix()
```
###### Actual Code
```r
improvement.grouped_barplot <- barplot(improvement.m, # dataset_variable
        beside = TRUE,
        ylim = c(0, 35), # Range of y-values
        main = "Bar Plot of Improvement, By Mode of Treatment", # Title
        cex.main = 1, # [Font size] Title
        ylab = "Frequency of Improvement", # y-axis label
        cex.names = 0.9, # [Font size] x-axis labels
        col = c("plum2", "lightgoldenrod1", "lightblue")) # Colours

legend("topright",
       fill = c("plum2", "lightgoldenrod1", "lightblue"),
       c("None", "Some", "Marked"),
       cex = 0.9) # [Font size] Legend

# Value labels
text(y = improvement.m, x = improvement.grouped_barplot,
     label = round(improvement.m, 2), pos = 3, cex = 0.9)
```
### ggplot2 Graphic
###### Preparation Code
```r
# Functions
library(dplyr)
library(knitr)
library(ggplot2)

# Sample Data
library(vcd)
A <- Arthritis
improvement <- A %>% group_by(Treatment, Improved) %>% count()
```
###### Actual Code
```r
ggplot(data = improvement, aes(x = Treatment, y = n, fill = Improved)) + # dataset_variable
  geom_bar(stat = "identity", position = position_dodge()) +
  labs(title = "Bar Plot of Improvement, By Mode of Treatment") + # Title
  geom_text(aes(label = n), vjust = 1.6, color = "black", position = position_dodge(0.9), size = 3.5) + # Value labels
  scale_fill_manual(values = c("lightgoldenrod1", "pink", "lightsteelblue1")) # Colours
```
