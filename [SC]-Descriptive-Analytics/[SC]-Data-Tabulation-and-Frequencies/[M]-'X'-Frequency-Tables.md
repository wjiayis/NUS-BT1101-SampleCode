## 'X' Frequency Tables
### Frequency Table
##### Sample Task 1
<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>

| ... | Discrete Variable | ... |
|:---:| :---: | :---: |
| ... | x | ... |
| ... | y | ... |
| ... | x | ... |
| ... | x | ... |
| ... | ... | ... |
</td><td>

| Discrete Variable | Frequency |
|:---:| :---: |
| x | ... |
| y | ... |
| ... | ... |
</td></tr> </table>

###### Preparation Code
```r
# Functions
library(dplyr)
library(knitr)

# Sample Data
library(vcd)
A <- Arthritis
```
###### Actual Code
Method 1 (used in latter parts)
```r
improvement.frequency_table <- A %>% group_by(Improved) %>% summarise(frequency = n())

kable(improvement.frequency_table, caption = "Frequency Table of Improvement",
      col.names = c("Improvement", "Frequency"))
```
Method 2
```r
improvement.frequency_table <- table(A$Improved) %>% as.data.frame()

kable(improvement.frequency_table, caption = "Frequency Table of Improvement",
      col.names = c("Improvement", "Frequency"))
```
<br><br>
##### Sample Task 2
<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>

| Discrete Variable | ... | Frequency |
|:---:| :---: | :---: |
| x | ... | ... |
| y | ... | ... |
| x | ... | ... |
| x | ... | ... |
| ... | ... | ... |
</td><td>

| Discrete Variable | Frequency |
|:---: | :---: |
| x | ... |
| y | ... |
| ... | ... |
</td></tr> </table>

###### Preparation Code
```r
# Functions
library(knitr)

# Sample Data
HEC <- as.data.frame(HairEyeColor)
```
###### Actual Code
```r
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)

kable(HEC, caption = "Frequency Table of Hair Colour",
      col.names = c("Hair Colour", "Frequency"))
```
<br><br>
##### Sample Task 3: Compute frequency of \[a continuous variable\]
###### Preparation Code
```r
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
R <- rdchem
```
###### Actual Code
Method 1
```r
rd.breaks <- seq(0, 1500, by = 100)
rd.cut <- cut(R$rd, rd.breaks, right = FALSE)
rd.frequency_table <- table(rd.cut) %>% transform()
rd.frequency_table
```
[Method 2: Histogram Frequency Table](../../[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md)

<br><br><br>
### Relative Frequency Table
##### Task

<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>
      
| Categories | Frequency |
|:---:| :---: |
| ... | ... |
</td><td>
      
| Categories | Frequency | Relative Frequency |
|:---:| :---: | :---: |
| ... | ... | ... |
</td></tr> </table>

###### Preparation Code
```r
# Functions
library(dplyr)
library(knitr)

# Sample Data
library(vcd)
A <- Arthritis
improvement.frequency_table <- A %>% group_by(Improved) %>% summarise(frequency = n()) # Obtain frequency table
```
###### Actual Code
```r
improvement.frequency_table$relative_frequency <- improvement.frequency_table$frequency/sum(improvement.frequency_table$frequency)

kable(improvement.frequency_table, caption = "Frequency Table of Improvement",
      col.names = c("Improvement", "Frequency", "Relative Frequency"))
```
<br><br><br>
### Cumulative Frequency and Cumulative Relative Frequency Table
##### Task
<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>
      
| Categories | Frequency |
|:---:| :---: |
| ... | ... |
</td><td>

| Categories | Frequency | Cumulative Frequency | Cumulative Relative Frequency |
|:---:| :---: | :---: | :---: |    
| ... | ... | ... | ... |
</td></tr> </table>

###### Preparation Code
```r
# Functions
library(dplyr)
library(knitr)

# Sample Data
library(vcd)
A <- Arthritis
improvement.frequency_table <- A %>% group_by(Improved) %>% summarise(frequency = n()) # Obtain frequency table
```
###### Actual Code
```r
improvement.frequency_table <- improvement.frequency_table %>% mutate(cumulative_frequency = cumsum(improvement.frequency_table$frequency),
       cumulative_relative_frequency = cumsum(improvement.frequency_table$frequency) / nrow(A))


kable(improvement.frequency_table, caption = "Frequency Table of Improvement", col.names = c("Improvement", "Frequency", "Cumulative Frequency", "Cumulative Relative Frequency"))
```
