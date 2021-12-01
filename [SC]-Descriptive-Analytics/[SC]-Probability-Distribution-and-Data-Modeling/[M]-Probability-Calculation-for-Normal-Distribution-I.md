### Normal, Mean, Standard Deviation &#8594; Probability for A Single Observation
#### **_Sample Task 1:</br>The distribution for customer demand (units per month) is normal with mean = 750 and standard deviation = 100.</br>Find the probability that demand will be at most 900 units/month._**
**Actual Code**
```
pnorm(900, 750, 100)
```
#### **_Sample Task 2:</br>The distribution for customer demand (units per month) is normal with mean = 750 and standard deviation = 100.</br>Find the probability that demand will exceed 700 units/month._**
\[M1\] **Actual Code**
```
1 - pnorm(700, 750, 100)
```
\[M2\] **Actual Code**
```
pnorm(700, 750, 100, lower.tail = FALSE)
```
#### **_Sample Task 3:</br>The distribution for customer demand (units per month) is normal with mean = 750 and standard deviation = 100.</br>Find the probability that demand will be between 700 and 900 units/month._**
**Actual Code**
```
pnorm(900, 750, 100) - pnorm(700, 750, 100)
```
