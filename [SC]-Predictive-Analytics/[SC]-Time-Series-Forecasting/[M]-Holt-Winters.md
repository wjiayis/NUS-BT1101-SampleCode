### Holt Winters
Preparation Code
```
# Take 10 years for fitting, last 2 years for evaluation
ap.train <- window(AirPassengers, start=1949, end=1958.917)
ap.test <- window(AirPassengers, start=1959, end=1960.917)
```
**Actual Code**
1. Run `HoltWinters` with different specifications.
```
fit1 <- HoltWinters(ap.train)
fit2 <- HoltWinters(ap.train, gamma = FALSE)
fit3 <- HoltWinters(ap.train, beta = FALSE, gamma = FALSE)

fit1.prediction <- predict(fit1, n.ahead = 24)
plot(fit1, fit1.prediction)
lines(ap.test, col='blue')
sqrt(mean((fit1.prediction - ap.test)^2)) # lowest

fit2.prediction <- predict(fit2, n.ahead = 24)
plot(fit2, fit2.prediction)
lines(ap.test, col='blue')
sqrt(mean((fit2.prediction - ap.test)^2))

fit3.prediction <- predict(fit3, n.ahead = 24)
plot(fit3, fit3.prediction)
lines(ap.test, col='blue')
sqrt(mean((fit3.prediction - ap.test)^2))
```
2. Select the fit with lowest root mean square error (RMSE).
