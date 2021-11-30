## Test of Normality
### Shapiro-wilk test[^1]
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
### Graphical Methods[^1]
1. Density Plot
2. [Histogram]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md)
 - [_Helper Function_]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Histogram-&-Frequency-Table.md)  
4. Q-Q Plot
[^1]: You should include the Shapiro-wilk test and at least one of the graphical methods.
