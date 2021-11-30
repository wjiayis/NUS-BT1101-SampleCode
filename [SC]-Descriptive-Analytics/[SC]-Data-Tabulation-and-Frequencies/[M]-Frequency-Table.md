#### **_Sample Task 2._**
<table>
<tr><th> FROM </th><th> TO </th></tr>
<tr><td>

| Discrete Variable | ... | Frequency |
|:---:| :---: | :---: |
| **x** | ... | ... |
| y | ... | ... |
| **x** | ... | ... |
| **x** | ... | ... |
</td><td>

| Discrete Variable | ... | Frequency |
|:---:| :---: | :---: |
| **x** | ... | ... |
| y | ... | ... |

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
