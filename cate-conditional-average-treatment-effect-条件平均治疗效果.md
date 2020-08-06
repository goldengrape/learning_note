# CATE (Conditional Average Treatment Effect, 条件平均治疗效果)

通过条件平均治疗效果可以得到个人治疗效果ITE. 

给定条件X=x时, 计算
<!-- $$
E[Y_i(1)-Y_i(0)|X=x]
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=E%5BY_i(1)-Y_i(0)%7CX%3Dx%5D"></div>

其中X=x时条件约束, 例如X=[年龄=56, 血压=150...]

## Two-tree model
则学习拟合出
Treatment response function
<!-- $$
\hat \mu_1 (x) = E[Y_i|W_i=1,X=x] 
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=%5Chat%20%5Cmu_1%20(x)%20%3D%20E%5BY_i%7CW_i%3D1%2CX%3Dx%5D%20"></div>

Control response function
<!-- $$
\hat \mu_0 (x) = E[Y_i|W_i=0,X=x] 
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=%5Chat%20%5Cmu_0%20(x)%20%3D%20E%5BY_i%7CW_i%3D0%2CX%3Dx%5D%20"></div>

然后计算
<!-- $$
\hat \mu_1 (x)-\hat \mu_0 (x)
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=%5Chat%20%5Cmu_1%20(x)-%5Chat%20%5Cmu_0%20(x)"></div>

## Single-tree model
直接拟合出
<!-- $$
\hat \mu (x,w) = E[Y_i|W_i=w,X=x] 
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=%5Chat%20%5Cmu%20(x%2Cw)%20%3D%20E%5BY_i%7CW_i%3Dw%2CX%3Dx%5D%20"></div>
然后计算
<!-- $$
\hat \mu (x,1)-\hat \mu (x,0)
$$ --> 

<div align="center"><img src="https://render.githubusercontent.com/render/math?math=%5Chat%20%5Cmu%20(x%2C1)-%5Chat%20%5Cmu%20(x%2C0)"></div>

参考
