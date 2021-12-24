## Q-Q Plot
### Base R Graphic
###### Actual Code
```r
qqnorm(mtcars$mpg, main = "Q-Q Plot of Miles/(US) gallon")
qqline(mtcars$mpg, col = 2)
```
### ggplot2 Graphic
###### Actual Code
```r
qplot(sample = mpg, data = mtcars) +
  stat_qq() +
  stat_qq_line(col = 2)
```
