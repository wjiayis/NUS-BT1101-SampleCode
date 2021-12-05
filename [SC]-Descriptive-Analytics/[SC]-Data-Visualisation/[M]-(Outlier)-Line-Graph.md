## \[Outlier Identification\] Line Graph
### Base R Graphic
##### Preparation Code
```
# Sample Data
library(wooldridge)
B <- barium
```
##### Actual Code
###### Sample Task 1
>Identify outliers using the third empirical rule.
```
plot(B$t, B$gas,
     main = "Line Graph of Gasoline Production Over Time",
     ylab = "Gasoline Production", xlab = "Time Trend")
lines(B$t, B$gas)

gas.upper_limit3 <- mean(B$gas) + 3*sd(B$gas)
gas.lower_limit3 <- mean(B$gas) - 3*sd(B$gas)
abline(h = gas.upper_limit3, col=2)
abline(h = gas.lower_limit3, col=2)
```
###### Sample Task 2
>Identify outliers using the second empirical rule.
```
plot(B$t, B$gas,
     main = "Line Graph of Gasoline Production Over Time",
     ylab = "Gasoline Production", xlab = "Time Trend")
lines(B$t, B$gas)

gas.upper_limit3 <- mean(B$gas) + 1.5*sd(B$gas)
gas.lower_limit3 <- mean(B$gas) - 1.5*sd(B$gas)
abline(h = gas.upper_limit3, col=4)
abline(h = gas.lower_limit3, col=4)
```
