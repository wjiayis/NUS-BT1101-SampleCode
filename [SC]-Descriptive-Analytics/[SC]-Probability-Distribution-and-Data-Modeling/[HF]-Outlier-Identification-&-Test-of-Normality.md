### \[HF\] Outlier Identification and Test of Normality
Preparation Code
```
# Functions
library(dplyr)
library(glue)

# Sample Data
library(wooldridge)
G <- gpa2
```
**Actual Code**
1. Helper function. (Must be included. Do not edit.)
```
test.NormalityOutliers <- function(dataset_variable, variable.text, density_plot.remove_na = TRUE){
# Test of normality
shapiro.test(dataset_variable) %>% print()
hist(dataset_variable, main = glue::glue("Histogram to Assess if {variable.text} is Normally Distributed"))
plot(density(dataset_variable, na.rm = density_plot.remove_na), main = glue::glue("Scatterplot to Assess if {variable.text} is Normally Distributed"))
qqnorm(dataset_variable,  main = glue::glue("qq-Plot to Assess if {variable.text} is Normally Distributed"))
qqline(dataset_variable, col = 2)
# Outlier Identification
boxplot(dataset_variable, range = 3, main = glue::glue("Boxplot to Examine Distribution of Extreme Outliers"))
boxplot(dataset_variable, range = 1.5, main = glue::glue("Boxplot to Examine Distribution of Moderate Outliers"))}
```
2. **Inputs**. (Must be included. Edit this.)
```
test.NormalityOutliers(G$sat, # dataset_variable
               "SAT score") # variable.text
```
3. Optional Keyword Arguments for Fine-tuning of Output. (If you wish to include some of these, edit the rhs of `=` and add them at the back of your input.)
```
#               density_plot.remove_na = TRUE
```
