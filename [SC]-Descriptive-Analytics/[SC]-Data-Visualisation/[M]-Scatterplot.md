## Scatterplot
### Base R Graphic
##### Actual Code
###### One Variable
```r
plot(mtcars$mpg, main = "Scatterplot for `mtcars$mpg`")
```
###### Two Variables
```r
plot(mtcars$wt, mtcars$mpg,
     main = "Scatterplot for `mtcars$mpg` on `mtcars$wt`")
```
### ggplot2 Graphic
###### Actual Code
###### One Variable
```r
qplot(seq_along(mtcars$mpg), mtcars$mpg) +
  labs(title = "Scatterplot for `mtcars$mpg`")
```
###### Two Variables
```r
ggplot(mtcars, aes(x=wt, y=mpg)) +
  geom_point() +
  labs(title = "Scatterplot for `mtcars$mpg` on `mtcars$wt`")
```
