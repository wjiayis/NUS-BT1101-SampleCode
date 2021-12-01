## Test of Normality
:white_heart: [_Helper Function Available_](../../[SC]-Descriptive-Analytics/[SC]-Probability-Distribution-and-Data-Modeling/[HF]-Outlier-Identification-and-Test-of-Normality.md)

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
1. [Density Plot](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Density-Plot.md)
2. [Histogram]../../([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md)
3. [Q-Q Plot](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Q-Q-Plot.md)
[^1]: You should include the Shapiro-wilk test and at least one of the graphical methods.
