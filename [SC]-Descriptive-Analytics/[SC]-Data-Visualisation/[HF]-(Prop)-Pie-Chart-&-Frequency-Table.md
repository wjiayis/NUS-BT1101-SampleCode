### [HF] Pie Chart for Proportion
Preparation Code
```
# Functions
library(dplyr)
library(knitr)
library(glue)

# Sample Data
data(HairEyeColor)
HEC <- HairEyeColor %>% as.data.frame()
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)
```
**Actual Code**
1. Set {r ..., results="asis", ...}
2. Helper function. (Must be included. Do not edit.)
```
plot.PieChart.Proportion <- function(data_df, subject.text, title.font_size = 1, possible_colours = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1", "darkolivegreen2"), include_frequency_table = TRUE){

# Frequency Table
if(include_frequency_table){
kable(data_df, caption = glue::glue("Frequency of {subject.text}"),
      col.name = c(glue::glue("{subject.text}"), "Frequency")) %>% print()}

# Graph
pie(data_df[[2]],
    labels = glue::glue("{data_df[[1]]}, {round(100 * data_df[[2]]/sum(data_df[[2]]),2)}%"),
    col = possible_colours,
    main = glue::glue("Pie Chart of {subject.text}"),
    cex.main = title.font_size)}
```
3. **Inputs**. (Must be included. Edit this.)
```
plot.PieChart.Proportion(HEC, # data_df
              "Hair Colour") # subject.text
```
4. Optional Keyword Arguments for Fine-tuning of Output. (If you wish to include some of these, edit the rhs of = and add them at the back of your input.)
```
#              title.font_size = 1
#              possible_colours = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1", "darkolivegreen2")
#              include_frequency_table = TRUE
```
Additional Notes:
1. The default palette can support up to 5 slices. If more slices are to be plotted, you must input `possible_colours`.
2. Structure of data frame `data_df`

| Discrete Variable* | Continuous Variable |
| :---: | :---: |
| ... | ... |

\*Variable Name as Column Name
