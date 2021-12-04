## [Base R] ECDF plot
###### Preparation Code
```
# Functions
library(ggplot2) # For ggplot2 graphic
```
###### Actual Code
###### Base R graphic
```
plot(ecdf(mtcars$mpg),
     main = "Cumulative Frequency of Miles/(US) gallon",
     xlab = "Miles/(US) gallon")
```
