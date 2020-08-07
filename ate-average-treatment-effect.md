# ATE Average Treatment Effect

平均治疗效果

使用: Neyman-Rubin causal model

定义: 

* Y_i(1): 第i个病人给予了治疗
  * Y_i(1)=1 : 该病人发生了事件(如心梗)
  * Y_i(1)=0 : 该病人没有发生事件
* Y_i(0): 第i个病人没有给予治疗, 或给了对照
  * Y_i(0)=1 : 该病人发生了事件(如心梗)
  * Y_i(0)=0 : 该病人没有发生事件
* Y_i(1)-Y_i(0) : 治疗是否有益

|i | Y_i(1)| Y_i(0)|Y_i(1)-Y_i(0)|
|:--|:--|:--|:--|
|1|0|1|-1|
|2|1|1|0|
|3|1|0|1|
|4|0|0|0|

计算mean, 可以得到平均治疗效果(Average Treatment Effect, *ATE*):

<!-- $$
E[Y_i(1)-Y_i(0)] = E[Y_i(1)] - E[Y_i(0)]
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=E%5BY_i(1)-Y_i(0)%5D%20%3D%20E%5BY_i(1)%5D%20-%20E%5BY_i(0)%5D"></div>

但实际上, 不能同时得到Y_i(1)和Y_i(0), 设W_i=是否给予治疗

|i |W_i| Y_i(1)| Y_i(0)|Y_i(1)-Y_i(0)|
|:--|:--|:--|:--|:--|
|1|1|a_1|?|?|
|2|0|?|b_2|?|
|3|0|?|b_3|?|
|4|1|a_4|0|?|

按W_i=1/0拆分表格:

|i |W_i| Y_i| 
|:--|:--|:--|
|1|1|a_1|
|4|1|a_4|
|mean||(a_1+a_4)/2|

|i |W_i| Y_i| 
|:--|:--|:--|
|2|0|b_2|
|3|0|b_3|
|mean||(b_2+b_3)/2|

<!-- $$
E[Y_i(1)-Y_i(0)] = E[Y_i| W_i=1] - E[Y_i|W_i=0]
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=E%5BY_i(1)-Y_i(0)%5D%20%3D%20E%5BY_i%7C%20W_i%3D1%5D%20-%20E%5BY_i%7CW_i%3D0%5D"></div>
当随机均匀分配时, W_i=1,W_i=0数量相等, 
<!-- $$
E[Y_i(1)-Y_i(0)] = (a_1+a_4)/2 - (b_2+b_3)/2
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=E%5BY_i(1)-Y_i(0)%5D%20%3D%20(a_1%2Ba_4)%2F2%20-%20(b_2%2Bb_3)%2F2"></div>
