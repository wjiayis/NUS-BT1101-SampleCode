## [ggplot2] ECDF plot
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
