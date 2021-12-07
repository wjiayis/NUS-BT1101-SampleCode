## Density Plot
### Base R Graphic
###### Actual Code
```r
plot(density(mtcars$mpg),
     main = "Density Plot of Miles/(US) gallon")
```
### ggplot2 Graphic
###### Preparation Code
```r
library(ggplot2)
```
###### Actual Code
```r
ggplot(mtcars, aes(mpg))+
      geom_density() +
      labs(title = "Density Plot of Miles/(US) gallon")
```
