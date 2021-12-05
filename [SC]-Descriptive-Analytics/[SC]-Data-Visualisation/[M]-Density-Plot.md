## Density Plot
### Base R Graphic
###### Actual Code
```
plot(density(mtcars$mpg),
     main = "Density Plot of Miles/(US) gallon")
```
### ggplot2 Graphic
###### Preparation Code
```
library(ggplot2)
```
###### Actual Code
```
ggplot(mtcars, aes(mpg))+
        geom_density() +
        labs(title="Density Plot of Miles/(US) gallon")
```
