---
title: 'Markdown语法|LaTex数学公式'
date: 2020-05-12 02:37:44
tags: []
published: true
hideInList: false
feature: 
isTop: false
---
## **1.常用语法**

| 特殊字符    | 说  明                                  | 实例                             | 完整字符串                     |
| ----------- | --------------------------------------- | -------------------------------- | ------------------------------ |
| $           | 数学公式前后加$是行内公式               | 数学公式:$a=x+y$                 | 数学公式:a=x+y                 |
| $$          | 数学公式加$$就是读占一行的公式          | 独占一行:$$a=x+y$$               | 独占一行:a=x+y                 |
| \           | 转义字符,特殊字符要显示原意,就在前面加\ | $\$$                             | \                              |
| \\          | 在数学公式中是换行                      | $a=x+y\\b=y$                     | a=x+y\\b=y                     |
| _           | 后跟内容为下标                          | $a_i$                            | a_i                            |
| ^           | 后跟内容为上标                          | $a^i$                            | a^i                            |
| {}          | 被括号起来的公式是一组内容              | $x_{22} y^{(x)} x^{y^z}$         | x_{22} y^{(x)} x^{y^z}         |
| \frac       | 分数                                    | $\frac{1}{a}$                    | \frac{1}{a}                    |
| \sqrt       | 开根                                    | $\sqrt{xy}+\sqrt[a]{x}$          | \sqrt{xy}+\sqrt[a]{x}          |
| \ldots      | 跟文本底线对齐的省略号                  | $a_{i\ldots{n}}$                 | a_{i\ldots{n}}                 |
| \cdots      | 跟文本中线对齐的省略号                  | $i\cdots n$                      | i\cdots n                      |
| \sum        | 求和                                    | $\sum_{k=1}^nkx $                | \sum_{k=1}^nkx                 |
| \int        | 积分                                    | $\int_a^b$                       | \int_a^b                       |
| \limits     | 强制上下限在上下侧                      | $\sum\limits_{k=1}^nkx $         | \sum\limits_{k=1}^nkx          |
| \nolimits   | 强制上下限在右侧                        | $\sum\nolimits_{k=1}^nkx$        | \sum\nolimits_{k=1}^nkx        |
| \overline   | 上划线                                  | $\overline{a+b}$                 | \overline{a+b}                 |
| \underline  | 下划线                                  | $\underline{a+b}$                | \underline{a+b}                |
| \overbrace  | 上花括号                                | $\overbrace{a+b+\dots+n}^{m个}$\ | \overbrace{a+b+\dots+n}^{m个}\ |
| \underbrace | 下花括号                                | $\underbrace{a+b+\dots+n}_{m个}$ | \underbrace{a+b+\dots+n}_{m个} |
| \vec        | 向量                                    | $\vec{a}$                        | \vec{a}                        |

## 2.矩阵的显示**


$$
 \frac{du}{dx}
$$
∣∣∣adbecf∣∣∣|abcdef|
其实是上面语法的一个组合, 代码如下:

```
$\left|                --左边的竖线
\begin{array}{lcr}     --一个array的开始, l/c/r表示列的对齐方式左/中/右
a & b & c \\           --&分隔列 \\换行 
d & e & f 
\end{array}            --一个array的结束
\right|$               --右边的竖线123456
```

版权声明：本文为CSDN博主「_汐影_」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/zryxh1/article/details/53161011