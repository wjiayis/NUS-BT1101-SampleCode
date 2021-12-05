## Chebyshev’s Theorem & Empirical Rule
### Chebyshev’s Theorem
##### Sample Task 1.1
>Using Chebyshev’s Theorem, obtain an interval in which lies at least 75% of the data.
###### Actual Code
```
m <- mtcars$mpg
m.lower_bound <- mean(m) - 2*sd(m)
m.upper_bound <- mean(m) + 2*sd(m)
#(length(m[m > m.lower_bound & m < m.upper_bound])) / length(m) # For verification (in fact, 93% of data lie within this interval)
```
##### Sample Task 1.2
>Using Chebyshev’s Theorem, obtain an interval in which lies at least 89% of the data.
###### Actual Code
```
m <- mtcars$mpg
m.lower_bound <- mean(m) - 3*sd(m)
m.upper_bound <- mean(m) + 3*sd(m)
# (length(m[m > m.lower_bound & m < m.upper_bound])) / length(m) # For verification (in fact, 100% of data lie within this interval)
```
### Empirical Rule
##### Sample Task 2.1
>Using empirical rule, obtain an interval in which lies at least 68% of the data.
###### Actual Code
```
m <- mtcars$mpg
m.lower_bound <- mean(m) - sd(m)
m.upper_bound <- mean(m) + sd(m)
# (length(m[m > m.lower_bound & m < m.upper_bound])) / length(m) # For verification (in fact, 75% of data lie within this interval)
```
##### Sample Task 2.2

>Using empirical rule, obtain an interval in which lies at least 95% of the data.
###### Actual Code
```
m <- mtcars$mpg
m.lower_bound <- mean(m) - 2*sd(m)
m.upper_bound <- mean(m) + 2*sd(m)
# (length(m[m > m.lower_bound & m < m.upper_bound])) / length(m) # For verification (in fact, 93% of data lie within this interval)
```
##### Sample Task 2.3
>Using empirical rule, obtain an interval in which lies at least 99.7% of the data.
###### Actual Code
```
m <- mtcars$mpg
m.lower_bound <- mean(m) - 3*sd(m)
m.upper_bound <- mean(m) + 3*sd(m)
# (length(m[m > m.lower_bound & m < m.upper_bound])) / length(m) # For verification (in fact, 100% of data lie within this interval)
```
