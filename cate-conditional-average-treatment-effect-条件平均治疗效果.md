# CATE (Conditional Average Treatment Effect, 条件平均治疗效果)

通过条件平均治疗效果可以得到个人治疗效果ITE. 

给定条件X=x时, 计算
$$
E[Y_i(1)-Y_i(0)|X=x]
$$

其中X=x时条件约束, 例如X=[年龄=56, 血压=150...]

## Two-tree model
则学习拟合出
Treatment response function
$$
\hat \mu_1 (x) = E[Y_i|W_i=1,X=x] 
$$

Control response function
$$
\hat \mu_0 (x) = E[Y_i|W_i=0,X=x] 
$$

然后计算
$$
\hat \mu_1 (x)-\hat \mu_0 (x)
$$

## Single-tree model
直接拟合出
$$
\hat \mu (x,w) = E[Y_i|W_i=w,X=x] 
$$
然后计算
$$
\hat \mu (x,1)-\hat \mu (x,0)
$$

参考

[[ATE (Average Treatment Effect, 平均治疗效果)计算]]