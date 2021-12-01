### Confidence Interval (Unknown Population sd)
: _white_heart_ : _Helper Function Available_
Preparation Code
```
library(Rmisc)
```
**Actual Code**
```
mpg.ci <- CI(mtcars$mpg, ci = 0.95)
mpg.ci <- cbind(mpg.ci[3],mpg.ci[1])
colnames(mpg.ci) <- c("lCI", "uCI")
rownames(mpg.ci) <- NULL
print(mpg.ci, digits = 4)
```
