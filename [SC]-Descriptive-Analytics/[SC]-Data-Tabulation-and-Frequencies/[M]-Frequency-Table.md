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

| Discrete Variable | ... | Frequency |
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
```
\[M1\]**Actual Code**
```
improvement.frequency_table <- A %>% group_by(Improved) %>% summarise(n())

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
