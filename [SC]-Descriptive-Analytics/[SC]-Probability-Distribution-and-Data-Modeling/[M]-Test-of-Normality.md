## Test of Normality
### Shapiro-wilk test
Preparation Code
```
# Sample Data
data(mtcars)
MC <- mtcars
```
**Actual Code**
```
shapiro.test(MC$mpg)
```
