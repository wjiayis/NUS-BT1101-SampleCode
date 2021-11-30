## 'X' Frequency Tables
### Frequency Table
#### **_Sample Task 1._**
<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>

| ... | Discrete Variable | ... |
|:---:| :---: | :---: |
| ... | x | ... |
| ... | y | ... |
| ... | x | ... |
| ... | x | ... |
</td><td>

| Discrete Variable | Frequency |
|:---:| :---: |
| x | ... |
| y | ... |

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
\[M1\] **Actual Code** (used for latter data manipulation)
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
#### **_Sample Task 2._**
<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>

| Discrete Variable | ... | Frequency |
|:---:| :---: | :---: |
| x | ... | ... |
| y | ... | ... |
| x | ... | ... |
| x | ... | ... |
</td><td>

| Discrete Variable | Frequency |
|:---: | :---: |
| x | ... |
| y | ... |

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
### Relative Frequency Table
#### **_Task._**

<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>
      
| Discrete Variable | Frequency |
|:---:| :---: |
| x | ... |
| y | ... |
</td><td>
      
| Discrete Variable | Frequency | Relative Frequency |
|:---:| :---: | :---: |
| x | ... | ... |
| y | ... | ... |

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

kable(improvement.frequency_table, caption = "Relative Frequency Table of Improvement",
      col.names = c("Improvement", "Frequency", "Relative Frequency"))
```
### Cumulative Relative Frequency Table
