---
title: '如何用在Typora中添加数学公式?'
date: 2020-05-12 01:52:49
tags: [Markdown]
published: true
hideInList: false
feature: 
isTop: false
---
### 0.添加公式

语法：

```
$$
（这里输入要添加的公式）
$$
````

效果：
$$
（这里输入要添加的公式）
$$
注：

如果要在同一行输入多个公式，只需要在公式之间加上\(空格)或者\quad

如果要输入多行公式，只需要在上一行公式的末尾加上\\





### 1.算式

##### 1.1 分式

语法：

```
$$
\frac{a}{b}
$$
```

效果：
$$
\frac{a}{b}
$$

##### 1.2 根式

语法：

```
$$
\sqrt{x} or \sqrt[n]{x}
$$
```

效果：

$$
\sqrt{x} or \sqrt[n]{x}
$$


##### 1.3 上下标

语法：

```
$$
x^n or x_n
$$
```

效果：

$$
x^n or x_n
$$


##### 1.4 向量

语法：

```
$$
\vec{a}\cdot\vec{b}=0
$$
```

效果：
$$
\vec{a}\cdot\vec{b}=0
$$


##### 1.5 均值

语法：

```
$$
\overline{x}
$$
```

效果：

$$
\overline{x}
$$


##### 1.6 极限

语法：

```
$$
\lim_{n\to+\infty} n or \lim n
$$
```

效果：

$$
\lim_{n\to+\infty} n or \lim n
$$
``

##### 1.7 积分

语法：

```
$$
\int_0^n f(x)dx or \int f(x)dx
$$
```

效果：
$$
\int_0^n f(x)dx or \int f(x)dx
$$

##### 1.8 累加

语法：

```
$$
\sum_{i=1}^n a_i or \sum a_i
$$
```

效果：
$$
\sum_{i=1}^n a_i or \sum a_i
$$

##### 1.9 累乘

语法：

```
$$
\prod_{i=1}^n x_i or \prod x_i
$$
```

效果：
$$
\prod_{i=1}^n x_i or \prod x_i
$$





### 2.运算符

| 运算符 | markdown        |
| ------ | --------------- |
| ±      | \pm             |
| ×      | \times          |
| ÷      | \div            |
| ≤      | \leq            |
| ≥      | \geq            |
| ≠      | \neq            |
| ⇒      | \Rightarrow     |
| ⇔      | \Leftrightarrow |
| ⊂      | \subset         |
| ⊆      | \subseteq       |
| ∈      | \in             |
| ∉      | \notin          |
| ∪      | \cup            |
| ∩      | \cap            |
| R      | \mathbb{R}      |
| Q      | \mathbb{Q}      |
| Z      | \mathbb{Z}      |
| N      | \mathbb{N}      |





### 3.函数

##### 3.1 三角函数和对数函数

| 函数   | markdown |
| ------ | -------- |
| sin(x) | \sin(x)  |
| cos(x) | \cos(x)  |
| tan(x) | \tan(x)  |
| log2 x | \log_2 x |
| lnx    | \ln x    |
| lgx    | \lg x    |

##### 3.2 分段函数

语法：

```
$$
f(x)=
\begin{cases}
1 & x\geq 0\\
0 & x<0
\end{cases}
$$
```

效果：
$$
f(x)=
\begin{cases}
1 & x\geq 0\\
0 & x<0
\end{cases}
$$


### 4.希腊字母

| 大写 | markdown      | 小写 | markdown    |
| ---- | ------------- | ---- | ----------- |
| A    | A or \Alpha   | α    | \alpha      |
| B    | B or \Beta    | β    | \beta       |
| Γ    | \Gamma        | γ    | \gamma      |
| Δ    | \Delta        | δ    | \delta      |
| E    | E or \Epsilon | ϵ    | \epsilon    |
|      |               | ε    | \varepsilon |
| Z    | Z or \Zeta    | ζ    | \zeta       |
| H    | H or \Eta     | η    | \eta        |
| Θ    | \Theta        | θ    | \theta      |
| I    | I or \Iota    | ι    | \iota       |
| K    | K or \Kappa   | κ    | \kappa      |
| Λ    | \Lambda       | λ    | \lambda     |
| M    | M or \Mu      | μ    | \mu         |
| N    | N or \Nu      | ν    | \nu         |
| Ξ    | \Xi           | ξ    | \xi         |
| O    | O or \Omicron | ο    | \omicron    |
| Π    | \Pi           | π    | \pi         |
| P    | P or \Rho     | ρ    | \rho        |
| Σ    | \Sigma        | σ    | \sigma      |
| T    | T or \Tau     | τ    | \tau        |
| Υ    | Y or \Upsilon | υ    | \upsilon    |
| Φ    | \Phi          | ϕ    | \phi        |
|      |               | φ    | \varphi     |
| X    | X or \Chi     | χ    | \chi        |
| Ψ    | \Psi          | ψ    | \psi        |
| Ω    | \Omega        | ω    | \omega      |

版权声明：本文为CSDN博主「X7treme」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/Ernest_YN/article/details/84064233



