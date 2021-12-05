## Q-Q Plot
### Base R Graphic
###### Preparation Code
```
# Sample Data
MC <- mtcars
```
###### Actual Code
```
qqnorm(MC$mpg, main = "Q-Q Plot of Miles/(US) gallon")
qqline(MC$mpg, col=2)
```
