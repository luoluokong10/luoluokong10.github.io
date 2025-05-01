# Matlab 绘图


## 简介

Matlab 通常使用面向过程写法，也支持面向对象。绘图的过程非常切合面向对象的思想，在底层也是如此实现的。

尽管matlab支持函数式的绘图，但是这样的操作仅适合一些简单单图的处理。

### 图形对象层次结构

oop的绘图，就是摊开画布往上面添加元素，这些元素的包含关系即对象父子关系，具有层级结构。

通过引用将对象地址赋予变量，然后访问属性、方法来定制图像。

![层级结构图形对象的组织](/pictures/doccenter_graphicsheirarchy.png)

matlab的绘图层级，主要是 Figure - Axes - 各种函数对应的图形 以及它们上面的一些控件/文本/标记

直接使用函数绘图，仍然在后台构造对象(gcf, gca, gco)，只是未显式操作它们。

### 实例
> 在交互环境一行行执行即可看到对应的效果
```matlab
fg = figure; # 创建figure实例
ax = axes('parent', fg); # 创建axes实例，指定父级
x = linspace(0, 1, 100);
line = plot(x, sin(x));
```

使用 get()查看所有所有属性和值; properties 可用属性; inspect 交互式属性查看器.
```matlab
line.LineStyle = ':';
ax.FontSize = 16;
```
关于属性的效果参考 [mathwork](https://ww2.mathworks.cn/help/matlab/graphics-object-properties.html?s_tid=CRUX_lftnav)

## 实战

### 封装散点图+线性拟合

### 局部放大

---

> 作者: luoluo  
> URL: https://luoluokong10.github.io/2025/04/matlab-draw/  

