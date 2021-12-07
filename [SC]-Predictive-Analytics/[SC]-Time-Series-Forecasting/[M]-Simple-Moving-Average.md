## Simple Moving Average
##### Preparation Code
```r
# Functions
library(TTR)
library(glue)
library(ggplot2) # For ggplot2 graphic

# Sample Data
library(wooldridge)
B <- barium
```
##### Actual Code
1. Choose the window size that produces the lowest root mean square error.
```r
for (k in 2:20){
  B$bchlimpSMA <- SMA(B$bchlimp, n = k)
  rmse <- sqrt(mean((B$bchlimpSMA - B$chnimp)^2, na.rm = TRUE))
  print(glue::glue("{k}: {rmse}"))}
```
2. Run a Simple Moving Average model.
```r
# `B$bchlimp` is not a ts object.
B$bchlimp.SMA16.predict <-  dplyr::lag(SMA(B$bchlimp, n=16),1) # Window size = 16; lag = 1
```
3. If required, plot the prediction graph.
###### Base R Graphic
```r
plot(B$t, B$bchlimp, type="n")
lines(B$bchlimp)
lines(B$bchlimp.SMA16.predict, col="blue")
```
###### ggplot2 Graphic
```r
ggplot(B, aes(x=t)) +
  geom_line(aes(y=bchlimp, color="Raw")) +
  geom_line(aes(y=bchlimp.SMA16.predict, color="Window16")) +
  scale_color_manual(name="Legend", values =c("Raw"="black", "Window16"="blue"))
```
