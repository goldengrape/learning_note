# Feature Importance特征的重要性

## Drop Column method

扔掉被测列的数据, 计算C-Index.

例如:

* C-Index_{BP, Age}=0.9
* C-Index_{Age}=0.85
* C-Index_{BP}=0.82

则

* Age的重要性=C-Index_{BP, Age} - C-Index_{BP}=0.9-0.82=0.08
* BP的重要性=C-Index_{BP, Age} - C-Index_{Age}=0.9-0.85=0.05


## Permutation method

随机置换被测Feature列的数据, 计算得到一个C-Index.

例如:

* C-Index_{BP,Age}=0.9, 
* C-Index_{BP,Shuffled Age}=0.7
* C-Index_{Shuffled BP, Age}=0.83

则:

* Age的重要性: C-Index_{BP,Age} - C-Index_{BP,Shuffled Age}=0.9-0.7=0.20
* BP的重要性: C-Index_{BP,Age} - C-Index_{Shuffled BP, Age}=0.9-0.83=0.07

## Importance to individual

个人化的特征重要性, 使用Drop Column method, 但训练后计算的是prediction f, 发生事件的概率. 

### Shapley Values

考虑feature之间存在相关性, 例如针对Age, dBP, sBP的关联, 要计算sBP的重要性, 分别计算与各个feature组合的情况, 与除外sBP的情况:

|                          |                     | 相减 |
| :----------------------- | :------------------ | :--- |
| f({Age, dBP, sBP})= 0.95 | f({Age, dBP})= 0.84 | 0.01 |
| f({dBP, sBP})= 0.98      | f({dBP})= 0.96      | 0.02 |
| f({Age, sBP})= 0.93      | f({Age})= 0.40      | 0.53 |
| f({sBP})= 0.94           | f({})= 0.10         | 0.84 |

考虑sBP依次加入到组合feature中的情况:

* 已经有{Age,dBP}, 加入sBP到末尾, 
  * {Age, dBP, sBP}: f({Age, dBP, sBP})-f({Age, dBP})=0.01
  * {dBP, Age, sBP}: f({Age, dBP, sBP})-f({Age, dBP})=0.01
* 已经有{Age,dBP}, 加入sBP到中间, 
  * {Age, sBP, dBP}: f({Age, sBP})-f({Age})=0.53
  * {dBP, sBP, Age}: f({dBP, sBP})-f({Age})=0.02
* 已经有{Age,dBP}, 加入sBP到最前,
  * {sBP, Age, dBP}: f({sBP})-f({})=0.84
  * {sBP, dBP, Age}: f({sBP})-f({})=0.84

Shapley Value I(sBP)=(0.01+0.01+0.53+0.02+0.84+0.84)/6=0.38
