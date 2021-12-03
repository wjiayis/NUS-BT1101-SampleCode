### Simple Moving Average
Preparation Code
```
# Functions
library(TTR)
library(ggplot2)

# Sample Data
library(wooldridge)
B <- barium
```
**Actual Code**
```
B$SMA5.predict = dplyr::lag(SMA(B$chnimp, n=5),1) # Window size = 5; lag = 1
B$SMA20.predict = dplyr::lag(SMA(B$chnimp, n=20),1) # Window size = 20; lag = 1

ggplot(B, aes(x=t)) +
  geom_line(aes(y=chnimp, color="Raw")) +
  geom_line(aes(y=SMA5.predict, color="Window5")) +
  geom_line(aes(y=SMA20.predict, color="Window20")) +
  scale_color_manual(name="Legend", values =c("Raw"="black", "Window5"="blue", "Window20"="green")) +
  theme_bw()
```
