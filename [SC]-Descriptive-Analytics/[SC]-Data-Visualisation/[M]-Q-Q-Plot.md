## Q-Q Plot
### Base R Graphic
###### Actual Code
```r
qqnorm(mtcars$mpg, main = "Q-Q Plot of Miles/(US) gallon")
qqline(mtcars$mpg, col = 2)
```
