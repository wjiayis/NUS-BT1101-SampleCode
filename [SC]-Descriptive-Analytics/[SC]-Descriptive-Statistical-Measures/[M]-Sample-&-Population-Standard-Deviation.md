## Standard Deviation
### Sample Standard Deviation
###### Actual Code
```
sd(mtcars$mpg)
```
### Population Standard Deviation
| Implicit Assumptions |
| :---: |
| :white_medium_square: Sample data is population data. |
###### Actual Code
```
var(mtcars$mpg)*(nrow(mtcars)-1)/nrow(mtcars)
```
