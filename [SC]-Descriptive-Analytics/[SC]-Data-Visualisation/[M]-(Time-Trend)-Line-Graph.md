## \[Time Trend\] Line Graph
### Base R Graphic
#### For non-time-series data
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
     ylab = "Gasoline Production", xlab = "Time Trend", type="n")
lines(B$t, B$gas)
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
ggplot(B, aes(x=t, y=gas)) +
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
ggplot(B, aes(x=t, y=bchlimp.ts)) +
  geom_line()
```
