## \[Outlier Identification\] Line Graph
### Base R Graphic
##### Preparation Code
```r
# Sample Data
library(wooldridge)
B <- barium
```
##### Actual Code
###### Sample Task 1
>Identify outliers using the third empirical rule.
```r
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
```r
plot(B$t, B$gas,
     main = "Line Graph of Gasoline Production Over Time",
     ylab = "Gasoline Production", xlab = "Time Trend")
lines(B$t, B$gas)

gas.upper_limit3 <- mean(B$gas) + 1.5*sd(B$gas)
gas.lower_limit3 <- mean(B$gas) - 1.5*sd(B$gas)
abline(h = gas.upper_limit3, col=4)
abline(h = gas.lower_limit3, col=4)
```
### ggplot2 Graphic
##### Preparation Code
```r
# Functions
library(ggplot2)

# Sample Data
library(wooldridge)
B <- barium
```
##### Actual Code
###### Sample Task 1
>Identify outliers using the third empirical rule.
```r
gas.upper_limit3 <- mean(B$gas) + 3*sd(B$gas)
gas.lower_limit3 <- mean(B$gas) - 3*sd(B$gas)

ggplot(B, aes(x=t, y=gas)) +
        geom_line() +
        geom_hline(yintercept=gas.upper_limit3, colour = "blue") +
        geom_hline(yintercept=gas.lower_limit3, colour = "blue") +
        labs(title="Line Graph of Gasoline Production Over Time")
```
###### Sample Task 2
>Identify outliers using the second empirical rule.
```r
gas.upper_limit2 <- mean(B$gas) + 2*sd(B$gas)
gas.lower_limit2 <- mean(B$gas) - 2*sd(B$gas)

ggplot(B, aes(x=t, y=gas)) +
        geom_line() +
        geom_hline(yintercept=gas.upper_limit2, colour = "red") +
        geom_hline(yintercept=gas.lower_limit2, colour = "red") +
        labs(title="Line Graph of Gasoline Production Over Time")
```
