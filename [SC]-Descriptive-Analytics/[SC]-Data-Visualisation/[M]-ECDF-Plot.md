## ECDF plot
</br>Preparation Code
```
# Sample Data
MC <- mtcars
```
</br>**Actual Code**
###### Base R graphic
```
plot(ecdf(MC$mpg),
     main = "Cumulative Frequency of Miles/(US) gallon",
     xlab = "Miles/(US) gallon")
```
###### ggplot2 graphic
