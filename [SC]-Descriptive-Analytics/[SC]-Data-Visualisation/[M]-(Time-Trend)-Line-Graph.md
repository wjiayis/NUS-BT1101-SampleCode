## \[Time Trend\] Line Graph
### Base R Graphic
#### Non-time-series Graph
###### Preparation Code
```
# Sample Data
library(wooldridge)
B <- barium
```
###### Actual Code
```
plot(B$t, B$gas,
     main = "Line Graph of Gasoline Production Over Time",
     ylab = "Gasoline Production", xlab = "Time Trend")
lines(B$t, B$gas)
```
#### Time-series Graph
###### Preparation Code
```
# Sample Data
library(wooldridge)
B <- barium
B$bchlimp.ts <- ts(B$bchlimp, frequency = 12, start = c(1981,1))
```
###### Actual Code
```
plot(B$bchlimp.ts)
```
