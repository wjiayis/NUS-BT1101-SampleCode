### [HF] Prediction Interval
This helper function performs `transformTukey` if and only if it is required.
#### **_Sample Task: Compute the 95% prediction interval._**
**Actual Code**
1. Helper function. (Must be included. Do not edit.)
```
calculate.PredictionInterval.h <- function(dataset_variable, confidence.decimal, is_normal, normality.p_value.critical_value, normality.w_value.critical_value){

# Assess if transformation is required
if(is_normal == "TO BE DETERMINED"){
normality_test <- shapiro.test(dataset_variable)
is_normal <- ifelse(normality_test$p.value > normality.p_value.critical_value | normality_test$statistic > normality.w_value.critical_value, TRUE, FALSE)}

# No Transformation involved
if(is_normal){
m <- mean(dataset_variable)
sd <- sd(dataset_variable)

lPI <- m - (qt(((1-(1 - confidence.decimal)/2)),
       df = (length(dataset_variable)-1)) * sd * sqrt(1+1/length(dataset_variable)))
uPI <- m + (qt(((1-(1 - confidence.decimal)/2)),
       df = (length(dataset_variable)-1)) * sd * sqrt(1+1/length(dataset_variable)))

cbind(lPI, uPI) %>% print()}

# Transformation involved
if(!is_normal){
lambda <- transformTukey(dataset_variable, quiet = TRUE, plotit = FALSE, returnLambda = TRUE)
dataset_variable <- transformTukey(dataset_variable)
m <- mean(dataset_variable)
sd <- sd(dataset_variable)
  
lPI.t <- m - (qt(((1-(1 - confidence.decimal)/2)),
         df = (length(dataset_variable)-1)) * sd * sqrt(1+1/length(dataset_variable)))
uPI.t <- m + (qt(((1-(1 - confidence.decimal)/2)),
         df = (length(dataset_variable)-1)) * sd * sqrt(1+1/length(dataset_variable)))

cbind(lPI.t, uPI.t) %>% print()

if (lambda > 0){
  lPI <- lPI.t^(1/lambda)
  uPI <- uPI.t^(1/lambda)}

if (lambda == 0){
  lPI <- 10^lPI.t
  uPI <- 10^uPI.t}

if (lambda < 0){
  lPI <- (-1*lPI.t)^(1/lambda)
  uPI <-  (-1*uPI.t)^(1/lambda)}

output <- cbind(lPI, uPI)
rownames(output) <- NULL
print(output)}}
```
2. Hyperparameter. (Must be included. Edit only if the helper function is not producing the right output. Alert me if you have to edit this.)
```
calculate.PredictionInterval <- function(dataset_variable, confidence.decimal, is_normal = "TO BE CALCULATED"){calculate.PredictionInterval.h(dataset_variable, confidence.decimal, is_normal,
normality.p_value.critical_value = 0.05, normality.w_value.critical_value = 0.95)} 
```
3. **Inputs**. (Must be included. Edit this.)
```
calculate.PredictionInterval(mtcars$cyl, # dataset_variable
                             0.95) # confidence.decimal
```
4. Optional Arguments to override the helper function's test for normality. (If you wish to include it, edit the rhs of `=` and add them at the back of your input.)
```
#                             is_normal = "TO BE DETERMINED" ----- TRUE / FALSE
```
