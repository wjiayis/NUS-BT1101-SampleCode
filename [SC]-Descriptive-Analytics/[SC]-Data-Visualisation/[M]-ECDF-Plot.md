## ECDF plot
</br>Preparation Code
```
# Functions
library(ggplot2) # For ggplot2 graphic
```
</br>**Actual Code**
###### Base R graphic
```
plot(ecdf(mtcars$mpg),
     main = "Cumulative Frequency of Miles/(US) gallon",
     xlab = "Miles/(US) gallon")
```
###### ggplot2 graphic
```
ggplot(mtcars, aes(mpg)) +
stat_ecdf(col="darkblue") +
labs(title="Cumulative Frequency of Miles/(US) gallon") +
ylab("Cumulative Frequency") +
xlab("Miles/(US) gallon")
```
