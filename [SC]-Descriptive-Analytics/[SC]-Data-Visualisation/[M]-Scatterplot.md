## Scatterplot
### Base R Graphic
##### Actual Code
###### One Variable
```
plot(mtcars$mpg)
```
###### Two Variables
```
plot(mtcars$wt, mtcars$mpg)
```
### ggplot Graphic
###### Actual Code
###### One Variable
```
qplot(seq_along(mtcars$mpg), mtcars$mpg)
```
###### Two Variables
```
ggplot(mtcars, aes(x=wt, y=mpg)) +
  geom_point()
```
