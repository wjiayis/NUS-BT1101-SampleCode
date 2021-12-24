## \[Frequency\] Stacked Barplot
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
improvement.stacked_barplot <- barplot(improvement.m,
        beside = FALSE,
        ylim = c(0, 60),
        names.arg = c("Placebo", "Treated"), # Redundant in this case (columns are labeled)
        main = "Bar Plot of Improvement, By Mode of Treatment",
        ylab = "Frequency of Improvement",
        cex.main = 0.95,
        cex.names = 0.9,
        col = c("plum2", "lightgoldenrod1", "lightblue"))

legend("topright",
       fill = c("plum2", "lightgoldenrod1", "lightblue"),
       c("None", "Some", "Marked"),
       cex = 0.9)

H <- apply(improvement.m, 2L, cumsum) - improvement.m
text(x = rep(improvement.stacked_barplot, each = nrow(H)), y = H,
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
  geom_bar(stat = "identity") +
  labs(title = "Bar Plot of Mean Satisfaction for Math, By Year of Graduation") + # Title
  geom_text(aes(label = n), vjust = 1.6, color = "black", position = position_stack(0.9), size = 3.5) + # Value labels
  scale_fill_manual(values = c("lightgoldenrod1", "pink", "lightsteelblue1")) # Colours
```
