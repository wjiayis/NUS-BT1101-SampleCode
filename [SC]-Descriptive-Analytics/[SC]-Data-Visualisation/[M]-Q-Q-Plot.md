## Q-Q Plot
### Base R Graphic
###### Preparation Code
```r
# Sample Data
MC <- mtcars
```
###### Actual Code
```r
qqnorm(MC$mpg, main = "Q-Q Plot of Miles/(US) gallon")
qqline(MC$mpg, col = 2)
```
