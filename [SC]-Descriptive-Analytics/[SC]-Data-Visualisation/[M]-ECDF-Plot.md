### ECDF plot
Preparation Code
```
# Sample Data
data(mtcars)
MC <- mtcars
```
**Actual Code**
```
plot(ecdf(MC$mpg),
     main = "Cumulative Frequency of Miles/(US) gallon",
     xlab = "Miles/(US) gallon")
```
