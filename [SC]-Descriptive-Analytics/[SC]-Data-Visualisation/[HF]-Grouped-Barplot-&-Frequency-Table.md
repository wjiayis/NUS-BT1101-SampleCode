### [HF] Grouped Barplot
Preparation Code
```
# Functions
library(dplyr)
library(knitr)
library(glue)

# Sample Data
library(wooldridge)
M <- mathpnl %>% select(c(math4, math7, y92, y93, y94, y95))
M$Year <- ifelse(M$y92 == 1, "1992", ifelse(M$y93 == 1, "1993", ifelse(M$y94 == 1, "1994", ifelse(M$y95 == 1, "1995", NA))))
M <- M %>% filter(!is.na(Year)) %>% select(math4, math7, Year) %>% group_by(Year) %>% summarise(Satisfaction.Grade_4 = mean(math4, na.rm=TRUE), Satisfaction.Grade_7 = mean(math7, na.rm=TRUE))
```
**Actual Code**
1. Set `{r ..., results="asis", ...}`.
2. Helper function. (Must be included. Do not edit.)
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
3. Hyperparameter. (Must be included. Edit only if the helper function is not producing the right output. Alert me if you have to edit this.)
```
plot.GroupedBarplot <- function(data_df, title.text, y_variable.text, title.font_size = 1, categories.font_size = 1, value_labels.font_size = 1, legend.font_size = 1, possible_colours = c("plum2", "lightgoldenrod1", "pink", "lightsteelblue1", "darkolivegreen2"), legend.position = "PRESET", include_frequency_table = TRUE)
{plot.GroupedBarplot.h(data_df, title.text, y_variable.text, title.font_size, categories.font_size, value_labels.font_size, legend.font_size, possible_colours, legend.position, include_frequency_table,
                              barplot.axis_range.multiplication_constant = 1.2)}
```
4. **Inputs**. (Must be included. Edit this.)
```
plot.GroupedBarplot(M, # data_df
                           "Mean Satisfaction for Math, By Year of Graduation", # title.text
                           "Mean Satisfaction") # y_variable.text
```
5. Optional keyword arguments for fine-tuning of output. (If you wish to include some of these, edit the rhs of `=` and add them at the back of your input.)
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

| Discrete Variable[^1] | Continuous Variable 1[^1] | Continuous Variable 2[^1] | ... | 
| :---: | :---: | :---: | :---: |
| ... | ... | ... | ... |

[^1]: Variable name as column name
