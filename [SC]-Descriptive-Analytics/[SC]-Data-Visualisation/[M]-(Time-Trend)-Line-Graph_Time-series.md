## \[Time Trend\]\[Time-series\] Line Graph
### Base R Graphic
##### Single Line
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
<br>

##### Multiple Lines
###### Preparation Code
```r
library(wooldridge)
P <- prminwge
P$prgnp.ts <- ts(P$prgnp, start = c(1950,1))
P$usgnp.ts <- ts(P$usgnp, start = c(1950,1))
```
###### Actual Code
```r
plot(P$prgnp.ts,
     ylim = c(0, 5000),
     main = "Line Graph of Gross National Product over Time",
     ylab = "Gross National Product", xlab = "Year", type = "n")
lines(P$prgnp.ts, col = "lightblue")  
lines(P$usgnp.ts, col = "pink")
legend("topleft",
       legend = c("Puerto Rico", "United States"),
       col = c("lightblue", "pink"),
       lty = 1,
       cex = 0.8)
```
<br>

### ggplot2 Graphic
##### Single Line
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
<br>

##### Multiple Lines
###### Preparation Code
```r
# Functions
library(tidyr)
library(ggplot2)

# Sample Data
library(wooldridge)
P <- prminwge
P$prgnp.ts <- ts(P$prgnp, start = c(1950,1))
P$usgnp.ts <- ts(P$usgnp, start = c(1950,1))
```
###### Actual Code
```r
P %>%
  gather(key = "Country", value = "GNP", prgnp, usgnp) %>%
  ggplot(aes(x = year, y = GNP, color = Country)) +
  geom_line()
```
