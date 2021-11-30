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
### Graphical Methods
1. Density Plot
2. Histogram
  - _Helper Function_  
4. Q-Q Plot
