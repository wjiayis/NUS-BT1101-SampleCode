### Simple Moving Average
Preparation Code
```
# Functions
library(TTR)
library(ggplot2)
library(glue)

# Sample Data
library(wooldridge)
B <- barium
```
**Actual Code**
1. Choose the window size that produces the lowest root mean square error.
```
for (k in 2:20){
  B$bchlimpSMA <- SMA(B$bchlimp, n = k)
  rmse <- sqrt(mean((B$bchlimpSMA - B$chnimp)^2, na.rm = TRUE))
  print(glue::glue("{k}: {rmse}"))}
```
2. Produce a Simple Moving Average model.
```
B$bchlimp.SMA16.predict <-  dplyr::lag(SMA(B$bchlimp, n=16),1) # Window size = 16; lag = 1

ggplot(B, aes(x=t)) +
  geom_line(aes(y=bchlimp, color="Raw")) +
  geom_line(aes(y=bchlimp.SMA16.predict, color="Window16")) +
  scale_color_manual(name="Legend", values =c("Raw"="black", "Window16"="blue")) +
  theme_bw()
```
