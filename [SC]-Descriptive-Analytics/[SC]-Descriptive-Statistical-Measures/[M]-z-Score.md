### z-Score
Preparation Code
```
# Sample Data
data(mtcars)
MC <- mtcars
```
**Actual Code**
```
MC$mpg_z_score <- MC$mpg - mean(MC$mpg)
MC$mpg_z_score
```
