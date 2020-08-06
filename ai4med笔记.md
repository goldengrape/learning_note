# AI4Med笔记

- AI For Medical Treatment

## C-index计算:
$$
C_{index}=\frac{\#concordant \space pairs + 0.5 \times \#risk \space ties}{\#permissible \space pairs}
$$ 
其中:
* permissible pairs := 具有不同outcome的pairs数量
* concordant pairs := “方向一致”的pairs数量, 例如高estimate分数, 高outcome分数
* risk pairs := 同estimate分数, 不同outcome