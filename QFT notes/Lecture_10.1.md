---
title: "量子场论导论 Lecture 10.1"
date: null
tags:
  - 量子场论导论
  - lecture
  - 蝌蚪图抵消
  - Wick旋转
  - 维数积分
  - Feynman参数
source: "课堂板书"
---

# Lecture 10.1: 蝌蚪图抵消、Wick 旋转与维数积分

## 本节内容概览

本节先回顾蝌蚪图抵消的目的：通过加入线性反项，使一点函数满足 $\langle\Omega|\phi(x)|\Omega\rangle=0$。随后定义蝌蚪子图，说明所有含蝌蚪子图的图在重整化理论中都必须抵消，并用时空平移不变性证明蝌蚪子图的值是常数。课堂接着把相关动量积分写成一般的 $\widetilde{\mathcal I}(a,b)$，通过 Wick 旋转化为 Euclidean 积分。最后使用 $d$ 维球坐标、Beta/Gamma 函数和解析延拓得到积分的一般表达式，并引出 Feynman 参数公式。

# 1. 蝌蚪图抵消与线性反项

对应图片：

- 1
- 2
- 3
- 4
- 5
- 6

### 板书整理

![[Picture/10.1/1.jpg]]

上节回顾的两个主题：

- $V_{\mathrm{int}}=\dfrac{g}{n!}\phi^n$ 的费曼规则；
- 蝌蚪图抵消（tadpole cancellation）。

以三次相互作用为例：

$$
\mathcal L
=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2-\frac{g}{3!}\phi^3.
$$

板书指出：

$$
\langle\Omega|\phi(x)|\Omega\rangle\neq 0.
$$

因此需要重整化拉格朗日量：

$$
\mathcal L
=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2
-\frac{g}{3!}\phi^3+\gamma\phi,
$$

其中 $\gamma\phi$ 被标记为 “counter-term”，新的反项顶点因子为

$$
\text{一腿反项顶点}\quad\longleftrightarrow\quad +i\gamma.
$$

板书还给出多顶点与多场的例子：

$$
V_{\mathrm{int}}
=\frac{g_1}{3!}\phi^3+\frac{g_2}{5!}\phi^5,
\qquad
\text{相应顶点因子为 }-ig_1,\,-ig_2,
$$

以及

$$
V_{\mathrm{int}}
=\frac{g_1}{3!}\phi^3
+\frac{g_2}{3!}\chi^3
+\frac{g_3}{2!}\phi^2\chi+\cdots.
$$

![[Picture/10.1/2.jpg]]

一点函数可以通过选择 $\gamma$ 调整为零：

$$
\langle\phi_x\rangle=0
\qquad\text{if}\qquad
\gamma=\frac g2D_F(0)+O(g^2).
$$

**蝌蚪子图（tadpole sub-diagram）**的板书定义是：

> 可以通过切断一条内部线而从图中移除的部分，并且切断后不会使整幅图变得更加不连通；特别地，蝌蚪子图本身不包含外部点。

板书图示中：

- 含有一个闭合圈并通过一条内部线接回主图的部分，被标作 tadpole sub-diagram；
- 若切断后会把图分成更多独立部分，或该部分含有外部点，则标作 “not a tadpole”。

![[Picture/10.1/3.jpg]]

若一幅图含有一个或多个蝌蚪子图，则称其为蝌蚪图（tadpole diagram）。

板书命题：

> 在满足
> $$
> \langle\Omega|\phi(x)|\Omega\rangle=0
> $$
> 的重整化理论中，任意期望值
> $$
> \langle\Omega|T\{\phi(x_1)\cdots\phi(x_N)\}|\Omega\rangle
> $$
> 中的所有蝌蚪图都必须相互抵消。

证明从一幅含蝌蚪子图的图开始。板书把它写成

$$
\mathcal G
=
g(x_1,x_2,\ldots,x_N)\,
D_{xy}\,
G_{\mathrm{tadpole}},
$$

其中 $D_{xy}$ 是连接主图内部点 $x$ 与蝌蚪子图点 $y$ 的内部线。

![[Picture/10.1/4.jpg]]

加入反项后，对同一主图得到的贡献写成

$$
\mathcal G\,D_{xy}(i\gamma).
$$

因此只要选择

$$
\gamma=-iG_{\mathrm{tadpole}}
=\text{constant},
$$

蝌蚪子图贡献与反项贡献即可抵消。板书强调：这一选择对任意蝌蚪图都成立，因此也对所有蝌蚪图的总和成立。

![[Picture/10.1/5.jpg]]

证明中剩下的关键是说明 $G_{\mathrm{tadpole}}$ 与外部位置 $y$ 无关。由时空平移不变性，板书写出

$$
G_{\mathrm{tadpole}}
\propto
D_{y z_1}D_{y z_2}\cdots D_{y z_n}
\,f(z_1,z_2,\ldots,z_n),
$$

其中内部顶点位置已积分，且

$$
D_{yz}=D_F(y-z),
\qquad
D_{y,z+y}=D_F(-z).
$$

作变量代换

$$
z_i\longrightarrow z_i+y,
$$

并使用

$$
f(z_1+c,z_2+c,\ldots,z_n+c)
=f(z_1,z_2,\ldots,z_n),
$$

则

$$
\begin{aligned}
G_{\mathrm{tadpole}}
&\propto
D_F(-z_1)\cdots D_F(-z_n)
f(z_1,\ldots,z_n)\\
&\longrightarrow
\text{independent of }y
\longrightarrow \text{constant}.
\end{aligned}
$$

![[Picture/10.1/6.jpg]]

结论：

- 如果我们只想计算某个期望值，可以忽略蝌蚪图；
- Bubble diagrams，以及与所有外部点断开的子图，不包含在拉格朗日量微扰理论的关联函数中。

### 解释

线性反项的作用是抵消所有插入一点函数的蝌蚪子图。证明的核心不是逐个计算每一张图，而是利用平移不变性把蝌蚪子图整体平移，证明其值只依赖相对坐标，因此是常数。这样同一个常数反项 $\gamma$ 就能同时抵消任意外部图上的蝌蚪插入。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 2–6，关于“忽略蝌蚪图”和 bubble diagrams 的表述。
>
> 板书内容：与所有外部点断开的 bubble diagrams/子图不计入拉格朗日量微扰理论。
>
> 检查结果：这句话依赖于所使用的关联函数已经做了真空归一化。
>
> 说明：这里保留板书原意；若未归一化，纯真空泡图会作为整体因子出现，而不是逐项凭空消失。
>
> 注意：以上是适用范围说明，未修改板书内容。

# 2. Wick 旋转：从 Minkowski 动量积分到 Euclidean 积分

对应图片：

- 7
- 8
- 9
- 10
- 11

### 板书整理

![[Picture/10.1/7.jpg]]

考虑 $d$ 维时空，并定义动量积分

$$
\widetilde{\mathcal I}(a,b)
\equiv
\int\frac{d^d p}{(2\pi)^d}\,
\frac{(p^2)^a}{(-p^2-\Delta+i\epsilon)^b},
\qquad
\Delta>0.
$$

板书给出的例子是

$$
D_F(0)
=-i\int\frac{d^4p}{(2\pi)^4}
\frac{1}{p^2+m^2-i\epsilon}
=i\,\widetilde{\mathcal I}(0,1)
\qquad (d=4).
$$

![[Picture/10.1/8.jpg]]

采用度规约定：

$$
p^2=p^\mu p^\nu g_{\mu\nu}
=-(p^0)^2+\vec p^{\,2},
$$

其中

$$
p^\mu=(p^0,p^1,\ldots,p^{d-1}),
\qquad
\vec p=(p^1,\ldots,p^{d-1}).
$$

先对 $p^0$ 积分：

$$
\widetilde{\mathcal I}
=
\int\frac{d^{d-1}\vec p}{(2\pi)^{d-1}}
\int_{-\infty}^{\infty}\frac{dp^0}{2\pi}\,
\frac{(p^2)^a}
{\left((p^0)^2-(\vec p^{\,2}+\Delta)+i\epsilon\right)^b}
\equiv\widetilde{\mathcal I}_0.
$$

极点位于

$$
p^0
=\pm\sqrt{\vec p^{\,2}+\Delta-i\epsilon}
\approx
\pm\sqrt{\vec p^{\,2}+\Delta}\mp i\epsilon.
$$

图中画出沿实轴的积分路径以及上、下方的弧线 $\mathrm{arc}_1,\mathrm{arc}_2$。

![[Picture/10.1/9.jpg]]

若用闭合轮廓表示实轴积分，板书写成

$$
0=\oint f(\cdots)
=\widetilde{\mathcal I}_0-\widetilde{\mathcal I}_{E0}
+\mathrm{arc}_1+\mathrm{arc}_2,
$$

并注明所取轮廓内没有极点。

当 $|p^0|\to\infty$ 时，弧线贡献满足

$$
\mathrm{arc}
\propto
\int d\varphi\,
\frac{|p^0|^{2a}}{|p^0|^{2b}}
+\cdots
\longrightarrow 0
\quad\text{if}\quad
2a+1-2b<0,
$$

也就是

$$
b>a+\frac12.
$$

![[Picture/10.1/10.jpg]]

在弧线贡献消失的条件下，

$$
\widetilde{\mathcal I}_0
=\widetilde{\mathcal I}_{E0}
=\int_{-\infty}^{\infty}dp^0\,(\cdots)
=i\int_{-\infty}^{\infty}dp_E^0\,(\cdots).
$$

作变量代换

$$
p^0=i p_E^0.
$$

板书将 Minkowski 动量写成

$$
p^\mu
=(ip_E^0,p^1,\ldots,p^{d-1})
=(ip_E^0,\vec p),
$$

并定义 Euclidean 动量

$$
p_E^\mu=(p_E^0,\vec p).
$$

于是

$$
p^2
=g_{\mu\nu}p^\mu p^\nu
=(p_E^0)^2+\vec p^{\,2}
\longrightarrow
\text{Euclidean dot product}.
$$

![[Picture/10.1/11.jpg]]

Wick 旋转后，

$$
\widetilde{\mathcal I}
=
i\int\frac{d^{d-1}\vec p}{(2\pi)^{d-1}}
\int_{-\infty}^{\infty}\frac{dp_E^0}{2\pi}\,
\frac{(p_E^2)^a}
{(-p_E^2-\Delta+i\epsilon)^b},
$$

即

$$
\widetilde{\mathcal I}
=
i\int\frac{d^d p_E}{(2\pi)^d}\,
\frac{(p_E^2)^a}
{(-p_E^2-\Delta+i\epsilon)^b}.
$$

板书注明：若 $\Delta>0$，此时没有极点，可以在这一步令 $\epsilon=0$。因此得到框出的结果

$$
\boxed{
\widetilde{\mathcal I}
=
i(-1)^{-b}
\int\frac{d^d p_E}{(2\pi)^d}\,
\frac{(p_E^2)^a}{(p_E^2+\Delta)^b}
}.
$$

### 解释

Wick 旋转把时间分量的积分路径从实轴转到虚轴，并把 Minkowski 二次型变成正定的 Euclidean 内积。板书先在弧线确实消失的条件 $b>a+\tfrac12$ 下完成变形；后面的解析延拓用于把结果推广到更一般的 $a,b,d$。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 9–11，Wick 旋转的适用条件。
>
> 板书内容：弧线在 $b>a+\frac12$ 时消失，随后使用解析延拓。
>
> 检查结果：不能把后面的解析表达式直接理解为原始实轴积分在所有参数下都收敛。
>
> 说明：原始轮廓变形需要弧线衰减及极点避让；解析延拓得到的公式可定义更广的参数区域，但发散点仍由 Gamma 函数极点体现。
>
> 注意：以上为条件说明，未修改板书推导。

# 3. $d$ 维球坐标、Gamma 函数与 Feynman 参数

对应图片：

- 12
- 13
- 14

### 板书整理

![[Picture/10.1/12.jpg]]

在 $d$ 维 Euclidean 空间使用球坐标：

$$
d^d p_E
=
|\vec p_E|^{d-1}\,d|\vec p_E|\,d\Omega_{d-1},
$$

其中

$$
\vec p_E\equiv(p_E^0,\vec p),
\qquad
|\vec p_E|
=\sqrt{\vec p_E\cdot\vec p_E}.
$$

球面角元为

$$
d\Omega_{d-1}
=
d\varphi_1\cdots d\varphi_{d-1}\,
\sin^{d-2}(\varphi_{d-1})
\sin^{d-3}(\varphi_{d-2})
\cdots
\sin(\varphi_2).
$$

例子：

$$
d=2:\quad d\Omega_1=d\varphi_1,
$$

$$
d=3:\quad d\Omega_2=d\varphi_1\,d\varphi_2\sin(\varphi_2).
$$

球面总立体角：

$$
\int d\Omega_{d-1}
=\frac{2\pi^{d/2}}{\Gamma(d/2)}.
$$

板书还给出由 Beta 函数定义得到的径向积分：

$$
\int_0^\infty dx\,
\frac{x^A}{(x^2+\Delta)^B}
=
\frac{1}{2\Delta^{\,B-\frac{A+1}{2}}}
\frac{
\Gamma\!\left(\frac{A+1}{2}\right)
\Gamma\!\left(B-\frac{A+1}{2}\right)
}{
\Gamma(B)
}.
$$

![[Picture/10.1/13.jpg]]

代入球坐标并先做角积分：

$$
\widetilde{\mathcal I}
=
i(-1)^{-b}\frac{1}{(2\pi)^d}
\int d\Omega_{d-1}
\int_0^\infty d|\vec p_E|\,
|\vec p_E|^{d-1}
\frac{(p_E^2)^a}{(p_E^2+\Delta)^b}.
$$

使用上面的球面面积和径向积分，得到

$$
\boxed{
\widetilde{\mathcal I}
=
\frac{i(-1)^{-b}}{(4\pi)^{d/2}}\,
\frac{1}{\Delta^{\,b-a-d/2}}\,
\frac{
\Gamma\!\left(a+\frac d2\right)
\Gamma\!\left(b-a-\frac d2\right)
}{
\Gamma\!\left(\frac d2\right)\Gamma(b)
}
}.
$$

板书随后说明：由解析延拓，可以取 $a,b,d\in\mathbb R$（在所关心的情形还取 $\Delta>0$），因为 $\Gamma(x)$ 是亚纯函数，在复平面除孤立极点外解析，并且

$$
\Gamma(-n)=\infty,
\qquad n=0,1,2,\ldots.
$$

![[Picture/10.1/14.jpg]]

因此需要特别注意的条件是

$$
a+\frac d2=-n
\qquad\text{或}\qquad
b-a-\frac d2=-n.
$$

板书例子：

$$
D_F(0)
=-i\int\frac{d^4p}{(2\pi)^4}
\frac{1}{p^2+m^2-i\epsilon}
\quad\Longrightarrow\quad
a=0,\ b=1,\ d=4,
$$

于是

$$
b-a-\frac d2
=1-0-\frac42=-1,
$$

所以该积分发散。

最后引入 Feynman 参数公式：

$$
\boxed{
\frac{1}{A_1^{a_1}A_2^{a_2}\cdots A_N^{a_N}}
=
\frac{\Gamma(a_1+\cdots+a_N)}
{\Gamma(a_1)\cdots\Gamma(a_N)}
\int_0^1 dx_1\cdots dx_N\,
\frac{
x_1^{a_1-1}\cdots x_N^{a_N-1}
\delta(x_1+\cdots+x_N-1)
}{
\left[x_1A_1+\cdots+x_NA_N\right]^{a_1+\cdots+a_N}
}
}.
$$

### 解释

球坐标把 $d$ 维积分拆成径向积分和角积分，角积分产生 $\Gamma(d/2)$，径向积分则通过 Beta 函数化为两个 Gamma 函数的乘积。最终公式把紫外发散位置直接显示为 Gamma 函数的极点。Feynman 参数公式把多个分母合并成一个分母，是后续多传播子圈积分的标准整理步骤。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 13–14，Gamma 函数公式与发散条件。
>
> 板书内容：$\Gamma(-n)=\infty$，并以 $D_F(0)$ 的 $a=0,b=1,d=4$ 为例判定发散。
>
> 检查结果：这里的发散是未经正规化的积分发散；Gamma 函数公式本身是解析延拓后的表达式。
>
> 说明：原板书没有指定截断、维数正规化或其他具体正规化方案，因此只保留“发散”的判断，不替换为某一种正规化后的有限部分。
>
> 注意：以上为数学含义说明，未修改原板书表达式。

# 本节知识结构

三次相互作用导致一点函数非零  
↓  
加入线性反项 $\gamma\phi$  
↓  
定义蝌蚪子图与蝌蚪图  
↓  
平移不变性 $\Rightarrow$ 蝌蚪子图值为常数  
↓  
反项与所有蝌蚪插入抵消  
↓  
构造一般动量积分 $\widetilde{\mathcal I}(a,b)$  
↓  
$ p^0$ 复平面轮廓与 Wick 旋转  
↓  
Minkowski 二次型 $\to$ Euclidean 内积  
↓  
$d$ 维球坐标与 Beta/Gamma 函数  
↓  
解析延拓与发散条件  
↓  
Feynman 参数合并多个分母。

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $\mathcal L=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2-\frac{g}{3!}\phi^3+\gamma\phi$ | 加入线性反项后的拉格朗日量 |
| $\langle\phi_x\rangle=0$ if $\gamma=\frac g2D_F(0)+O(g^2)$ | 一点函数为零的反项条件 |
| $\gamma=-iG_{\mathrm{tadpole}}$ | 反项抵消蝌蚪子图的选择 |
| $D_{yz}=D_F(y-z)$ | 平移不变的传播子 |
| $\widetilde{\mathcal I}(a,b)=\int\frac{d^d p}{(2\pi)^d}\frac{(p^2)^a}{(-p^2-\Delta+i\epsilon)^b}$ | Wick 旋转前的一般动量积分 |
| $b>a+\frac12$ | $p^0$ 轮廓弧线消失的条件 |
| $p^0=ip_E^0$ | Wick 旋转变量代换 |
| $p^2=(p_E^0)^2+\vec p^{\,2}=p_E^2$ | Minkowski 二次型转为 Euclidean 内积 |
| $\widetilde{\mathcal I}=i(-1)^{-b}\int\frac{d^d p_E}{(2\pi)^d}\frac{(p_E^2)^a}{(p_E^2+\Delta)^b}$ | Wick 旋转后的积分 |
| $d^d p_E=|\vec p_E|^{d-1}d|\vec p_E|\,d\Omega_{d-1}$ | $d$ 维球坐标测度 |
| $\int d\Omega_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}$ | $(d-1)$ 维球面的总立体角 |
| $\int_0^\infty dx\,\frac{x^A}{(x^2+\Delta)^B}=\frac{\Gamma((A+1)/2)\Gamma(B-(A+1)/2)}{2\Delta^{B-(A+1)/2}\Gamma(B)}$ | Beta/Gamma 函数给出的径向积分 |
| $\widetilde{\mathcal I}=\frac{i(-1)^{-b}}{(4\pi)^{d/2}\Delta^{b-a-d/2}}\frac{\Gamma(a+d/2)\Gamma(b-a-d/2)}{\Gamma(d/2)\Gamma(b)}$ | 一般 $d$ 维积分结果 |
| $a+\frac d2=-n$ 或 $b-a-\frac d2=-n$ | Gamma 函数极点导致发散的条件 |
| $\frac{1}{\prod_i A_i^{a_i}}=\frac{\Gamma(\sum_i a_i)}{\prod_i\Gamma(a_i)}\int_0^1\prod_i dx_i\,\frac{\prod_i x_i^{a_i-1}\delta(\sum_i x_i-1)}{(\sum_i x_iA_i)^{\sum_i a_i}}$ | Feynman 参数公式 |

# 板书完整性与数学检查

- 已发现并按数字顺序处理 Picture/10.1/1.jpg 至 14.jpg，共 14 张；没有缺失编号，也没有未排序或无法读取的图片。
- 所有板书图片均已在对应小节附近嵌入，原图未移动、重命名或修改。
- 板书中的英文定义、图示说明、公式中间步骤、弧线收敛条件、解析延拓说明和 Feynman 参数公式均已保留。
- 图片 2–6 的 bubble diagram 结论、图片 9–11 的 Wick 旋转条件、图片 13–14 的 Gamma 函数发散判断分别以 warning callout 标记了适用范围或数学含义；没有改写原板书公式。
- 板书未提供可靠授课日期，因此 YAML 使用 date: null。

