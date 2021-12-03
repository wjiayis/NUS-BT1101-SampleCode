### \[HF\] Assessment of Classification
Preparation Code
```
# Functions
library(dplyr)
library(glue)
```
**Actual Code**
1. Helper function. (Must be included. Do not edit.)
```
calculate.Performance <- function(TP, TN, FP, FN){
classification_accuracy <- (TP + TN) / (TP + FP + TN + FN)
glue::glue("Classification accuracy = {round(classification_accuracy * 100, 1)}% (3s.f.)") %>% print()

precision <- TP / (TP + FP)
glue::glue("Precision = {round(precision * 100, 1)}% (3s.f.)") %>% print()

recall <- TP / (TP + FN)
glue::glue("Recall = {round(recall * 100, 1)}% (3s.f.)") %>% print()

f_score <- (2*precision*recall)/(precision+recall)
glue::glue("F-score = {round(f_score * 100, 1)}% (3s.f.)") %>% print()}
```
2. **Inputs**. (Must be included. Edit this.)
```
calculate.Performance(9, # TP ----- True Positive; 1 Actual 1 Predicted
                      2016, # TN ----- True Negative; 0 Actual 0 Predicted
                      8, # FP ----- False Positive; 0 Actual 1 Predicted
                      61) # FN ----- False Negative; 1 Actual 0 Predicted
```
