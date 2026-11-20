---
title: "量子场论导论 Lecture 11.2"
date: 2026-11-20
tags:
  - 量子场论导论
  - lecture
  - 精确传播子
  - 自能
  - 重整化条件
  - 维数正则化
source: "课堂板书"
---

# Lecture 11.2: 精确传播子、自能与维数正则化

## 本节内容概览

从 LSZ 公式如何消去外线传播子出发，本节考察圈修正怎样改变两点函数的极点位置和留数。把单粒子不可约的两点图组成自能插入，就能对这些插入的串联求和，得到精确传播子。随后用物理质量和留数给出重整化条件，并写出相应的反项顶点。最后引入维数正则化，从作用量推导场与耦合常数的质量量纲，说明重整化标度的来源。

# 1. 从 LSZ 外线到精确传播子

对应图片：1、2

## 板书整理

![[Picture/11.2/1.jpg]]

上节课依次讨论了动量空间的费曼规则、树图与 Mandelstam 变量，以及 $\phi^3$ 和 $\phi^4$ 理论中的 $2\to2$ 散射。本节转向**精确传播子**。先回顾 LSZ 公式中一条外线对应的因子，其余外线以省略号表示：

$$
\langle f|\hat S|i\rangle
=\left[i\int d^4x\,e^{ip\cdot x}(p^2+m^2)\right]\cdots
\langle\Omega|T\{\phi(x)\cdots\}|\Omega\rangle .
$$

图中从外点 $x$ 画一条线到相互作用区域上的点 $y$。这段外线的自由传播子为

$$
D_F(x-y)=-i\int\frac{d^4q}{(2\pi)^4}
\frac{e^{iq\cdot(x-y)}}{q^2+m^2-i\epsilon}.
$$

板书在 $x$ 积分下标出 $q\to p$，并分别划出 $i$ 与 $-i$、$p^2+m^2$ 与传播子分母，表示 LSZ 中外线传播子的消去。

> [!warning]
> **板书检查提醒**
>
> 位置：图 1，外线动量的红色旁注。
>
> 板书内容：$e^{ip\cdot x}$ 与 $e^{iq\cdot(x-y)}$，旁注 $q\to p$。
>
> 检查结果：按图中两处相位直接积分，得到 $(2\pi)^4\delta^{(4)}(p+q)$，选取的是 $q=-p$。
>
> 说明：将积分变量 $q$ 反向后可使用 $q=p$ 的标记。两种定向都给出 $q^2=p^2$，外线分母的消去相同。
>
> 注意：以上为检查提示，未修改原板书内容。

![[Picture/11.2/2.jpg]]

相互作用使外线受到圈图修正。以 $\phi^3$ 理论为例，板书在端点 $x,y$ 之间依次画出自由线、一圈图、上下两条弧交错的两圈图，再以省略号表示其余项。这个图和记作 $\Delta(x-y)$，即精确传播子。它也可直接定义为

$$
\boxed{\Delta(x-y)\equiv
\langle\Omega|T\{\phi(x)\phi(y)\}|\Omega\rangle .}
$$

再定义动量空间的两个传播子。板书在以下 Fourier 变换中将四维坐标测度简记为 $dx$：

$$
\widetilde D_F(p^2)\equiv\int dx\,e^{-ip\cdot x}D_F(x)
=\frac{-i}{p^2+m^2-i\epsilon}.
$$

板书标出自由传播子的极点 $p^2=-m^2$。对于精确传播子，

$$
\widetilde\Delta(p^2)\equiv\int dx\,e^{-ip\cdot x}\Delta(x).
$$

## 解释

LSZ 公式中的 $p^2+m^2$ 来自外线截除。自由传播子的分母直接给出需要消去的极点；外线上出现圈图后，需要考察完整两点函数在极点附近的行为。

# 2. 物理质量与波函数归一化

对应图片：3、4

## 板书整理

![[Picture/11.2/3.jpg]]

在微扰论中有 $\widetilde\Delta(p^2)\approx\widetilde D_F(p^2)$。因此，板书从自由理论的极点出发，指出相互作用理论的极点在 $-m^2$ 附近，位置一般会移动。用这个极点定义粒子的**物理质量** $m_{\rm ph}$：

$$
\widetilde\Delta(p^2)\sim
\frac{-iZ}{p^2+m_{\rm ph}^2-i\epsilon},
\qquad p^2\to-m_{\rm ph}^2 .
$$

$\widetilde D_F$ 与 $\widetilde\Delta$ 的留数可以不同，一般有 $Z\ne1$。

![[Picture/11.2/4.jpg]]

施加波函数归一化条件

$$
\langle\vec p\,;t|\phi(x)|\Omega\rangle=e^{-ip\cdot x}
$$

可使 $\boxed{Z=1}$。板书将由此推出 $Z=1$ 留作习题（HW）。

用费曼规则计算 $\widetilde\Delta(p^2)$ 时保留两侧外线。板书依次画出动量 $p$ 向右流过的自由线、一个圈、上下弧交错的两个圈、前后分离的两个圈，以及后续项。这里计算的是两点函数，未做 LSZ 截除。

## 解释

极点位置确定 $m_{\rm ph}$，极点前的系数给出留数 $-iZ$。归一化条件固定了场从真空产生单粒子态的矩阵元，因此也固定了两点函数中单粒子极点的系数。

# 3. 单粒子不可约图与自能求和

对应图片：5、6、7

## 板书整理

![[Picture/11.2/5.jpg]]

**定义**　一个连通图，若切断任意一条内部线后仍然连通，就称为单粒子不可约图（one-particle irreducible，1PI）。

- 上图的两条上弧由一条下弧跨接。切断任意一条内部线，仍能沿其他线保持连通，故标为 1PI。
- 下图左侧两个交错的圈与右侧单圈之间只靠一段直线相连。在虚线位置切开，整图分成两块，故不属于 1PI。

![[Picture/11.2/6.jpg]]

把 $\widetilde\Delta(p^2)$ 中所有 1PI 两点图的插入部分之和记为 $i\Sigma(p^2)$，板书标作 **self-energy**（自能）。圆块两边的箭头标明同一动量 $p$。精确传播子依次展开为自由线、插入一个圆块的线、串联两个圆块的线、……。逐图写成

$$
\begin{aligned}
\widetilde\Delta(p^2)
={}&\widetilde D_F(p^2)\\
&+\widetilde D_F(p^2)\,i\Sigma(p^2)\,\widetilde D_F(p^2)\\
&+\widetilde D_F(p^2)\,i\Sigma(p^2)\,\widetilde D_F(p^2)\,
  i\Sigma(p^2)\,\widetilde D_F(p^2)+\cdots .
\end{aligned}
$$

![[Picture/11.2/7.jpg]]

从左端提出自由传播子，按插入数 $n$ 求和：

$$
\begin{aligned}
\widetilde\Delta(p^2)
&=\widetilde D_F(p^2)\sum_{n=0}^{\infty}
  \left[i\Sigma(p^2)\widetilde D_F(p^2)\right]^n\\
&=\frac{-i}{p^2+m^2-i\epsilon}\sum_{n=0}^{\infty}
  \left[\frac{\Sigma(p^2)}{p^2+m^2-i\epsilon}\right]^n\\
&=\frac{-i}{(p^2+m^2-i\epsilon)
  \left(1-\dfrac{\Sigma}{p^2+m^2-i\epsilon}\right)} .
\end{aligned}
$$

> 此处使用了板书右上角的几何级数 $\sum_{n=0}^{\infty}x^n=1/(1-x)$。在上述微扰展开中按形式幂级数求和。

整理分母即得框出的结果：

$$
\boxed{\widetilde\Delta(p^2)=
\frac{-i}{p^2+m^2-i\epsilon-\Sigma(p^2)} .}
$$

同板红字回顾一点函数的重整化条件，并用箭头连到系数 $Y$：

$$
\langle\Omega|\phi(x)|\Omega\rangle=0 .
$$

## 解释

每多插入一个 1PI 圆块，就多一个 $i\Sigma$ 和一段自由传播子。已经由单条内部线串起的多个圆块由乘积项生成，因而不再计入单个圆块的定义。

# 4. 两点函数的重整化条件

对应图片：8、9

## 板书整理

![[Picture/11.2/8.jpg]]

板书将“两点函数”与“传播子”相连，并依次要求它有指定的极点和留数。

**极点位置**　令 $p^2=-m_{\rm ph}^2$，取 $\epsilon=0$。第一行原式为

$$
\widetilde\Delta^{-1}(-m_{\rm ph}^2)=0
=-m_{\rm ph}^2+m^2-\Sigma(-m_{\rm ph}).
$$

随后板书框出

$$
\boxed{m^2=m_{\rm ph}^2+\Sigma(-m_{\rm ph}^2).}
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图 8，极点条件第一行最右端。
>
> 板书内容：第一行写 $\Sigma(-m_{\rm ph})$，下一行框内写 $\Sigma(-m_{\rm ph}^2)$。
>
> 检查结果：第一行的自变量疑似漏写平方。
>
> 说明：图 7 定义的自能以 $p^2$ 为自变量，在极点应代入 $p^2=-m_{\rm ph}^2$。求零点时可直接令传播子的分母为零。
>
> 注意：以上为检查提示，未修改原板书内容。

**留数**　归一化后的留数为 $-i$。取 $\epsilon=0$，于是

$$
\lim_{p^2\to-m_{\rm ph}^2}(p^2+m_{\rm ph}^2)
\widetilde\Delta(p^2)=-i
$$

给出

$$
\lim_{p^2\to-m_{\rm ph}^2}
\frac{p^2+m_{\rm ph}^2}{p^2+m^2-\Sigma(p^2)}=1 .
$$

![[Picture/11.2/9.jpg]]

上式的分子与分母在极点同时为零。板书在箭头上标注洛必达法则（L’Hôpital），分别对 $p^2$ 求导：

$$
\lim_{p^2\to-m_{\rm ph}^2}\frac{1}{1-\Sigma'(p^2)}=1,
\qquad
\Sigma'(p^2)\equiv\frac{d\Sigma(p^2)}{d(p^2)} .
$$

由此得到第二个条件：

$$
\boxed{\Sigma'(-m_{\rm ph}^2)=0 .}
$$

图 9 下半转入反项（counter-terms）：为满足这些重整化条件，需要在拉格朗日量中加入新的项，具体形式接图 10。

## 解释

第一个条件使传播子的分母在指定质量处为零。第二个条件固定分母在同一点的斜率，因为对简单极点而言，这个斜率决定留数。

# 5. 反项拉格朗日量与顶点

对应图片：10、11

## 板书整理

![[Picture/11.2/10.jpg]]

引入 $Z_\phi,Z_m$，将拉格朗日量写成两种等价形式：

$$
\begin{aligned}
\mathcal L
&=-\frac12 Z_\phi(\partial\phi)^2
  -\frac12 Z_m m^2\phi^2+Y\phi-V_{\rm int}(\phi)\\
&=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2
  -V_{\rm int}(\phi)+\mathcal L_{\rm ct}.
\end{aligned}
$$

其中反项拉格朗日量为

$$
\mathcal L_{\rm ct}\equiv
-\frac12\underbrace{(Z_\phi-1)}_{\equiv\,\delta_\phi}(\partial\phi)^2
-\frac{m^2}{2}\underbrace{(Z_m-1)}_{\equiv\,\delta_m}\phi^2+Y\phi .
$$

![[Picture/11.2/11.jpg]]

线性项 $Y\phi$ 给出单腿顶点，图中直线终止在一个带叉的圆圈，顶点因子为 $iY$。同样，含 $\delta_\phi,\delta_m$ 的反项给出一个双腿顶点。动量 $p$ 从左流入圆叉，从右以同一动量流出，顶点因子为

$$
\boxed{-i\left(\delta_\phi p^2+\delta_m m^2\right).}
$$

这个顶点本身是 1PI，因而对自能插入 $i\Sigma(p^2)$ 有贡献。

## 解释

一点函数的条件对应单腿顶点。两点顶点中的 $\delta_\phi$ 项正比于 $p^2$，可以改变分母的斜率；$\delta_m m^2$ 是常数项，可以与前者一起调整极点位置。

# 6. 维数正则化与质量量纲

对应图片：12、13、14、15

## 板书整理

![[Picture/11.2/12.jpg]]

**维数正则化**（dimensional regularization，简称 dimreg）。圈计算中会遇到形如

$$
\int\frac{d^4p}{(2\pi)^4}\,f(p^2)
$$

的积分。当 $|p^\mu|\to\infty$ 时，这类积分常会发散，称为**紫外发散**。形式上，可以通过降低维数 $d$ 使积分收敛。

![[Picture/11.2/13.jpg]]

将时空维数定义为

$$
d=4-\varepsilon ,
$$

在计算的最后考虑 $\varepsilon\to0$。

**说明 ①　耦合常数依赖于维数 $d$。** 板书从作用量出发：

$$
S=\int d^dx\left[
-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2
-\frac{g}{n!}\phi^n
\right].
$$

作用量 $S$ 无量纲。记号 $[X]$ 表示 $X$ 的质量量纲。

![[Picture/11.2/14.jpg]]

由质量和作用量的量纲出发，板书列出

$$
\begin{aligned}
[m]&=1, & [S]&=0,\\
[p^\mu]&=1 && (E=m,\ c\equiv1),\\
[x^\mu]&=-1 && (\hbar\equiv1).
\end{aligned}
$$

由质量项得到场的量纲：

$$
[m^2\phi^2]=d=2+2[\phi]
\quad\Longrightarrow\quad
\boxed{[\phi]=\frac{d-2}{2}.}
$$

再对相互作用项作相同的量纲计数：

$$
\begin{aligned}
[g\phi^n]&=d=[g]+n[\phi],\\
d&=[g]+n\frac{d-2}{2}
\quad\Longrightarrow\quad
\boxed{[g]=d-n\frac{d-2}{2}.}
\end{aligned}
$$

![[Picture/11.2/15.jpg]]

代入 $d=4-\varepsilon$，等价地有

$$
\boxed{[g]=4-n+\left(\frac{n-2}{2}\right)\varepsilon .}
$$

为了在任意 $d$ 下使用质量量纲均为 $[g]=4-n$ 的新耦合常数，板书作替换

$$
\boxed{g\longrightarrow g\,\mu^{\left(\frac{n-2}{2}\right)\varepsilon}},
\qquad [\mu]=1 .
$$

这里 $\mu$ 称为**重整化标度**（renormalization scale）。

## 解释

图 14 的 $E=m$ 是自然单位下的静止能量关系，在此用来说明能量与质量的量纲相同。$d^dx$ 的质量量纲为 $-d$，所以被积的拉格朗日密度各项都须有量纲 $d$。替换箭头两侧沿用同一个字母 $g$：右侧的新 $g$ 保留四维量纲，$\mu$ 的幂提供从四维延拓到 $d$ 维所需的额外量纲。此处的 $\varepsilon=4-d$ 调节积分维数，前文传播子中的 $i\epsilon$ 指定极点处方。

# 7. 正则化结果中的发散项

对应图片：16

## 板书整理

![[Picture/11.2/16.jpg]]

**说明 ②**　板书指出，由于原积分发散，使用维数正则化所得的结果必含正比于

$$
\frac{1}{\varepsilon^p}
$$

的项，并将其与 Pauli–Villars 正则化中正比于 $M^p$ 的项类比。这些发散项可以被反项吸收，从而得到有限的可观测量。

> [!warning]
> **板书检查提醒**
>
> 位置：图 16，关于维数正则化结果“必含”极点的表述。
>
> 板书内容：原积分发散，结果必含正比于 $1/\varepsilon^p$ 的项。
>
> 检查结果：若将此句理解成对任意发散积分的断言，适用范围过宽。
>
> 说明：这里讨论的是在 $d=4$ 的延拓结果中留下紫外极点的情形。例如，无尺度积分在维数正则化中可为零。与 $M^p$ 的比较指两种方案都能标记发散，两个幂次没有逐项对应关系。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

$\varepsilon\to0$ 对应回到四维。若某个圈积分含有 $\varepsilon$ 的负次幂，就要把它与同阶反项贡献合并，再对可观测量取四维极限。

# 本节知识结构

LSZ 截除外线，自由传播子的极点  
↓  
外线圈修正与精确两点函数，极点定义物理质量，场的归一化固定留数  
↓  
识别 1PI 两点图，将自能插入串联求和  
↓  
用极点位置和留数约束自能及其导数  
↓  
在拉格朗日量中引入反项，写出单腿和双腿顶点  
↓  
延拓到 $d=4-\varepsilon$，由作用量求场和耦合常数的质量量纲  
↓  
引入标度 $\mu$，用反项吸收紫外极点，得到有限可观测量

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $i\int d^4x\,e^{ip\cdot x}(p^2+m^2)$ | LSZ 公式中图示外线的截除因子 |
| $\Delta(x-y)=\langle\Omega\vert T\{\phi(x)\phi(y)\}\vert\Omega\rangle$ | 精确传播子的定义 |
| $\widetilde D_F(p^2)=-i/(p^2+m^2-i\epsilon)$ | 动量空间自由传播子 |
| $\widetilde\Delta(p^2)\sim-iZ/(p^2+m_{\rm ph}^2-i\epsilon)$ | 物理质量极点附近的精确传播子 |
| $\langle\vec p\,;t\vert\phi(x)\vert\Omega\rangle=e^{-ip\cdot x}\ \Rightarrow\ Z=1$ | 固定单粒子极点的留数 |
| $\widetilde\Delta=\widetilde D_F\sum_{n=0}^{\infty}(i\Sigma\widetilde D_F)^n$ | 自能插入的几何级数，各因子取同一 $p^2$ |
| $\widetilde\Delta(p^2)=-i/[p^2+m^2-i\epsilon-\Sigma(p^2)]$ | 自能求和后的精确传播子 |
| $\langle\Omega\vert\phi(x)\vert\Omega\rangle=0$ | 一点函数的重整化条件 |
| $m^2=m_{\rm ph}^2+\Sigma(-m_{\rm ph}^2)$ | 物理极点的位置条件 |
| $\lim_{p^2\to-m_{\rm ph}^2}(p^2+m_{\rm ph}^2)\widetilde\Delta=-i\ \Rightarrow\ \Sigma'(-m_{\rm ph}^2)=0$ | 留数条件，这里取 $\epsilon=0$ |
| $\delta_\phi=Z_\phi-1,\quad\delta_m=Z_m-1$ | 动能项与质量项的反项系数 |
| $\mathcal L_{\rm ct}=-\tfrac12\delta_\phi(\partial\phi)^2-\tfrac{m^2}{2}\delta_m\phi^2+Y\phi$ | 反项拉格朗日量 |
| $iY,\quad-i(\delta_\phi p^2+\delta_m m^2)$ | 单腿、双腿反项顶点因子 |
| $d=4-\varepsilon,\quad\varepsilon\to0$ | 维数正则化与四维极限 |
| $[\phi]=(d-2)/2,\quad [g]=d-n(d-2)/2$ | $\phi^n$ 相互作用中场与耦合常数的质量量纲 |
| $[g]=4-n+(n-2)\varepsilon/2$ | 用 $\varepsilon$ 表示原耦合的量纲 |
| $g\to g\,\mu^{(n-2)\varepsilon/2},\quad[\mu]=1$ | 用重整化标度补足量纲，使新耦合保持四维量纲 |
| $1/\varepsilon^p$ | 维数正则化结果中的极点形式 |

# 板书完整性与数学检查

图 1 至图 16 编号连续，均在对应段落附有原图。图 1 的动量定向、图 8 的自变量及图 16 的适用范围已在原式旁标注；图 4 留作习题的归一化推导按板书保留。
