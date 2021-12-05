## ECDF plot
### Base R Graphic
###### Actual Code
```
plot(ecdf(mtcars$mpg),
     main = "Cumulative Frequency of Miles/(US) gallon",
     xlab = "Miles/(US) gallon")
```
### ggplot2 Graphic
###### Preparation Code
```
# Functions
library(ggplot2)
```
###### Actual Code
```
ggplot(mtcars, aes(mpg)) +
  stat_ecdf(col="darkblue") +
  labs(title="Cumulative Frequency of Miles/(US) gallon") +
  ylab("Cumulative Frequency") +
  xlab("Miles/(US) gallon")
```
