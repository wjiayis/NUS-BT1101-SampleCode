## [HF] Pareto Analysis
###### Preparation Code
```r
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
R <- rdchem
```
###### Actual Code
1. Helper function. (Must be included. Do not edit.)
```r
calculate.ParetoAnalysis <- function(dataset_variable){
  pareto_analysis.descending_order <- sort(dataset_variable, decreasing = TRUE) # Sort variable in descending order
  pareto_analysis.descending_order.percentage <- pareto_analysis.descending_order / sum(pareto_analysis.descending_order) # Translate variable to percentage
  pareto_analysis.descending_order.percentage.cumulative <- cumsum(pareto_analysis.descending_order.percentage) # Compute relative percentage
  output <- which(pareto_analysis.descending_order.percentage.cumulative > 0.8)[1] %>% print()
  output.percentage <- glue::glue("{round((100*output/length(dataset_variable)),3)}%") %>% print()}
```
2. Inputs. (Must be included. Edit this.)
```r
calculate.ParetoAnalysis(R$rd)
```
