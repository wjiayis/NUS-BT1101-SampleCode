## Holt Winters
##### Preparation Code
```
# Take 10 years for fitting, last 2 years for evaluation
ap.train <- window(AirPassengers, start=1949, end=1958.917) # ts object
ap.test <- window(AirPassengers, start=1959, end=1960.917) # ts object
```
##### Actual Code
1. Run `HoltWinters` with different specifications.
```
fit1 <- HoltWinters(ap.train)
fit2 <- HoltWinters(ap.train, gamma = FALSE)
fit3 <- HoltWinters(ap.train, beta = FALSE, gamma = FALSE)
```
2. Select the fit with lowest root mean square error.
```
fit1.prediction <- predict(fit1, n.ahead = 24)
fit2.prediction <- predict(fit2, n.ahead = 24)
fit3.prediction <- predict(fit3, n.ahead = 24)

sqrt(mean((fit1.prediction - ap.test)^2)) # lowest
sqrt(mean((fit2.prediction - ap.test)^2))
sqrt(mean((fit3.prediction - ap.test)^2))
```
4. Plot the prediction graph.
###### Base R Graphic
```
plot(fit1, fit1.prediction)
lines(ap.test, col='blue')
```
###### ggplot2 Graphic (UNDONE)
```
```
