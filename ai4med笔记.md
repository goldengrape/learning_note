# AI4Med笔记

- AI For Medical Treatment

## C-index计算:
<!-- $$
C_{index}=\frac{\#concordant \space pairs + 0.5 \times \#risk \space ties}{\#permissible \space pairs}
$$ --> 

<div align="center"><img height ="50" src="https://render.githubusercontent.com/render/math?math=C_%7Bindex%7D%3D%5Cfrac%7B%5C%23concordant%20%5Cspace%20pairs%20%2B%200.5%20%5Ctimes%20%5C%23risk%20%5Cspace%20ties%7D%7B%5C%23permissible%20%5Cspace%20pairs%7D"></div> 
其中:

* permissible pairs := 具有不同outcome的pairs数量
* concordant pairs := “方向一致”的pairs数量, 例如高estimate分数, 高outcome分数
* risk pairs := 同estimate分数, 不同outcome