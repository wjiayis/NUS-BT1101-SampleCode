## Variance
### Sample Variance
###### Actual Code
```
var(mtcars$mpg)
```
### Population variance
| Implicit Assumptions |
| :---: |
| :white_medium_square: Sample data is population data. |
###### Actual Code
```
var(mtcars$mpg)*(nrow(mtcars)-1)/nrow(mtcars)
```
