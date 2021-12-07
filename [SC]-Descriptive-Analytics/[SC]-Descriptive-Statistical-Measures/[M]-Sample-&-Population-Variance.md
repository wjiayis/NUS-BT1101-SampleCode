## Variance
### Sample Variance
###### Actual Code
```r
var(mtcars$mpg)
```
### Population variance
| Implicit Assumptions |
| :---: |
| :white_medium_square: Sample data is population data. |
###### Actual Code
```r
var(mtcars$mpg)*(nrow(mtcars)-1)/nrow(mtcars)
```
