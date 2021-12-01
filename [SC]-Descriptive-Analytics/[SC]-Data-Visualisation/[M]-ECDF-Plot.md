### ECDF plot
Preparation Code
```
# Sample Data
MC <- mtcars
```
**Actual Code**
```
plot(ecdf(MC$mpg),
     main = "Cumulative Frequency of Miles/(US) gallon",
     xlab = "Miles/(US) gallon")
```
