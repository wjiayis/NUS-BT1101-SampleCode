### Linear Optimisation
Preparation Code
```
# Functions
library(lpSolve)
```
###### Sample Task 1: Maximise Profits with the given constraints.
| Maximise total profit using decision variables</br>X<sub>1</sub> = volume of apple juice, X<sub>2</sub> = volume of orange juice | Profit = 11X<sub>1</sub> + 12X<sub>2</sub> |
|---|---|
| Budget Constraint | 0.1X<sub>1</sub> + 0.2X<sub>2</sub> ≤ 12 |
| Space Constraint | 1.1X<sub>1</sub> + 1.2X<sub>2</sub> ≤ 34|
| Contract Constraint 1 | X<sub>1</sub> ≥ 5 |
| Contract Constraint 2 | X<sub>2</sub> ≥ 5 |
| Non-negativity Constraint 1 | X<sub>1</sub> ≥ 0 |
| Non-negativity Constraint 2 | X<sub>2</sub> ≥ 0 |
**Actual Code**
1. Run the linear optimisation model.
```
objective.fn <- c(11, 22)

const.mat <- (matrix(
  c(0.1, 0.2,
    1.1, 1.2,
    1, 0,
    0, 1), # R assumes non-negativity, so the non-negativity constraint does not need to be specified
  ncol = 2, # number of decision variables
  byrow = TRUE))

const.dir <- c("<=","<=",">=",">=")

const.rhs <- c(12,34,5,5)

lp.solution <- lp("max", objective.fn, const.mat, const.dir, const.rhs, compute.sens=T)

lp.solution
lp.solution$solution
```
2. If required, obtain shadow prices.
```
lp.solution$duals
```
3. If required, conduct sensitivity analysis.
```
lp.solution$sens.coef.from
lp.solution$sens.coef.to
```
