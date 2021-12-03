### Normal Distribution, Mean, Standard Deviation &#8594; Probability for A Single New Observation


</br>**Actual Code**
###### Sample Task 1:
>The distribution for customer demand (units per month) is normal with mean = 750 and standard deviation = 100.</br>Find the probability that demand will be at most 900 units/month.
```
pnorm(900, 750, 100)
```
###### Sample Task 2:
>The distribution for customer demand (units per month) is normal with mean = 750 and standard deviation = 100.</br>Find the probability that demand will exceed 700 units/month.

Method 1
```
1 - pnorm(700, 750, 100)
```
Method 2
```
pnorm(700, 750, 100, lower.tail = FALSE)
```
###### Sample Task 3:
>The distribution for customer demand (units per month) is normal with mean = 750 and standard deviation = 100.</br>Find the probability that demand will be between 700 and 900 units/month.
```
pnorm(900, 750, 100) - pnorm(700, 750, 100)
```
