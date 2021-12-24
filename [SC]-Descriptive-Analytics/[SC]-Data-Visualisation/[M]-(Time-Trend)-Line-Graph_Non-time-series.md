## \[Time Trend\]\[Non-time-series\] Line Graph
### Base R Graphic
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
<br>

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
     main = "Line Graph of Gross National Product over Time",
     ylab = "Gross National Product", xlab = "Time Trend", type = "n")
lines(P$prgnp, col = "lightblue")  
lines(P$usgnp, col = "pink")
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
```
###### Actual Code
```r
ggplot(B, aes(x = t, y = gas)) +
  geom_line()
```
<br>

##### Multiple Lines
###### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(dplyr)
library(babynames)
B <- babynames %>% 
  filter(name %in% c("Ashley", "Patricia", "Helen")) %>%
  filter(sex=="F")
```
###### Actual Code
```r
ggplot(B, aes(x=year, y=n, group=name, color=name)) +
    geom_line()
```
