### Range
Preparation Code
```
# Sample Data
data(mtcars)
MC <- mtcars
```
**Actual Code**
```
range(MC$mpg) # Prints the interval
mpg.range <- max(MC$mpg) - min(MC$mpg)
mpg.range # Prints the size of the interval
```
