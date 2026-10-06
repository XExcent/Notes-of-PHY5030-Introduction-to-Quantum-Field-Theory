---
title: "量子场论导论 Lecture 4.1"
date: 2026-10-02
tags:
  - 量子场论导论
  - lecture
  - Noether定理
  - 能量动量张量
  - 外源
  - Klein-Gordon场
  - Yukawa势
  - 场量子化
source: "课堂板书"
---

# Lecture 4.1: 能量动量张量、外源与标量场

## 本节内容概览

本节从上节课的 Hamiltonian、Noether 定理、$U(1)$ 对称性和时空平移不变性出发，整理时空平移对应的 Noether 流及能量动量张量。随后引入外部源，先以电动力学为例说明源项如何进入运动方程，再求解带静态点源的 Klein–Gordon 场，得到 Yukawa 势及其无质量极限的 Coulomb 势。最后开始自由实 Klein–Gordon 场的平面波展开，并由实场条件确定正、负频系数之间的关系。

# 1. 时空平移与能量动量张量

## 1.1 上节课回顾与平移变换

![[4.1/1.jpg]]

上节课讨论了：

- Hamiltonian；
- Noether theorem；
- $U(1)$ symmetry；
- spacetime translation invariance。

对四维时空平移，板书取

$$
x^\mu\longrightarrow x'^{\mu}=x^\mu+a^\mu,
\qquad \mu\in\{0,1,2,3\},
$$

因此有四个独立的平移参数（四个连续对称性）。标量场在同一点坐标表示下的无穷小变换为

$$
\phi(x)\longrightarrow \phi(x+a)
=\phi(x)+a^\mu\partial_\mu\phi(x),
$$

所以平移方向为 $\nu$ 时，场的变分可记为

$$
\Delta_{a,\nu}=\partial_\nu\phi.
$$

这里要区分两种写法：$\phi'(x)=\phi(x)$ 表示在同一个坐标 $x$ 比较场，而 $\phi'(x')=\phi(x)$ 是把坐标也变换后的关系。拉格朗日密度是标量，故

$$
\mathcal L(x)\longrightarrow \mathcal L(x+a)
=\mathcal L(x)+a^\mu\partial_\mu\mathcal L.
$$

作用量为

$$
S=\int d^4x\,\mathcal L,
$$

平移变换满足 $d^4x'=d^4x$，因而 $S\to S$。板书还指出，Lorentz 变换也满足 $|\det\Lambda|=1$，因此在相应条件下作用量同样保持不变。

## 1.2 Noether 流的指标标记

![[4.1/2.jpg]]

平移参数的上标是一个标签。将每个平移方向 $\nu$ 单独标记，有

$$
a^\mu\partial_\mu\mathcal L
=a^\nu\partial_\mu\!\left(\mathcal L\,\delta^\mu{}_{\nu}\right)
\equiv a^\nu\partial_\mu K^\mu{}_{a,\nu},
$$

其中可取

$$
K^\mu{}_{a,\nu}=\delta^\mu{}_{\nu}\mathcal L.
$$

一般 Noether 流

$$
j^\mu_\epsilon
=\frac{\partial\mathcal L}
{\partial(\partial_\mu\phi)}\,\Delta_\epsilon
-K^\mu_\epsilon
$$

在平移对称性下写成

$$
j^\mu{}_{a,\nu}
=\frac{\partial\mathcal L}
{\partial(\partial_\mu\phi)}\,\partial_\nu\phi
-\delta^\mu{}_{\nu}\mathcal L.
$$

板书把这四个流称为 four Noether currents，并引入能量动量张量的符号约定

$$
\bar T^\mu{}_{\nu}
\equiv \mathcal L\,\delta^\mu{}_{\nu}
-\frac{\partial\mathcal L}
{\partial(\partial_\mu\phi)}\,\partial_\nu\phi,
\qquad
j^\mu{}_{a,\nu}=-\bar T^\mu{}_{\nu}.
$$

在后续能量和动量的定义中，板书使用等价的升降指标记号 $T^{\mu}{}_{\nu}$，并给出守恒方程

$$
\partial_\mu j^\mu{}_{a,\nu}=0
\quad\Longrightarrow\quad
\partial_\mu T^\mu{}_{\nu}=0.
$$

> [!warning] 板书符号约定
> 图 2 中 $j^\mu{}_{a,\nu}$、$\bar T^\mu{}_{\nu}$ 与 $T^\mu{}_{\nu}$ 的整体负号和指标位置随板书约定变化。以下保留板书的定义，并在能量、动量处明确使用的分量；不要在不同约定之间直接混用。

## 1.3 Noether 荷、能量与动量

![[4.1/3.jpg]]

Noether 荷定义为

$$
Q_\epsilon\equiv\int d^3x\,j^0_\epsilon.
$$

由

$$
\partial_\mu j^\mu{}_{a,\nu}=0
$$

得到能量动量张量的守恒方程

$$
\boxed{\partial_\mu T^\mu{}_{\nu}=0}.
$$

时间平移（$\nu=0$）给出

$$
\int d^3x\,j^0{}_{a,0}
=-\int d^3x\,T^0{}_0
=\int d^3x\,T^{00}
\equiv E,
$$

其中 $E$ 是系统总能量。空间平移（$\nu=i=1,2,3$）给出

$$
\int d^3x\,j^0{}_{a,i}
=-\int d^3x\,T^0{}_i
\equiv -P_i,
$$

从而

$$
\boxed{P^i=\int d^3x\,T^{0i}}.
$$

## 1.4 能量密度、动量密度与 Hamiltonian

![[4.1/4.jpg]]

板书给出分量的物理解释：

$$
T^{00}\quad\longrightarrow\quad\text{energy density},
$$

$$
T^{0i}\quad\longrightarrow\quad
\text{momentum density in direction }i.
$$

在每个 on-shell（满足场的物理构型）条件下，能量 $E$ 与 Hamiltonian $H$ 相同，而不是把场当作任意函数时的形式恒等式。对标量场，令

$$
\pi\equiv\frac{\partial\mathcal L}{\partial(\partial_0\phi)}=\dot\phi,
$$

则

$$
T^{00}=-T^0{}_0
=\frac{\partial\mathcal L}{\partial(\partial_0\phi)}\,\partial_0\phi-\mathcal L
=\pi\dot\phi-\mathcal L
\equiv\mathcal H.
$$

积分后

$$
\boxed{\int d^3x\,T^{00}=\int d^3x\,\mathcal H\equiv H}.
$$

## 1.5 动量的空间表达式

![[4.1/5.jpg]]

对自由标量场，板书把动量写成

$$
\boxed{\vec P=-\int d^3x\,\pi\,\vec\nabla\phi}.
$$

右上角标注为 exercise。这个式子应与上一节采用的 $T^{0i}$ 指标、度规号差约定一起使用。

# 2. 外部源与电动力学例子

## 2.1 外部源的拉格朗日量

![[4.1/6.jpg]]

外部源（external source）代表独立于场本身的物理作用。总拉格朗日密度写为

$$
\mathcal L_{\mathrm{tot}}
=\mathcal L[\phi]+\phi\,\bar J(x),
$$

其中 $\bar J(x)$ 是外部源。对电动力学，板书取

$$
\mathcal L_{\mathrm{tot}}
=-\frac14F^{\mu\nu}F_{\mu\nu}+A_\mu J^\mu.
$$

对 $A_\nu$ 使用 Euler–Lagrange 方程得到

$$
\boxed{\partial_\mu F^{\mu\nu}+J^\nu=0}.
$$

四维电流的分量解释为

$$
F^{0i}=E^i\quad(\text{electric field}),
$$

$$
F^{ij}=\epsilon^{ij}{}_{k}B^k
\quad(\text{magnetic field}),
$$

$$
J^0=\rho\quad(\text{charge density}),
\qquad
\vec J\quad(\text{electric 3-current}).
$$

## 2.2 Maxwell 方程的分量形式

![[4.1/7.jpg]]

取 $\nu=0$：

$$
\partial_iF^{i0}+J^0=0
\quad\Longrightarrow\quad
-\vec\nabla\cdot\vec E+\rho=0.
$$

取 $\nu=j$：

$$
\partial_0F^{0j}+\partial_iF^{ij}+J^j=0.
$$

板书将空间项写成

$$
\partial_0F^{0j}=\frac{\partial E^j}{\partial t},
\qquad
\partial_iF^{ij}
=-\epsilon^{ij}{}_{k}\partial_iB^k
=-(\vec\nabla\times\vec B)^j,
$$

因此

$$
\boxed{\frac{\partial\vec E}{\partial t}
-\vec\nabla\times\vec B+\vec J=0}.
$$

> [!warning] 度规和场强张量约定
> 图 6--7 的正负号依赖 $F^{0i}$、$F^{ij}$ 以及度规号差的约定。此处原样记录板书的约定；若与其他章节采用的 Maxwell 方程符号不同，应先统一约定再比较。

# 3. 静态点源产生的标量场

## 3.1 运动方程与空间 Fourier 变换

![[4.1/8.jpg]]

考虑带有静态点源的实标量场：

$$
\mathcal L_{\mathrm{tot}}
=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2+\phi\,\bar J,
\qquad
\bar J(x)\equiv\alpha\,\delta^3(\vec x),
$$

其中 $\alpha$ 为常数。Euler–Lagrange 方程为

$$
\boxed{\Box\phi-m^2\phi=-\alpha\,\delta^3(\vec x)}.
$$

寻找在 $|\vec x|\to\infty$ 足够快衰减的静态特殊解。采用三维 Fourier 变换

$$
\phi(\vec x)
=\int\frac{d^3k}{(2\pi)^3}\,\phi_{\vec k}\,
e^{i\vec k\cdot\vec x},
\qquad
\phi_{\vec k}
=\int d^3x\,\phi(\vec x)e^{-i\vec k\cdot\vec x}.
$$

## 3.2 求出动量空间解

![[4.1/9.jpg]]

所需的 delta 函数 Fourier 表示为

$$
\delta^3(\vec x)
=\int\frac{d^3k}{(2\pi)^3}e^{i\vec k\cdot\vec x},
\qquad
\delta^4(x)
=\int\frac{d^4k}{(2\pi)^4}e^{ik\cdot x}.
$$

静态场满足 $\partial_t\phi=0$，因此

$$
\Box\phi=\vec\nabla^2\phi
=-\int\frac{d^3k}{(2\pi)^3}
\phi_{\vec k}|\vec k|^2e^{i\vec k\cdot\vec x}.
$$

代入运动方程，逐个 Fourier 模式满足

$$
-\phi_{\vec k}|\vec k|^2-m^2\phi_{\vec k}=-\alpha,
$$

故

$$
\boxed{\phi_{\vec k}=\frac{\alpha}{|\vec k|^2+m^2}}.
$$

于是

$$
\phi(\vec x)
=\alpha\int\frac{d^3k}{(2\pi)^3}
\frac{e^{i\vec k\cdot\vec x}}{|\vec k|^2+m^2}.
$$

取球对称坐标

$$
\vec x=(0,0,r),
\qquad
\vec k=|\vec k|(\sin\theta\cos\varphi,
\sin\theta\sin\varphi,\cos\theta),
$$

则 $\vec k\cdot\vec x=kr\cos\theta$，其中 $k=|\vec k|$。

## 3.3 角向积分与复变积分

![[4.1/10.jpg]]

球坐标积分给出

$$
\begin{aligned}
\phi(r)
&=\alpha\frac{2\pi}{(2\pi)^3}
\int_0^\infty k^2dk\int_0^\pi\sin\theta\,d\theta\,
\frac{e^{ikr\cos\theta}}{k^2+m^2}\\
&=\frac{\alpha}{4\pi^2}
\int_0^\infty dk\,\frac{k^2}{k^2+m^2}
\int_{-1}^{1}d(\cos\theta)e^{ikr\cos\theta}\\
&=-\frac{i\alpha}{4\pi^2r}
\int_{-\infty}^{\infty}dk\,
\frac{k e^{ikr}}{k^2+m^2}.
\end{aligned}
$$

其中角向积分为

$$
\int_{-1}^{1}du\,e^{ikru}
=\frac{e^{ikr}-e^{-ikr}}{ikr}.
$$

为了将 $k\in[0,\infty)$ 的积分写成全实轴积分，对含 $e^{-ikr}$ 的部分作 $k\to-k$。当 $r>0$ 时，复平面轮廓闭合在上半平面；被积函数的极点为

$$
k=\pm im,
$$

上半平面内只有 $k=im$。

![[4.1/11.jpg]]

由留数定理

$$
\begin{aligned}
\phi(r)
&=-\frac{i\alpha}{4\pi^2r}(2\pi i)
\operatorname*{Res}_{k=im}
\frac{k e^{ikr}}{k^2+m^2},\\
\operatorname*{Res}_{k=im}
\frac{k e^{ikr}}{k^2+m^2}
&=\left.\frac{k e^{ikr}}{k+im}\right|_{k=im}
=\frac{im\,e^{-mr}}{2im}
=\frac12e^{-mr}.
\end{aligned}
$$

最终得到

$$
\boxed{\phi(r)=\frac{\alpha}{4\pi}\frac{e^{-mr}}{r}}.
$$

这就是 Yukawa potential。当 $m=0$ 时，退化为

$$
\boxed{\phi(r)=\frac{\alpha}{4\pi}\frac1r},
$$

即 Coulomb potential。

# 4. 自由 Klein–Gordon 场的平面波展开

## 4.1 一般平面波解

![[4.1/12.jpg]]

自由实标量场满足 Klein–Gordon 方程

$$
\boxed{\Box\phi-m^2\phi=0},
\qquad \phi=\phi^*.
$$

一般解是平面波的叠加。三维 Fourier 展开写为

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3}
\,\mu_{\vec p}(t)\,a_{\vec p}\,e^{i\vec p\cdot\vec x},
$$

其中 $\mu_{\vec p}(t)$ 是与时间有关的 mode function，$a_{\vec p}$ 是与时间无关的展开系数；也可把每个动量模记为

$$
\phi_{\vec p}(t)=\mu_{\vec p}(t)a_{\vec p}.
$$

## 4.2 时间模方程

![[4.1/13.jpg]]

使用

$$
\Box=-\partial_t^2+\vec\nabla^2
$$

代入 Fourier 展开，得到

$$
-\ddot\mu_{\vec p}
-|\vec p|^2\mu_{\vec p}
-m^2\mu_{\vec p}=0.
$$

令

$$
\omega_{\vec p}\equiv\sqrt{|\vec p|^2+m^2},
$$

时间模的通解为

$$
\mu_{\vec p}(t)
=A_{\vec p}e^{-i\omega_{\vec p}t}
+B_{\vec p}e^{i\omega_{\vec p}t},
$$

其中 $A_{\vec p}$、$B_{\vec p}$ 是积分常数。因此

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3}
\left[
A_{\vec p}a_{\vec p}e^{-i\omega_{\vec p}t+i\vec p\cdot\vec x}
+B_{\vec p}a_{\vec p}e^{i\omega_{\vec p}t+i\vec p\cdot\vec x}
\right].
$$

## 4.3 归一化与动量变量替换

![[4.1/14.jpg]]

由于 $A_{\vec p}$、$B_{\vec p}$ 和 $a_{\vec p}$ 的分配并不唯一，板书重新定义系数

$$
A_{\vec p}a_{\vec p}\equiv
\frac{1}{\sqrt{2\omega_{\vec p}}}a_{\vec p},
\qquad
B_{\vec p}a_{\vec p}\equiv
\frac{1}{\sqrt{2\omega_{\vec p}}}b_{\vec p}.
$$

于是

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_{\vec p}}}
\left[
a_{\vec p}e^{-i\omega_{\vec p}t+i\vec p\cdot\vec x}
+b_{\vec p}e^{i\omega_{\vec p}t+i\vec p\cdot\vec x}
\right].
$$

对第二项作变量替换 $\vec p\to-\vec p$。由于积分区域为整个动量空间，$\int d^3p$ 在该替换下不变，且 $\omega_{-\vec p}=\omega_{\vec p}$，所以第二项可改写为带有 $b_{-\vec p}$ 的负动量模式。

## 4.4 实场条件

![[4.1/15.jpg]]

对上式取复共轭，并在相应项中作 $\vec p\to-\vec p$，有

$$
\phi^*(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_{\vec p}}}
\left[
b^*_{-\vec p}e^{-i\omega_{\vec p}t+i\vec p\cdot\vec x}
+a^*_{-\vec p}e^{i\omega_{\vec p}t+i\vec p\cdot\vec x}
\right].
$$

要求实标量场满足 $\phi^*(x)=\phi(x)$，比较正频率和负频率项，得到

$$
b^*_{-\vec p}=a_{\vec p},
\qquad
a^*_{-\vec p}=b_{\vec p}.
$$

这两个关系互相等价，板书将其概括为

$$
\boxed{b^*_{-\vec p}=a_{\vec p}}.
$$

## 4.5 实标量场的最终展开

![[4.1/16.jpg]]

代入实场条件后，最终的自由实 Klein–Gordon 场展开为

$$
\boxed{
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_{\vec p}}}
\left[
a_{\vec p}e^{-i\omega_{\vec p}t+i\vec p\cdot\vec x}
+a^*_{-\vec p}e^{i\omega_{\vec p}t+i\vec p\cdot\vec x}
\right]
}.
$$

第二项是第一项的复共轭形式（在动量变量作适当替换后），因此该展开满足 $\phi=\phi^*$。

# 本节知识结构

时空平移不变性
$\rightarrow$ Noether 流与能量动量张量
$\rightarrow$ 能量、动量及 Hamiltonian
$\rightarrow$ 外部源与场的耦合
$\rightarrow$ 静态点源的 Klein–Gordon 方程
$\rightarrow$ Fourier 积分与留数定理
$\rightarrow$ Yukawa 势及 Coulomb 极限
$\rightarrow$ 自由实标量场的平面波展开
$\rightarrow$ 实场条件 $b^*_{-\vec p}=a_{\vec p}$。

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $j^\mu_\epsilon=\dfrac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\Delta_\epsilon-K^\mu_\epsilon$ | 一般 Noether 流 |
| $K^\mu{}_{a,\nu}=\delta^\mu{}_{\nu}\mathcal L$ | 平移变换的全导数项 |
| $j^\mu{}_{a,\nu}=\dfrac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\partial_\nu\phi-\delta^\mu{}_{\nu}\mathcal L$ | 平移 Noether 流 |
| $\partial_\mu T^\mu{}_{\nu}=0$ | 能量动量守恒 |
| $E=\int d^3x\,T^{00}$ | 总能量 |
| $P^i=\int d^3x\,T^{0i}$ | 总动量 |
| $\vec P=-\int d^3x\,\pi\vec\nabla\phi$ | 标量场动量（板书约定） |
| $\partial_\mu F^{\mu\nu}+J^\nu=0$ | 带电流的电动力学方程 |
| $\phi_{\vec k}=\dfrac{\alpha}{\lvert\vec k\rvert^2+m^2}$ | 静态点源的动量空间解 |
| $\phi(r)=\dfrac{\alpha}{4\pi}\dfrac{e^{-mr}}r$ | Yukawa 势 |
| $\phi(r)\big\vert_{m=0}=\dfrac{\alpha}{4\pi r}$ | Coulomb 势极限 |
| $\omega_{\vec p}=\sqrt{\lvert\vec p\rvert^2+m^2}$ | Klein–Gordon 模的频率 |
| $b^*_{-\vec p}=a_{\vec p}$ | 实场条件 |

# 推导逻辑与内容正确性检查

- 平移对称性先给出四个带空间时间指标的 Noether 流，再通过 $T^{00}$ 和 $T^{0i}$ 识别能量与动量密度。
- 外部源只作为给定函数耦合到场；电动力学例子中，$A_\mu J^\mu$ 产生电流源项。
- 静态点源问题先在动量空间代数求解，再经球坐标角积分和上半平面留数积分返回位置空间。
- $m\neq0$ 时的极点 $k=im$ 产生 $e^{-mr}$，而 $m=0$ 恢复 $1/r$ 长程势。
- 自由实标量场的正、负频率模式先独立展开，最后由 $\phi^*=\phi$ 把它们联系起来。

# 检查报告

## 严重问题

- 暂未发现可以在不改变板书约定的情况下确定的推导断裂。

## 疑似符号问题

- 图 2--4 中 $j^\mu{}_{a,\nu}$、$\bar T^\mu{}_{\nu}$、$T^\mu{}_{\nu}$ 的整体负号和指标升降依赖约定；图 3--4 通过 $T^{00}=-T^0{}_0$ 定义能量。使用其他教材时需要先统一度规和张量定义。
- 图 6--7 中 $F^{0i}=E^i$、$F^{ij}=\epsilon^{ij}{}_kB^k$ 与 Maxwell 方程的正负号必须配套；笔记保留板书原式，没有替换成另一套约定。
- 图 14--16 重新使用 $a_{\vec p}$ 表示归一化后的系数。为避免与最初的 Fourier 系数混淆，阅读时应以最终展开式中的 $a_{\vec p}$ 为准。

## 需要人工确认

- 若课程前文已经固定了不同的度规号差、$F^{\mu\nu}$ 定义或能量动量张量符号，应回看前文并统一本节公式。
- 图 2 中上方关于 $a^\mu\partial_\mu\mathcal L$ 的中间等式是指标标记步骤，若要与某一特定教材的 $K^\mu{}_{\nu}$ 定义逐项对照，应以原图确认指标位置。

## 总体评价

本节板书完整覆盖了时空平移的 Noether 守恒量、外部源、Yukawa 势和自由实标量场展开。主要复核风险集中在张量符号、度规约定以及 Fourier 归一化；这些位置已保留原式并作出检查提示。
