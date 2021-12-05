## \[HF\]\[Base R\] Histogram
###### Preparation Code
```
# Functions
library(dplyr)
library(knitr)
library(glue)

# Sample Data
library(wooldridge)
CS <- ceosal1 %>% filter(salary < 1000)
```
###### Actual Code
1. Set `{r ..., results="asis", ...}`.
2. Helper function. (Must be included. Do not edit.)
```
plot.Histogram.h <- function(dataset_variable, variable.text_singular, subject.text_plural, histogram.bins, histogram.colour, frequency_table.bins.upper_bound, include_frequency_table, histogram.range_of_y_values.multiplication_constant){

# Graph (1/2)
histogram <- function(histogram.y_axis_range, is_plotted){
  hist(dataset_variable,
       breaks = histogram.bins,
       ylim = histogram.y_axis_range,
       main = glue::glue("Histogram of {subject.text_plural}' {variable.text_singular}"),
       xlab = glue::glue("{variable.text_singular}"),
       ylab = glue::glue("Number of {subject.text_plural}"),
       labels = TRUE,
       plot = is_plotted,
       col = histogram.colour)}

# Frequency Table
frequency_table <- cut(dataset_variable, invisible(histogram(NULL, FALSE))$breaks, include.lowest = TRUE, right = frequency_table.bins.upper_bound) %>% table() 

if(include_frequency_table){
kable(frequency_table, caption = glue::glue("Frequency Distribution of {subject.text_plural}' {variable.text_singular}"),
    col.names = c(glue::glue("{subject.text_plural}' {variable.text_singular} (grouped)"), "Frequency")) %>% print()}

# Graph (2/2)
histogram(c(0,max(frequency_table)*histogram.range_of_y_values.multiplication_constant), TRUE)}
```
3. Hyperparameter. (Must be included. Edit only if the helper function is not producing the right output. Alert me if you have to edit this.)
```
plot.Histogram <- function(dataset_variable, variable.text_singular, subject.text_plural, histogram.bins = "Sturges", histogram.colour = "pink", frequency_table.bins.upper_bound = FALSE, include_frequency_table = TRUE)
  {plot.Histogram.h(dataset_variable, variable.text_singular, subject.text_plural, histogram.bins, histogram.colour, frequency_table.bins.upper_bound, include_frequency_table,
  histogram.range_of_y_values.multiplication_constant = 1.2)}
```
4. Inputs. (Must be included. Edit this.)
```
plot.Histogram(CS$salary, # dataset_variable
               "Salary", # variable.text_singular ----- "Histogram of {subject.text_plural}' {variable.text_singular}"
               "CEOs") # subject.text_plural ----- "Histogram of {subject.text_plural}' {variable.text_singular}"
```
5. Optional keyword arguments for fine-tuning of output. (If you wish to include some of these, edit the rhs of `=` and add them at the back of your input.)
```
#               histogram.bins = "Sturges" # ----- e.g., "Sturges" / 6
#               histogram.colour = "pink"
#               frequency_table.bins.upper_bound = TRUE
#               include_frequency_table = TRUE
```
