## Variance
### Sample Variance
###### Actual Code
```
var(mtcars$mpg)
```
### \[If sample data is population data\] Population variance
###### Actual Code
```
var(mtcars$mpg)*(nrow(mtcars$mpg)-1)/nrow(mtcars$mpg)
```
