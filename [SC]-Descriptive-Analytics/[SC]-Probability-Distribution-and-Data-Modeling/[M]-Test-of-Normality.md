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
2. [Histogram]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md)
  - [_Helper Function_]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Histogram-&-Frequency-Table.md)  
4. Q-Q Plot
