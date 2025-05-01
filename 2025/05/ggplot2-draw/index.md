# ggplot2 绘图

> 参考 [R语言教程-李东风](https://www.math.pku.edu.cn/teachers/lidf/docs/Rbook/html/_Rbook/ggplot2.html#)
> [R for Data Science](https://r4ds.had.co.nz/data-visualisation.html)

## 简介

ggplot2包是R的一个作图用的扩展包， 它实现了“图形的语法”， 将一个作图任务分解为若干个子任务， 只要完成各个子任务就可以完成作图。 在作常用的图形时， 只需要两个步骤： 首先将图形所展现的数据输入到ggplot()函数中， 然后调用某个geom_xxx()函数， 指定图形类型，如散点图、曲线图、盒形图等。

本质上，ggplot2 是对 R 语言绘图能力的一次高级封装。它引入了图层语法，以数据为核心，通过映射（aesthetic mapping）、几何对象（geoms）、统计变换（stats）等组件构建图像。相比传统绘图方式中对“画布元素”逐个添加的思路，ggplot2 更注重语义表达，使绘图过程更具逻辑性和可读性。

与 MATLAB 的绘图系统相比，ggplot2 更接近“数据可视化”范式而非“函数图像绘制”范式。MATLAB 更强调通过函数表达式控制图形细节，适合工程、信号处理等领域的数学函数可视化；而 ggplot2 更关注数据结构与变量间关系的呈现，更适用于统计建模、数据分析、科研可视化等场景。因此，ggplot2 与数据的耦合度更高。

作图流程：

1. 准备数据，data frame，长表(每行是一个观测对象，每列是一种属性);
2. 数据输入到ggplot()函数中, 指定参与作图的每个变量分别映射到哪些图形特性， 比如映射为x坐标、y坐标、颜色、形状等;
3. 选择一个合适的图形类型， 函数名以geom_开头， 如geom_point()表示散点图。 图形类型简称为geom。 将ggplot()部分与geom_xxx()部分用加号连接。 到此已经可以作图，下面的步骤是进一步的细化设定;
4. 设定适当的坐标系统， 如coord_cartesian(), scale_x_log10()等。 仍用加号连接;
5. 设定标题和图例位置等，如labs()。 仍用加号连接。

模版
```R
p <- ggplot(data=<输入数据框>,
  mapping=aes(<维度>=<变量名>,
    <维度>=<变量名>, <...>))
p + geom_<图形类型>(<...>) + 
  scale_<映射>_<类型>(<...>) +
  coord_<类型>(<...>) +
  labs(<...>)
```

### 实例

```R
library(tidyverse) # 加载数据集和ggplot2
mpg # 美国环境保护署对 38 种汽车型号的观察结果
p <- ggplot(data = mpg)
p + geom_point(mapping = aes(x= displ, y = hwy, color = class))
```


---

> 作者: luoluo  
> URL: https://luoluokong10.github.io/2025/05/ggplot2-draw/  

