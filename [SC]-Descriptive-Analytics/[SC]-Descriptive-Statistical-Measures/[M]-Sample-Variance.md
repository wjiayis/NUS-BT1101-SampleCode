## Variance
### Sample Variance
###### Actual Code
```
var(mtcars$mpg)
```
### \[If sample data is population data\] Population variance
###### Actual Code
```
var(mtcars$mpg)*(nrow(mtcars)-1)/nrow(mtcars)
```
