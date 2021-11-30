## Line Graph for Cumulative Frequency and Cumulative Relative Frequency
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
data(rdchem)
R <- rdchem
rd.breaks <- seq(0, 1500, by=100)
rd.cut <- cut(R$rd, rd.breaks, right=FALSE)
rd.frequency_table <- table(rd.cut) %>% transform() %>% mutate(cumulative_frequency = cumsum(Freq), cumulative_relative_frequency = cumulative_frequency/nrow(R))
```
### Cumulative Frequency
**Actual Code**
```
# To start at 0
rd.cumulative_frequency <- c(0,rd.frequency_table$cumulative_frequency)

plot(rd.breaks, rd.cumulative_frequency,
     main = "Line Graph of Cumulative Frequency of R&D spending, millions",
     xlab = "R&D spending, millions",
     ylab = "Cumulative Frequency")
lines(rd.breaks, rd.cumulative_frequency)
```
### Cumulative Relative Frequency
**Actual Code**
```
# To start at 0
rd.cumulative_relative_frequency <- c(0,rd.frequency_table$cumulative_relative_frequency)

plot(rd.breaks, rd.cumulative_relative_frequency,
     main = "Line Graph of Cumulative Frequency of R&D spending, millions",
     xlab = "R&D spending, millions",
     ylab = "Cumulative Relative Frequency")
lines(rd.breaks, rd.cumulative_relative_frequency)
```
