## \[CumFreq & CumRelFreq\] Line Graph
### Base R Graphic
###### Preparation Code
```r
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
R <- rdchem
rd.breaks <- seq(0, 1500, by = 100)
rd.cut <- cut(R$rd, rd.breaks, right = FALSE)
rd.frequency_table <- table(rd.cut) %>% transform() %>% mutate(cumulative_frequency = cumsum(Freq), cumulative_relative_frequency = cumulative_frequency/nrow(R))
```
#### Cumulative Frequency
###### Actual Code
```r
rd.cumulative_frequency <- c(0,rd.frequency_table$cumulative_frequency) # To start at 0

plot(rd.breaks, rd.cumulative_frequency,
     main = "Line Graph of Cumulative Frequency of R&D spending, millions",
     xlab = "R&D spending, millions",
     ylab = "Cumulative Frequency")
lines(rd.breaks, rd.cumulative_frequency)
```
#### Cumulative Relative Frequency
###### Actual Code
```r
rd.cumulative_relative_frequency <- c(0,rd.frequency_table$cumulative_relative_frequency) # To start at 0

plot(rd.breaks, rd.cumulative_relative_frequency,
     main = "Line Graph of Cumulative Frequency of R&D spending, millions",
     xlab = "R&D spending, millions",
     ylab = "Cumulative Relative Frequency")
lines(rd.breaks, rd.cumulative_relative_frequency)
```
### ggplot2 Graphic
###### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(dplyr)
library(wooldridge)
R <- rdchem
rd.breaks <- seq(0, 1500, by = 100)
rd.cut <- cut(R$rd, rd.breaks, right = FALSE)
rd.frequency_table <- table(rd.cut) %>% transform() %>% mutate(cumulative_frequency = cumsum(Freq), cumulative_relative_frequency = cumulative_frequency/nrow(R))
```
#### Cumulative Frequency
###### Actual Code
```r
rd.cumulative_frequency <- c(0,rd.frequency_table$cumulative_frequency) # To start at 0

ggplot(mapping = aes(x = 1:length(rd.cumulative_frequency), y = rd.cumulative_frequency)) +
  geom_line() +
  labs(title = "Line Graph of Cumulative Frequency of R$rd",
        x = "R&D spending, millions", y = "Cumulative Frequency")
```
#### Cumulative Relative Frequency
###### Actual Code
```r
rd.cumulative_relative_frequency <- c(0,rd.frequency_table$cumulative_relative_frequency) # To start at 0

ggplot(mapping = aes(x = 1:length(rd.cumulative_relative_frequency), y = rd.cumulative_relative_frequency)) +
  geom_line() +
  labs(title = "Line Graph of Cumulative Relative Frequency of R$rd",
        x = "R&D spending, millions", y = "Cumulative Relative Frequency")
```
