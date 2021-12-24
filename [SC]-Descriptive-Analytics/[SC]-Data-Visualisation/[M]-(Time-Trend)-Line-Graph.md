## \[Time Trend\] Line Graph
### Base R Graphic
#### For non-time-series data
##### Single Line
###### Preparation Code
```r
# Sample Data
library(wooldridge)
B <- barium
```
###### Actual Code
```r
plot(B$t, B$gas,
     main = "Line Graph of Gasoline Production Over Time",
     ylab = "Gasoline Production", xlab = "Time Trend", type = "n")
lines(B$t, B$gas)
```
##### Multiple Lines
###### Preparation Code
```r
# Sample Data
library(dplyr)
library(wooldridge)
P <- prminwge
```
###### Actual Code
```r
plot(P$prgnp,
     ylim = c(0, 5000),
     main = "Line Graph of Imports over Time",
     ylab = "Gross National Income", xlab = "Time Trend", type = "n")
lines(P$prgnp, col = "lightblue")  
lines(P$usgnp, col = "pink")
legend("topleft",
       legend = c("Puerto Rico", "United States"),
       col = c("lightblue", "pink"),
       lty = 1,
       cex = 0.8)
```
#### For time-series data
###### Preparation Code
```r
# Sample Data
library(wooldridge)
B <- barium
B$bchlimp.ts <- ts(B$bchlimp, frequency = 12, start = c(1981,1))
```
###### Actual Code
```r
plot(B$bchlimp.ts)
```
### ggplot2 Graphic
#### For non-time-series data
###### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(wooldridge)
B <- barium
```
###### Actual Code
```r
ggplot(B, aes(x = t, y = gas)) +
  geom_line()
```
#### For time-series data
###### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(wooldridge)
B <- barium
B$bchlimp.ts <- ts(B$bchlimp, frequency = 12, start = c(1981,1))
```
###### Actual Code
```r
ggplot(B, aes(x = t, y = bchlimp.ts)) +
  geom_line()
```
