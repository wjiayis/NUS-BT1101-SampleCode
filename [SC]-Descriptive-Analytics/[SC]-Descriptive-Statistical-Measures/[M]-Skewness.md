### Skewness
Preparation Code
```{r}
# Functions
library(psych)

# Sample Data
data(mtcars)
MC <- mtcars
```
**Actual Code**
```{r}
skew(MC$mpg)
```
