## Integer Optimisation
##### Sample Task 1
>Maximise profits with the given constraints.
<details open>
  <summary></summary>
  
| Maximise total profit using decision variables</br>X<sub>1</sub> = number of apples to sell, X<sub>2</sub> = whether to sell one orange or not | Profit = 11X<sub>1</sub> + 12X<sub>2</sub> |
|---|---|
| Budget Constraint | 0.1X<sub>1</sub> + 0.2X<sub>2</sub> ≤ 12 |
| Space Constraint | 1.1X<sub>1</sub> + 1.2X<sub>2</sub> ≤ 34|
| Contract Constraint (X<sub>1</sub>) | X<sub>1</sub> ≥ 5 |
| Non-negativity Constraint (X<sub>1</sub>) | X<sub>1</sub> ≥ 0 |
| Non-negativity Constraint (X<sub>2</sub>) | X<sub>2</sub> ≥ 0 |
| Integer Constraint (X<sub>1</sub>) | X<sub>1</sub> is an integer |
| Binding Constraint (X<sub>2</sub>) | X<sub>2</sub> is binary |

</details>

###### Preparation Code
```
# Functions
library(lpSolve)
```
###### Actual Code
1. Run the integer optimisation model.
```
# Define parameters
objective.fn <- c(11, 22)

const.mat <- (matrix(
  c(0.1, 0.2,
    1.1, 1.2,
    1, 0), # R assumes non-negativity, so the non-negativity constraint does not need to be specified
  ncol = 2, # Number of decision variables
  byrow = TRUE))

const.dir <- c("<=","<=",">=")

const.rhs <- c(12,34,5)

# Run the model
lp.solution <- lp("max", objective.fn, const.mat, const.dir, const.rhs, int.vec = 1, binary.vec = 2, compute.sens=FALSE)

lp.solution
lp.solution$solution
```
2. If required, obtain shadow prices.
```
lp.solution$duals
```
3. If required, conduct sensitivity analysis.
```
lp.solution$sens.coef.to # Upper bounds to the coefficients
lp.solution$sens.coef.from # Lower bounds to the coefficients
```
</br></br></br>
##### Sample Task 2
>Minimise costs with the given constraints.
<details open>
  <summary></summary>

| Minimise total cost using decision variables</br>X<sub>1</sub> = number of apples to sell, X<sub>2</sub> = whether to sell one orange or not | Cost = 11X<sub>1</sub> + 12X<sub>2</sub> |
|---|---|
| Budget Constraint | 0.1X<sub>1</sub> + 0.2X<sub>2</sub> ≤ 12 |
| Space Constraint | 1.1X<sub>1</sub> + 1.2X<sub>2</sub> ≤ 34|
| Contract Constraint (X<sub>1</sub>) | X<sub>1</sub> ≥ 5 |
| Non-negativity Constraint (X<sub>1</sub>) | X<sub>1</sub> ≥ 0 |
| Non-negativity Constraint (X<sub>2</sub>) | X<sub>2</sub> ≥ 0 |
| Integer Constraint (X<sub>1</sub>) | X<sub>1</sub> is an integer |
| Binding Constraint (X<sub>2</sub>) | X<sub>2</sub> is binary |

</details>

###### Preparation Code
```
# Functions
library(lpSolve)
```
###### Actual Code
1. Run the integer optimisation model.
```
# Define parameters
objective.fn <- c(11, 22)

const.mat <- (matrix(
  c(0.1, 0.2,
    1.1, 1.2,
    1, 0), # R assumes non-negativity, so the non-negativity constraint does not need to be specified
  ncol = 2, # Number of decision variables
  byrow = TRUE))

const.dir <- c("<=","<=",">=")

const.rhs <- c(12,34,5)

# Run the model
lp.solution <- lp("min", objective.fn, const.mat, const.dir, const.rhs, int.vec = 1, binary.vec = 2, compute.sens=FALSE)

lp.solution
lp.solution$solution
```
2. If required, obtain shadow prices.
```
lp.solution$duals
```
3. If required, conduct sensitivity analysis.
```
lp.solution$sens.coef.to # Upper bounds to the coefficients
lp.solution$sens.coef.from # Lower bounds to the coefficients
```
