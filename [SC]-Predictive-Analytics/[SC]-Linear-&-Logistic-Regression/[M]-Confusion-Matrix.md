## Confusion Matrix
###### Preparation Code
```
# Functions
library(dplyr)

# Sample Data
M_train <- mtcars %>% filter(mpg <= 24)
M_test <- mtcars %>% filter(mpg > 24)
fit <- glm(am ~ mpg + cyl, family="binomial", M_train) # am is binary, mpg and cyl are continuous
```
###### Actual Code
```
```
M_test$predicted_probability <- predict(fit, M_test, type="response")

M_test$predicted <- factor(    # make factor for labels
  round(M_test$predicted_probability),
  levels = c(0,1),
  labels = c("0_predict","1_predict"))

table(M_test$am, M_test$predicted) 
