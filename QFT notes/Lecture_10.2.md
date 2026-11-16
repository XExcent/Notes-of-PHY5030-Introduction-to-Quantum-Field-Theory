---
title: "量子场论导论 Lecture 10.2"
date: null
tags:
  - 量子场论导论
  - lecture
  - Pauli-Villars正则化
  - Feynman参数
  - 动量空间费曼规则
source: "课堂板书"
---

# Lecture 10.2: 正则化与动量空间费曼规则

## 本节内容概览

本节先复习 Wick 旋转、Euclidean 积分和 Feynman 参数化，并把多个传播子分母合并为单一分母。随后用 Pauli–Villars 方法正则化 $D_F(0)$，比较引入一个和两个虚构质量后的紫外收敛性，并在 $d=4$ 中计算其大质量极限。最后回到 $\phi^3$ 理论，说明非观测量可以吸收发散，并从 LSZ 公式开始写出动量空间的费曼规则与一圈 tadpole 贡献。

## 1. 复习：Wick 旋转、Euclidean 积分与 Feynman 参数

对应图片：1、2

### 板书整理

![[Picture/10.2/1.jpg]]

板书提醒：`HW due today`。上节内容列出：

- Tadpole cancellation；
- Wick rotation：$\widetilde{\mathcal I}=\widetilde{\mathcal I}_E$，并把 Minkowski 积分转为 Euclidean 积分。

板书给出的 Euclidean 积分关系为

$$
\int \frac{d^d p}{(2\pi)^d}
\frac{(p^2)^a}{(-p^2-\Delta+i\epsilon)^b}
=
\frac{i(-1)^{-b}}{(4\pi)^{d/2}}
\frac{1}{\Delta^{\,b-a-d/2}}
\frac{\Gamma\!\left(a+\frac d2\right)\Gamma\!\left(b-a-\frac d2\right)}
{\Gamma(b)\Gamma\!\left(\frac d2\right)} .
$$

Feynman 参数公式的例子是

$$
\frac1{AB}
=
\frac{\Gamma(1+1)}{\Gamma(1)\Gamma(1)}
\int_0^1 dx\int_0^1dy\,
\frac{\delta(x+y-1)}{[yA+xB]^2}.
$$

蓝色标注说明：现在分母 $A,B$ 出现在同一个分母中。利用 $\delta(x+y-1)$ 做掉一个参数后，板书写成

$$
\frac1{AB}
=\int_0^1dx\,
\frac1{[(1-x)A+xB]^2}.
$$

![[Picture/10.2/2.jpg]]

对两个二次分母，板书逐步写出

$$
\begin{aligned}
\int\frac{d^4p}{(2\pi)^4}
\frac1{(p^2+\Delta_1)(p^2+\Delta_2)}
&=\int_0^1dx\int\frac{d^4p}{(2\pi)^4}
\frac1{\big[(1-x)(p^2+\Delta_1)+x(p^2+\Delta_2)\big]^2}\\
&=\int_0^1dx\int\frac{d^4p}{(2\pi)^4}
\frac1{\big[p^2+\Delta_1+x(\Delta_2-\Delta_1)\big]^2}.
\end{aligned}
$$

因此可以把形如

$$
\int\frac{d^dp}{(2\pi)^d}
\frac{\operatorname{polynomial}(p^2)}{(p^2+\Delta_1)\cdots(p^2+\Delta_N)}
$$

的积分化为对 Feynman 参数的积分。

### 解释

Feynman 参数化把多个传播子分母合并成一个幂次更高的分母，便于先完成动量积分，再处理参数积分。板书中的 $\delta(x+y-1)$ 强制参数位于一个约束面上；在两个分母的例子中，合并后的有效质量平方是 $\Delta_1+x(\Delta_2-\Delta_1)$。

## 2. 正则化程序与 Pauli–Villars 正则化

对应图片：3、4、5、6、7、8、9

### 板书整理

![[Picture/10.2/3.jpg]]

板书定义正则化程序为：对发散积分给出一种计算处方，使得可观测量有限，并且与所选处方无关；也就是说，最终可观测量应当是稳健的，不同方法给出相同结果。

板书进入第一种方法：`Pauli–Villars regularization`，并考虑 $d$ 维中的 $D_F(0)$。

![[Picture/10.2/4.jpg]]

首先

$$
D_F(0)
=-i\int\frac{d^dp}{(2\pi)^d}\frac1{p^2+m^2-i\epsilon}
=\int\frac{d^dp_E}{(2\pi)^d}\frac1{p_E^2+m^2}.
$$

写成 $d$ 维球坐标后，板书得到

$$
D_F(0)
=\frac1{(2\pi)^d}\frac{2\pi^{d/2}}{\Gamma(d/2)}
\int_0^\infty d|p_E|\,
\frac{|p_E|^{d-1}}{|p_E|^2+m^2}
\quad\longrightarrow\quad
\text{convergent iff }d<2.
$$

定义带一个 Pauli–Villars 虚构质量 $M$ 的传播子：

$$
D_F^{\mathrm{PV}}(0)
=-i\int\frac{d^dp}{(2\pi)^d}
\left[
\frac1{p^2+m^2-i\epsilon}
-\frac1{p^2+M^2-i\epsilon}
\right],
\qquad M\gg m.
$$

板书把 $m$ 标为 physical mass，把 $M$ 标为 fictitious mass，并说明它在能标 $E\ll M$ 时不应影响可观测量；红字标注为 ghost particle（板书字样为“$D_V$ ghost”附近的说明）。

![[Picture/10.2/5.jpg]]

合并两个分母，板书写成

$$
D_F^{\mathrm{PV}}(0)
=-i\int\frac{d^dp}{(2\pi)^d}
\frac{M^2-m^2}
{(p^2+m^2-i\epsilon)(p^2+M^2-i\epsilon)}
\sim
-iM^2\int\frac{d^dp}{(2\pi)^d}
\frac1{(p^2+m^2-i\epsilon)(p^2+M^2-i\epsilon)}.
$$

板书结论：它比 $D_F(0)$ 更收敛，并且 `convergent iff $d<4$`。

接着引入两个虚构质量 $M_1,M_2$：

$$
\begin{aligned}
D_F^{\mathrm{PV2}}(0)=-i\int\frac{d^dp}{(2\pi)^d}\Bigg[&
\frac1{p^2+m^2-i\epsilon}\\
&+\frac1{M_1^2-M_2^2}
\left(
\frac{M_2^2-m^2}{p^2+M_1^2-i\epsilon}
-\frac{M_1^2-m^2}{p^2+M_2^2-i\epsilon}
\right)\Bigg].
\end{aligned}
$$

![[Picture/10.2/6.jpg]]

化为一个分式后，板书得到

$$
D_F^{\mathrm{PV2}}(0)
=-i\int\frac{d^dp}{(2\pi)^d}
\frac{M_1^2M_2^2-m^2(M_1^2+M_2^2)+m^4}
{(p^2+m^2-i\epsilon)(p^2+M_1^2-i\epsilon)(p^2+M_2^2-i\epsilon)}.
$$

取

$$
M_1=M_2\equiv M\gg m,
$$

于是

$$
D_F^{\mathrm{PV2}}(0)
=-iM^4\int\frac{d^dp}{(2\pi)^d}
\frac1{(p^2+m^2-i\epsilon)(p^2+M^2-i\epsilon)^2},
\qquad \text{convergent iff }d<6.
$$

板书随后设 $d=4$。

![[Picture/10.2/7.jpg]]

在 $d=4$ 中使用 Feynman 参数，板书写出

$$
\begin{aligned}
D_F^{\mathrm{PV2}}(0)
&=-iM^4\int\frac{d^4p}{(2\pi)^4}
\frac{\Gamma(3)}{\Gamma(1)\Gamma(2)}
\int_0^1dx\,dy\,
\frac{y\,\delta(x+y-1)}
{\left[x(p^2+m^2-i\epsilon)+y(p^2+M^2-i\epsilon)\right]^3}\\
&=-2iM^4\int\frac{d^4p}{(2\pi)^4}\int_0^1dy\,
\frac{y}{\left[p^2+m^2-i\epsilon+(M^2-m^2)y\right]^3}.
\end{aligned}
$$

用 Wick 旋转和前述积分公式，板书继续写成

$$
D_F^{\mathrm{PV2}}(0)
=\frac{M^4}{16\pi^2}\int_0^1dy\,
\frac{y}{m^2+M^2y},
$$

其中右侧标注了 $\Delta=m^2+M^2y$、$a=0$、$b=3$、$d=4$；在分母中把 $(M^2-m^2)y$ 近似为 $M^2y$ 是 $M\gg m$ 下的板书近似。

![[Picture/10.2/8.jpg]]

积分结果为

$$
D_F^{\mathrm{PV2}}(0)
=\frac{M^4}{16\pi^2}
\left[
\frac1{M^2}
+\frac{m^2}{M^4}
\log\left(\frac{m^2}{m^2+M^2}\right)
\right]
\sim \frac{M^2}{16\pi^2}.
$$

板书将含 $m^2/M^4$ 的项划掉并标为 $\sim0$，即在 $M\to\infty$ 的大质量极限下忽略它。

板书回顾 $\phi^3$ 理论中的一阶结果：

$$
\gamma=\frac g2D_F(0)+O(g^3),
$$

因此得到框出的结果

$$
\boxed{\gamma=\frac{gM^2}{32\pi^2}+O(g^3)}.
$$

注：板书中的符号是手写的高大“Y”形，结合 $\phi^3$ 反项语境按 $\gamma$ 记录；若按字形阅读，也可能被看作 $\Upsilon$。

![[Picture/10.2/9.jpg]]

板书说明：现在可以取 $M\to\infty$。$\gamma$ 不是可观测量，所以它形式上为无穷大是可以接受的；这给出了重整化的一个例子：

1. 重新定义拉格朗日量：
   $$
   \mathcal L\longrightarrow \mathcal L+\gamma\phi.
   $$
2. 把无穷大吸收到 counter-terms 中，板书以 `$\gamma=\infty$` 表示。
3. 可观测量保持有限，例如
   $$
   \langle\Omega|\phi(x)|\Omega\rangle=0.
   $$

### 解释

Pauli–Villars 正则化通过加入带负号的重质量传播子，抵消大动量展开中的主导项。一个虚构质量把收敛条件从 $d<2$ 改善到 $d<4$；两个虚构质量进一步把条件改善到 $d<6$。虚构质量最终取很大，只要考察的物理能标远小于 $M$，其影响可以被限制在正则化和反项的处理中。

### 板书检查提醒

> [!warning]
> **板书检查提醒**
>
> 位置：图片 7–8，$D_F^{\mathrm{PV2}}(0)$ 的 $d=4$ 计算。
>
> 板书先出现精确组合 $m^2+(M^2-m^2)y$，随后在 $M\gg m$ 下写成 $m^2+M^2y$，并得到对数项。
>
> 检查结果：后一步是大 $M$ 近似，不能当作对任意 $M$ 都成立的精确等式。
>
> 注意：以上为检查提示，未修改原板书内容。

## 3. 动量空间费曼规则与一圈 tadpole

对应图片：10、11、12

### 板书整理

![[Picture/10.2/10.jpg]]

板书标题为 `Feynman rules in momentum space`，考虑最简单的“scattering”过程 $1\to1$，外线动量由 $p$ 变为 $p'$。

从 LSZ 公式开始，板书写出

$$
\begin{aligned}
\langle p'|S|p\rangle
={}&
\left[i\int d^4x\,e^{ip\cdot x}(-\Box_x+m^2)\right]
\left[i\int d^4x'\,e^{-ip'\cdot x'}(-\Box_{x'}+m^2)\right]\\
&\qquad\times
\langle\Omega|T\{\phi(x)\phi(x')\}|\Omega\rangle.
\end{aligned}
$$

![[Picture/10.2/11.jpg]]

板书把两端算符作用在传播子上，强调它们会 `exactly cancel the external propagators`。外部线对应 $D_{xy}$、$D_{x'y'}$；板书给出的传播子形式为

$$
D_F(x-y)\sim -i\int\frac{d^4q}{(2\pi)^4}
\frac{e^{iq\cdot(x-y)}}{q^2+m^2-i\epsilon}.
$$

在 $\phi^3$ 理论中，板书画出

$$
\langle\phi_x\phi_{x'}\rangle
=\text{自由传播线}
+\text{带 tadpole 的一圈图}
+O(g^4),
$$

并注明 trivial scattering $	o$ ignore，即把没有相互作用的平凡传播部分忽略。

![[Picture/10.2/12.jpg]]

一圈 tadpole 图的坐标空间表达式为

$$
\langle\phi_x\phi_{x'}\rangle_{\text{1-loop}}
=\frac{(-ig)^2}{2}
\int d^4y\,d^4y'\,
D_{xy}\,D_{yy'}^{\,2}\,D_{y'x'}.
$$

将四条传播子都写成动量积分，板书得到

$$
\begin{aligned}
\langle\phi_x\phi_{x'}\rangle_{\text{1-loop}}
={}&-\frac{g^2}{2}(-i)^4
\int d^4y\,d^4y'
\int\frac{d^4k_1}{(2\pi)^4}\frac{d^4k_2}{(2\pi)^4}
\frac{d^4k_3}{(2\pi)^4}\frac{d^4k_4}{(2\pi)^4}\\
&\quad\times
\frac{\exp\!\left\{i\left[k_1\!\cdot(x-y)+k_2\!\cdot(y-y')
+k_3\!\cdot(y-y')+k_4\!\cdot(y'-x')\right]\right\}}
{(k_1^2+m^2-i\epsilon)(k_2^2+m^2-i\epsilon)
(k_3^2+m^2-i\epsilon)(k_4^2+m^2-i\epsilon)}.
\end{aligned}
$$

指数中对顶点坐标的组合为

$$
y\cdot(-k_1+k_2+k_3)+y'\cdot(-k_2-k_3+k_4),
$$

积分产生动量守恒的 delta 函数。板书特别标注了

$$
k_3=k-q,
\qquad
\delta(k'-q-k_3)=\delta\big(k'-q-(k-q)\big)=\delta(k'-k).
$$

最后写成

$$
\begin{aligned}
\langle\phi_x\phi_{x'}\rangle_{\text{1-loop}}
=-&\frac{g^2}{2}
\int\frac{d^4k}{(2\pi)^4}\frac{d^4k'}{(2\pi)^4}\frac{d^4q}{(2\pi)^4}
\frac{(2\pi)^4\delta(k'-k)e^{ik\cdot x}e^{-ik'\cdot x'}}
{(k^2+m^2-i\epsilon)(q^2+m^2-i\epsilon)
\big((k-q)^2+m^2-i\epsilon\big)(k'^2+m^2-i\epsilon)}.
\end{aligned}
$$

### 解释

LSZ 外部算符把外腿传播子的极点因子剥离，因此真正的散射核只保留内部传播子、顶点和动量守恒条件。一圈 tadpole 中两个顶点之间有两条相同的内部线，所以坐标空间中出现 $D_{yy'}^2$；对顶点坐标积分后得到动量守恒 delta 函数，并可用它消去一个独立动量。

# 本节知识结构

Wick 旋转与 Euclidean 积分
↓
Feynman 参数化：合并多个分母
↓
Pauli–Villars：加入重虚构质量抵消紫外发散
↓
$D_F(0)$ 的收敛性改善：$d<2\to d<4\to d<6$
↓
大质量极限与 counter-term
↓
LSZ 外腿抵消
↓
动量空间费曼规则与一圈 tadpole 动量积分

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $\displaystyle \frac1{AB}=\int_0^1dx\,\frac1{[(1-x)A+xB]^2}$ | 两个分母的 Feynman 参数化 |
| $\displaystyle D_F^{\mathrm{PV}}(0)=-i\int\frac{d^dp}{(2\pi)^d}\left[\frac1{p^2+m^2-i\epsilon}-\frac1{p^2+M^2-i\epsilon}\right]$ | 一个虚构质量的 Pauli–Villars 正则化 |
| $\displaystyle D_F^{\mathrm{PV2}}(0)=-iM^4\int\frac{d^dp}{(2\pi)^d}\frac1{(p^2+m^2-i\epsilon)(p^2+M^2-i\epsilon)^2}$ | 两个虚构质量相等时的形式 |
| $\displaystyle D_F^{\mathrm{PV2}}(0)\sim\frac{M^2}{16\pi^2}$ | $d=4$、$M\gg m$ 下的结果 |
| $\displaystyle \gamma=\frac{gM^2}{32\pi^2}+O(g^3)$ | $\phi^3$ 理论中板书给出的正则化一阶项 |
| $\displaystyle \langle\phi_x\phi_{x'}\rangle_{\text{1-loop}}=\frac{(-ig)^2}{2}\int d^4y\,d^4y' D_{xy}D_{yy'}^2D_{y'x'}$ | 一圈 tadpole 的坐标空间表达式 |

# 板书完整性与数学检查

- 已发现 `Picture/10.2/1.jpg` 至 `Picture/10.2/12.jpg`，共 12 张；按整数编号顺序处理，无缺失编号、重复编号或未排序图片。
- 每张图片均已在对应小节附近嵌入，原始图片未移动、重命名或修改。
- 保留了板书中的中间步骤、近似符号、收敛条件、颜色标注含义和 $M\to\infty$ 的说明。
- 图片 7–8 中从 $m^2+(M^2-m^2)y$ 到 $m^2+M^2y$ 是 $M\gg m$ 近似，已单独标注；未用近似式替换原先出现的精确组合。
- 图片 1 中 Euclidean 积分总式的 $(-1)^{-b}$ 按板书原样记录；未将其改写为其他约定。
- 图片 12 的指数和动量命名按板书可辨认内容记录；未发现足以确定为数学错误的地方。
