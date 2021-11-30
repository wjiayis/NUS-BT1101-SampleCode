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
1. [Density Plot]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Density-Plot.md) (LINK NOT WORKING)
2. [Histogram]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md) (LINK NOT WORKING)
   - [_Helper Function_]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[HF]-Histogram-&-Frequency-Table.md) (LINK NOT WORKING)
4. [Q-Q Plot]([SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Q-Q-Plot.md) (LINK NOT WORKING)
[^1]: You should include the Shapiro-wilk test and at least one of the graphical methods.
