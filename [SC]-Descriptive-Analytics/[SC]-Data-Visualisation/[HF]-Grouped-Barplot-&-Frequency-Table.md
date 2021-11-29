### [HF] Grouped Barplot
Preparation Code
```
# Functions
library(dplyr)
library(knitr)
library(glue)
# Data for Sample Inputs
library(wooldridge)
data(mathpnl)
M <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993", ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>% summarise(Satisfaction.Grade_4 = mean(math4, na.rm=TRUE), Satisfaction.Grade_7 = mean(math7, na.rm=TRUE))
```
**Actual Code**
1. Helper function. Do not edit.
  - You must include this code to use the helper function.
```
plot.GroupedBarplot.h <- function(data_df, title.text, y_variable.text, title.font_size, categories.font_size, value_labels.font_size, legend.font_size, possible_colours, legend.position, barplot.axis_range.multiplication_constant, include_frequency_table){
  
grouped_barplot.matrix <- data_df %>% select(-1) %>% as.matrix() %>% t()

if(include_frequency_table){kable(data_df, caption = glue::glue("Table of {title.text}")) %>% print()}

grouped_barplot <- barplot(grouped_barplot.matrix,
        beside = TRUE,
        ylim = c(0, max(grouped_barplot.matrix)*barplot.axis_range.multiplication_constant),
        names.arg = data_df[[1]],
        main = glue::glue("Grouped Barplot of {title.text}"),
        ylab = glue::glue("{y_variable.text}"),
        cex.main = title.font_size,
        cex.names = categories.font_size,
        col = possible_colours[1:ncol(data_df)-1])

if(legend.position == "PRESET"){
legend.position <- ifelse(max(grouped_barplot.matrix[,1]) > max(grouped_barplot.matrix[,-1]), "topright", "topleft")}
legend(legend.position,
       fill = possible_colours[1:ncol(data_df)-1],
       colnames(data_df)[2:ncol(data_df)],
       cex = legend.font_size)

text(y = grouped_barplot.matrix, x = grouped_barplot, label = round(grouped_barplot.matrix,2), pos = 3, cex = value_labels.font_size)}
```
2. Hyperparameter. Edit only if helper function is not producing the right output. Alert me if you have to edit this.
  - You must include this code to use the helper function.
```
plot.GroupedBarplot <- function(data_df, title.text, y_variable.text, title.font_size = 1, categories.font_size = 1, value_labels.font_size = 1, legend.font_size = 1, possible_colours = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1", "darkolivegreen2"), legend.position = "PRESET", include_frequency_table = TRUE)
{plot.GroupedBarplot.h(data_df, title.text, y_variable.text, title.font_size, categories.font_size, value_labels.font_size, legend.font_size, possible_colours, legend.position, include_frequency_table,
                              barplot.axis_range.multiplication_constant = 1.2)}
```
**3. Sample Input. Edit this.**
  - You must include this code to use the helper function.
```
plot.GroupedBarplot(M, # data_df
                           "Mean Satisfaction for Math, By Year of Graduation", # title.text
                           "Mean Satisfaction") # y_variable.text
```
4. Optional Arguments (for fine-tuning of output). If you wish to include some of these keyword arguments, edit what is on the right of the `=` and add them at the back of your input.
```
#                           title.font_size = 1
#                           categories.font_size = 1
#                           value_labels.font_size = 1
#                           legend.font_size = 1
#                           possible_colours = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1", "darkolivegreen2")
#                           legend.position = " PRESET" ----- e.g., "PRESET" / list(x = 1, y = 70)
#                           include_frequency_table = TRUE
```
Additional Notes:
1. Structure of data frame `data_df`

| Discrete Variable* | Continuous Variable 1* | Continuous Variable 2* | ... | 
| :---: | :---: | :---: | :---: |
| ... | ... | ... | ... |

\*Variable Name as Column Name
