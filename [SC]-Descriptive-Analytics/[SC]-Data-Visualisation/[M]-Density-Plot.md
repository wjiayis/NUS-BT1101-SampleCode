### Density Plot
Preparation Code
```
# Sample Data
data(mtcars)
MC <- mtcars
```
**Actual Code**
```
plot(density(MC$mpg),
     main = "Density Plot of Miles/(US) gallon")
```
