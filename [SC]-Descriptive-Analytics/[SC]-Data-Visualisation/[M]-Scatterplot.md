## Scatterplot
### Base R Graphic
##### Actual Code
###### One Variable
```
plot(mtcars$mpg, main="Scatterplot for `mtcars$mpg`")
```
###### Two Variables
```
plot(mtcars$wt, mtcars$mpg,
     main="Scatterplot for `mtcars$mpg` on `mtcars$wt`")
```
### ggplot Graphic
###### Actual Code
###### One Variable
```
qplot(seq_along(mtcars$mpg), mtcars$mpg) +
  labs(title="Scatterplot for `mtcars$mpg`")
```
###### Two Variables
```
ggplot(mtcars, aes(x=wt, y=mpg)) +
  geom_point() +
  labs(title="Scatterplot for `mtcars$mpg` on `mtcars$wt`")
```
