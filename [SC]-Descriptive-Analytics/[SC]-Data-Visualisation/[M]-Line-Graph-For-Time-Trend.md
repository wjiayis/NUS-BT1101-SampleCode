## Line Graph for Time Trend

### Non-time-series Graph
Preparation Code
```
# Sample Data
library(wooldridge)
data(barium)
B <- barium
```
**Actual Code**
```
plot(B$t, B$gas,
     main = "Line Graph of Gasoline Production Over Time",
     ylab = "Gasoline Production", xlab = "Time Trend")
lines(B$t, B$gas)
```
### Time-series Graph
