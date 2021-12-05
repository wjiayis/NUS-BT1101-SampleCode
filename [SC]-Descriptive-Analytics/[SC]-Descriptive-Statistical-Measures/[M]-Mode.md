## Mode
:white_heart: [Helper Function Available](../../[SC]-Descriptive-Analytics/[SC]-Descriptive-Statistical-Measures/[HF]-Mode.md)
##### Actual Code
###### Sample Task
>Compute mode `mtcars$mpg`.
```
names(table(mtcars$mpg))[table(mtcars$mpg)==max(table(mtcars$mpg))]
```
