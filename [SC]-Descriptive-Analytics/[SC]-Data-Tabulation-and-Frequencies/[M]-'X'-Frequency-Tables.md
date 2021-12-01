## 'X' Frequency Tables
### Frequency Table
#### **_Sample Task 1:_**
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

Preparation Code
```
# Functions
library(dplyr)
library(knitr)

# Sample Data
library(vcd)
data(Arthritis)
A <- Arthritis
```
\[M1\] **Actual Code** (used in latter data manipulation)
```
improvement.frequency_table <- A %>% group_by(Improved) %>% summarise(frequency = n())

kable(improvement.frequency_table, caption = "Frequency Table of Improvement",
      col.names = c("Improvement", "Frequency"))
```
\[M2\] **Actual Code**
```
improvement.frequency_table <- table(A$Improved) %>% as.data.frame()

kable(improvement.frequency_table, caption = "Frequency Table of Improvement",
      col.names = c("Improvement", "Frequency"))
```
#### **_Sample Task 2:_**
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

Preparation Code
```
# Functions
library(dplyr)
library(knitr)

# Sample Data
data(HairEyeColor)
HEC <- HairEyeColor %>% as.data.frame()
```
**Actual Code**
```
HEC <- HEC[c("Hair", "Freq")]
HEC <- aggregate(Freq~Hair, HEC, sum)

kable(HEC, caption = "Frequency Table of Hair Colour",
      col.names = c("Hair Colour", "Frequency"))
```
#### **_Sample Task 3: Continuous Variable_**
Preparation Code
```
# Functions
library(dplyr)

# Sample Data
library(wooldridge)
data(rdchem)
R <- rdchem
```
\[M1\] **Actual Code**
```
rd.breaks <- seq(0, 1500, by=100)
rd.cut <- cut(R$rd, rd.breaks, right=FALSE)
rd.frequency_table <- table(rd.cut) %>% transform()
rd.frequency_table
```
[\[M Histogram\]](../../[SC]-Data-Tabulation-and-Frequencies/[SC]-Descriptive-Analytics/[SC]-Data-Visualisation/[M]-Histogram-&-Frequency-Table.md)
### Relative Frequency Table
#### **_Task:_**

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

Preparation Code
```
# Functions
library(dplyr)
library(knitr)

# Sample Data
library(vcd)
data(Arthritis)
A <- Arthritis
improvement.frequency_table <- A %>% group_by(Improved) %>% summarise(frequency = n())
```
**Actual Code**
```
improvement.frequency_table$relative_frequency <- improvement.frequency_table$frequency/sum(improvement.frequency_table$frequency)

kable(improvement.frequency_table, caption = "Frequency Table of Improvement",
      col.names = c("Improvement", "Frequency", "Relative Frequency"))
```
### Cumulative Frequency and Cumulative Relative Frequency Table
#### **_Task:_**
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

Preparation Code
```
# Functions
library(dplyr)
library(knitr)

# Sample Data
library(vcd)
data(Arthritis)
A <- Arthritis
improvement.frequency_table <- A %>% group_by(Improved) %>% summarise(frequency = n())
```
**Actual Code**
```
improvement.frequency_table <- improvement.frequency_table %>% mutate(cumulative_frequency = cumsum(improvement.frequency_table$frequency),
       cumulative_relative_frequency = cumsum(improvement.frequency_table$frequency) / nrow(A))


kable(improvement.frequency_table, caption = "Frequency Table of Improvement", col.names = c("Improvement", "Frequency", "Cumulative Frequency", "Cumulative Relative Frequency"))
```
