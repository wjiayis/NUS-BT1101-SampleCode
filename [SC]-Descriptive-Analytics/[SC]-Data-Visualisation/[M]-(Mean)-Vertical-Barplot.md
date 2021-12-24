## \[Mean\] Vertical Barplot
### Base R Graphic
###### Preparation Code
```r
# Functions
library(dplyr)
library(tidyr)

# Sample Data
library(wooldridge)
M <- mathpnl %>% select(c(math4, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                   ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, Year) %>% group_by(Year) %>% summarise(Mean = mean(math4, na.rm=TRUE))
```
###### Actual Code
```r
satisfaction.barplot <- barplot(M$Mean, # dataset_variable
        ylim = c(0,70), # Range of y-values
        main = "Barplot of Mean Satisfaction", # Title
        cex.main = 1.1, # [Font size] Title
        ylab = "Mean Satisfaction", # y-axis label
        xlab = "Year", # x-axis label
        names.arg = c("1992","1993","1994","1995"), # x-axis labels
        las = 1, # [Orientation] x-axis labels
        cex.names = 0.9, # [Font size] x-axis labels
        col="pink") # Colour

text(y = M$Mean, x = satisfaction.barplot, label = round(M$Mean,3), pos = 3, cex = 1) # Value labels
```
### ggplot2 Graphic
###### Preparation Code
```r
# Functions
library(dplyr)
library(tidyr)
library(ggplot2)

# Sample Data
library(wooldridge)
M <- mathpnl %>% select(c(math4, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993",
                   ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, Year) %>% group_by(Year) %>% summarise(Mean = mean(math4, na.rm=TRUE))
```
###### Actual Code
```r
ggplot(data = M, aes(x = Year, y = Mean)) + # dataset_variable
  geom_bar(stat = "identity",
           fill = "pink") + # Colour
  geom_errorbar(aes(ymin = Mean - sd, ymax = Mean + sd), width = 0.2, col = "grey55") + # Error bars
  labs(title = "Bar Plot of Mean Satisfaction") + # Title
  #geom_text(aes(label = round(Mean,2)), vjust = -0.3, color = "black", size = 3.5) # 'Outside-bars' value labels
  geom_text(aes(label = round(Mean,2)), vjust = 1.6, color = "black", size = 3.5) # 'Within-bars' value labels
```
