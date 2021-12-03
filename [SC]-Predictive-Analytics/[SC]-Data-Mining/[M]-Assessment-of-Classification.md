## Assessment of Classification
:white_heart: [_Helper Function Available_](../../[SC]-Predictive-Analytics/[SC]-Data-Mining/[HF]-Assessment-of-Classification.md)
### Classification Accuracy
**Actual Code**
```
true_positive <- 1
true_negative <- 2
false_positive <- 3
false_negative <- 4
classification_accuracy <- (true_positive + true_negative) / (true_positive + true_negative + false_positive + false_negative)
classification_accuracy
```
### Precision
**Actual Code**
```
true_positive <- 1
false_positive <- 3
precision <- true_positive / (true_positive + false_positive)
precision
```
### Recall
**Actual Code**
```
true_positive <- 1
false_negative <- 4
recall <- true_positive / (true_positive + false_negative)
```
### F-score
**Actual Code**
```
true_positive <- 1
false_positive <- 3
false_negative <- 4
precision <- true_positive / (true_positive + false_positive)
recall <- true_positive / (true_positive + false_negative)
f_score <- (2*precision*recall)/(precision+recall)
f_score
```
