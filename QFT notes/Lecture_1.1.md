---
title: "量子场论导论 Lecture 01"
date: 2026-09-23
tags:
  - 量子场论导论
  - lecture
  - Klein-Gordon方程
  - Fock空间
source: "课堂板书"
---

# Lecture 01: 为什么需要量子场论

## 本节内容概览

本节从量子力学与相对论的结合出发，说明为什么需要用量子场论描述自然。课堂依次讨论了相对论性薛定谔方程的非局域性、平方根哈密顿量导致的负能量解，以及概率密度难以保持正定这三个困难。随后得到 Klein–Gordon 方程，并指出其波函数不应直接解释为单粒子概率波函数。最后以自由的非相互作用粒子系统为例，引入产生、湮灭算符以及 $N$ 粒子 Hilbert 空间和 Fock 空间。

---

# 1. 为什么需要量子场论

对应图片：

- 1
- 2

## 板书整理

![[1.1/1.png]]

板书标注授课教师：**Prof. Sebastian**。

板书写出：

$$
\mathrm{QM}\ \longrightarrow\ \hat O(t)
$$

$$
\mathrm{QFT}\ \longrightarrow\ \hat O(t,\vec x)
$$

因此，在量子场论中基本对象是场（field）。量子力学与相对论结合后得到：

$$
\mathrm{QM}+\mathrm{relativity}\ \longrightarrow\ \mathrm{fields}.
$$

相对论要求时间和空间处于平等地位（time and space on equal footing）。

![[1.1/2.png]]

板书给出两个动机：

1. 相对论要求使用时空（spacetime）。
2. 相对论中粒子数不一定守恒。

静止能量为

$$
E_{\mathrm{rest}}=mc^2,
$$

能量可以转化为粒子的产生或湮灭。

而在普通量子力学中，粒子数守恒，概率归一化写作

$$
\int d^3x\,|\psi(\vec x,t)|^2=1,
$$

表示粒子必定在某处。

## 解释

量子力学通常把 $\psi$ 看成单粒子波函数；但相对论允许能量转化为粒子，因此粒子数不再适合作为始终固定的基本量。量子场论改用依赖时空的场作为基本对象，从而能够容纳粒子的产生与湮灭。

---

# 2. 相对论性薛定谔方程的尝试

对应图片：

- 3
- 4

## 板书整理

![[1.1/3.png]]

### 自由粒子的非相对论薛定谔方程

$$
i\hbar\frac{\partial\psi}{\partial t}
=-\frac{\hbar^2}{2m}\vec\nabla^{\,2}\psi
=\hat H\psi,
$$

其中

$$
\hat H=\frac{\hat{\vec p}^{\,2}}{2m},
\qquad
\hat{\vec p}=-i\hbar\vec\nabla
$$

（位置表象）。

相对论能量关系为

$$
E=\sqrt{(pc)^2+(mc^2)^2}
\simeq mc^2+\frac{p^2}{2m}+\cdots.
$$

尝试把哈密顿量改为

$$
\hat H=\sqrt{\hat{\vec p}^{\,2}c^2+(mc^2)^2}
=\sqrt{-\hbar^2c^2\vec\nabla^{\,2}+m^2c^4}.
$$

于是得到

$$
i\hbar\frac{\partial\psi}{\partial t}
=\sqrt{-\hbar^2c^2\vec\nabla^{\,2}+m^2c^4}\,\psi.
$$

![[1.1/4.png]]

### 自然单位与第一个困难

取自然单位

$$
c=1,\qquad \hbar=1,\qquad \epsilon_0=1,
$$

并有

$$
[\mathrm{mass}]=[\mathrm{frequency}]=[\mathrm{energy}]=[\mathrm{momentum}]=1,
$$

$$
[\mathrm{position}]=[\mathrm{time}]=-1.
$$

精细结构常数为

$$
\alpha=\frac{e^2}{4\pi}\simeq\frac1{137}.
$$

相对论性方程变为

$$
i\frac{\partial\psi}{\partial t}
=\sqrt{-\vec\nabla^{\,2}+m^2}\,\psi.
$$

这是一个非局域微分方程（non-local differential equation），标记为 **Trouble #1**。

板书对局部算符作如下说明：若微分算符 $\hat D$ 满足

$$
\hat Df(x)=\int dy\,K(x-y)f(y),
$$

且核 $K(x-y)$ 只在 $x=y$ 处有支撑，则称 $\hat D$ 是局部的。

## 解释

相对论能量关系含有动量的平方根。把动量替换为微分算符后，平方根算符通常不能写成有限阶的局部微分算符，因此它会把 $x$ 点的场与其他位置的场联系起来。这就是第一个困难。

---

# 3. 局部性与平方根算符

对应图片：

- 5
- 6

## 板书整理

![[1.1/5.png]]

单位算符的例子：

$$
\hat Df(x)=f(x)
=\int_{-\infty}^{\infty}dy\,\delta(x-y)f(y).
$$

这里 $δ(x-y)$ 是 Dirac delta 函数，除 $x=y$ 外为零，因此该算符是局部的。

如果核不是只在 $x=y$ 处有支撑，$\hat D$ 就是非局部的。

另一个例子是

$$
\hat D=e^{a\frac{d}{dx}},
$$

其中 $a$ 为常数。板书给出

$$
\hat Df(x)
=\sum_{n=0}^{\infty}\frac{a^n}{n!}
\left(\frac{d^n}{dx^n}f(x)\right)
=f(x+a),
$$

即把函数取到距离 $a$ 的位置，因而体现出非局域性。

![[1.1/6.png]]

为消除平方根，考虑

$$
i\frac{\partial}{\partial t}
=\sqrt{-\vec\nabla^{\,2}+m^2}.
$$

两边平方：

$$
\left(i\frac{\partial}{\partial t}\right)^2
=-\frac{\partial^2}{\partial t^2},
$$

因此

$$
-\frac{\partial^2}{\partial t^2}
=-\vec\nabla^{\,2}+m^2.
$$

## 解释

平方根哈密顿量的非局域性来自无限阶导数展开。平方操作把它转化为二阶时空微分方程，为得到局部且相对论协变的方程提供了方向。

---

# 4. Klein–Gordon 方程与负能量

对应图片：

- 7
- 8

## 板书整理

![[1.1/7.png]]

对波函数作用后得到

$$
-\frac{\partial^2\psi}{\partial t^2}
+\vec\nabla^{\,2}\psi
=m^2\psi.
\tag{1}
$$

板书将其标为速度 $c=1$ 的波动方程。一般波动方程写成

$$
-\frac{\partial^2u}{\partial t^2}
+c_s^2\vec\nabla^{\,2}u=f(t,\vec x),
$$

其中 $c_s$ 是波速，$f$ 是“力”或源项。

考虑平面波解

$$
\psi=C e^{-i\omega t+i\vec k\cdot\vec x}.
$$

![[1.1/8.png]]

将平面波代入方程 (1)：

$$
\omega^2-\vec k^{\,2}=m^2,
$$

所以

$$
\omega=\pm\sqrt{\vec k^{\,2}+m^2}.
$$

一般解可写为

$$
\psi
=A e^{-i\sqrt{\vec k^{\,2}+m^2}\,t}e^{i\vec k\cdot\vec x}
+B e^{+i\sqrt{\vec k^{\,2}+m^2}\,t}e^{i\vec k\cdot\vec x}.
$$

在经典物理中，两项都可以接受；但在量子力学中，第二项对应

$$
\hat H\psi_B
=i\frac{\partial\psi_B}{\partial t}
=-\sqrt{\vec k^{\,2}+m^2}\,\psi_B.
$$

它是负能量本征态，导致没有基态（no ground state），标记为 **Trouble #2**。

## 解释

对时间作二阶导数的方程天然包含正、负两个频率分支。若仍把 $\psi$ 当作普通单粒子薛定谔波函数，负频率分支就表现为无下界的能谱，量子力学解释遇到困难。

---

# 5. 概率守恒的困难

对应图片：

- 9
- 10
- 11
- 12

## 板书整理

![[1.1/9.png]]

### Trouble #3：没有局域的概率守恒

希望存在某个概率流 $\vec j$，使得

$$
\frac{\partial}{\partial t}|\psi|^2
=-\vec\nabla\cdot\vec j.
$$

直接计算左侧：

$$
\frac{\partial}{\partial t}|\psi|^2
=\psi^*\frac{\partial\psi}{\partial t}
+\psi\frac{\partial\psi^*}{\partial t}.
$$

由

$$
i\frac{\partial\psi}{\partial t}
=\sqrt{-\vec\nabla^{\,2}+m^2}\,\psi,
$$

以及其复共轭

$$
-i\frac{\partial\psi^*}{\partial t}
=\sqrt{-\vec\nabla^{\,2}+m^2}\,\psi^*,
$$

可得

$$
\frac{\partial}{\partial t}|\psi|^2
=-i\left[
\psi^*\sqrt{-\vec\nabla^{\,2}+m^2}\,\psi
-\psi\sqrt{-\vec\nabla^{\,2}+m^2}\,\psi^*
\right].
$$

将平方根按 $m$ 展开：

$$
\sqrt{-\vec\nabla^{\,2}+m^2}
=m\sqrt{1-\frac{\vec\nabla^{\,2}}{m^2}}
$$

$$
=m\left[
1-\frac{1}{2m^2}\vec\nabla^{\,2}
-\frac{1}{8m^4}(\vec\nabla^{\,2})^2+\cdots
\right].
$$

> 此处使用了二项式展开 $(1+z)^{1/2}=1+\frac12z-\frac18z^2+\cdots$。

于是

$$
\begin{aligned}
\frac{\partial}{\partial t}|\psi|^2
=-im\Bigg[&
\psi^*\psi-\psi\psi^*
-\frac{1}{2m^2}
\left(\psi^*\vec\nabla^{\,2}\psi
-\psi\vec\nabla^{\,2}\psi^*\right)\\
&-\frac{1}{8m^4}
\left(\psi^*(\vec\nabla^{\,2})^2\psi
-\psi(\vec\nabla^{\,2})^2\psi^*\right)+\cdots
\Bigg].
\end{aligned}
$$

常数项相消；二阶导数项可写成散度：

$$
\psi^*\vec\nabla^{\,2}\psi
-\psi\vec\nabla^{\,2}\psi^*
=\vec\nabla\cdot
\left(\psi^*\vec\nabla\psi-\psi\vec\nabla\psi^*\right).
$$

> 此处使用了乘积求导法则，将二阶导数差改写为总散度。

更高阶导数项也可以继续整理为类似的总散度形式。板书的结论是：这些项可形式上写成

$$
\frac{\partial}{\partial t}|\psi|^2
=-\vec\nabla\cdot\vec j,
$$

但对应的 $\vec j$ 包含无限阶空间导数，体现出原方程的非局域性。

![[1.1/10.png]]

板书继续将展开式中的各项整理为

$$
\vec\nabla\cdot(\psi^*\vec\nabla\psi)
-\vec\nabla\cdot(\psi\vec\nabla\psi^*)
=\vec\nabla\cdot
\left(\psi^*\vec\nabla\psi-\psi\vec\nabla\psi^*\right),
$$

并指出其余高阶项同样给出总散度，从而形式上得到量子力学中的概率守恒结构。

![[1.1/11.png]]

### 波动方程的连续性方程

板书指出，波动方程 (1) 确实有连续性方程

$$
\frac{\partial\rho}{\partial t}
=-\vec\nabla\cdot\vec j,
$$

但需要定义

$$
\rho
\equiv i\left(\psi^*\partial_t\psi
-\psi\partial_t\psi^*\right).
$$

利用

$$
\partial_t^2\psi
=\vec\nabla^{\,2}\psi-m^2\psi,
$$

有

$$
\begin{aligned}
\partial_t\rho
&=i\left(\psi^*\partial_t^2\psi
-\psi\partial_t^2\psi^*\right)\\
&=i\left[\psi^*(\vec\nabla^{\,2}-m^2)\psi
-\psi(\vec\nabla^{\,2}-m^2)\psi^*\right]\\
&=i\vec\nabla\cdot
\left(\psi^*\vec\nabla\psi
-\psi\vec\nabla\psi^*\right).
\end{aligned}
$$

因此可取

$$
\vec j
=i\left(\psi^*\vec\nabla\psi
-\psi\vec\nabla\psi^*\right).
$$

⚠️ **检查提醒：**

- 类型：推导错误
- 问题：上式给出的 $\vec j$ 与前面的连续性方程符号不一致。
- 分析：由第 469--478 行的推导，$\partial_t\rho=i\,\vec\nabla\cdot(\psi^*\vec\nabla\psi-\psi\vec\nabla\psi^*)$。若约定 $\partial_t\rho=-\vec\nabla\cdot\vec j$，则应取 $\vec j=-i(\psi^*\vec\nabla\psi-\psi\vec\nabla\psi^*)$；当前正号会得到 $\partial_t\rho=+\vec\nabla\cdot\vec j$。
- 建议：结合原始板书确认电流的整体符号，并统一连续性方程的约定。
- 置信度：高

![[1.1/12.png]]

然而，$ρ$ 不是正定的（$ρ$ is not positive definite），因此它不能作为概率密度。

结论：不可能找到一个既相对论性又具有普通概率解释的薛定谔方程。我们得到了一个好的相对论性方程

$$
-\partial_t^2\psi+\vec\nabla^{\,2}\psi=m^2\psi,
$$

但不应把 $\psi$ 解释为波函数。

## 解释

对 Klein–Gordon 方程而言，守恒量的密度是 $\rho$，而不是 $|\psi|^2$；由于 $\rho$ 可以为负，它不符合概率密度必须非负的要求。这是从单粒子波函数解释转向场的量子化的关键动机。

---

# 6. d'Alembert 算符与 Klein–Gordon 方程

对应图片：

- 13

## 板书整理

![[1.1/13.png]]

定义 d'Alembert 算符

$$
\Box\equiv-\frac{\partial^2}{\partial t^2}+\vec\nabla^{\,2}.
$$

于是方程写成

$$
\boxed{\Box\psi-m^2\psi=0},
$$

称为 Klein–Gordon equation。

板书总结：

$$
\mathrm{QM}+\mathrm{relativity}
\ \Longrightarrow\ \mathrm{QFT}
=\mathrm{QM\ of\ fields}.
$$

但逆命题不成立：存在适用于非相对论系统的量子场论。

## 解释

Klein–Gordon 方程是相对论性标量场满足的局部运动方程。其困难不在方程本身，而在于把解 $\psi$ 当作单粒子概率波函数的解释；将 $\psi$ 升格为场算符后，负频率和非正定密度会获得不同的物理含义。

---

# 7. 从多粒子量子力学到场

对应图片：

- 14
- 15
- 16

## 板书整理

![[1.1/14.png]]

考虑 $N$ 个自由的（非相互作用）相同粒子组成的非相对论系统。

哈密顿量为

$$
\hat H_S
=-\frac{1}{2m}\sum_{j=1}^{N}\vec\nabla_j^{\,2},
$$

其中

$$
\vec\nabla_j
\equiv \frac{\partial}{\partial\vec x_j},
\qquad
\vec\nabla_j^{\,2}\text{ 为相应的拉普拉斯算符},
\qquad
\vec x_j(t)：粒子\ j\ 的位置。
$$

波函数为

$$
\Psi(\vec x_1,\vec x_2,\ldots,\vec x_N,t).
$$

对应的态矢写成

$$
\begin{aligned}
|\Psi(t)\rangle\equiv{}&
\int d^3x_1\cdots d^3x_N\,
\Psi(\vec x_1,\ldots,\vec x_N,t)\\
&\times a^\dagger(\vec x_1)\cdots
a^\dagger(\vec x_N)|0\rangle.
\end{aligned}
$$

![[1.1/15.png]]

$a^\dagger(\vec x)$ 与 $a(\vec x)$ 分别是产生和湮灭算符：

- $a^\dagger(\vec x)$：在位置 $\vec x$ 产生一个粒子；
- $|0\rangle$：真空态，即零粒子态；
- $a(\vec x)|0\rangle=0$；
- $a^\dagger(\vec x)|0\rangle$：单粒子态；
- $a^\dagger(\vec x)a^\dagger(\vec y)|0\rangle$：双粒子态；
- 继续作用可得到更多粒子态。

![[1.1/16.png]]

因此

$$
|\Psi(t)\rangle
\longrightarrow N\text{-particle state},
$$

并且它是形如

$$
a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)|0\rangle
$$

的线性组合。

记 $N$ 粒子态所在的 Hilbert 空间为 $\mathcal H_N$：

$$
|\Psi(t)\rangle\in\mathcal H_N.
$$

Fock 空间定义为所有粒子数扇区的直和：

$$
\mathcal F
=\bigoplus_{N=0}^{\infty}\mathcal H_N.
$$

板书也写作：$N$ 粒子态构成 $\mathcal H_N$ 的基。

## 解释

在固定粒子数的量子力学中，态属于单个 $\mathcal H_N$。引入产生、湮灭算符后，粒子数可以改变，所有 $\mathcal H_N$ 被统一放入 Fock 空间 $\mathcal F$。这为随后把场视为算符并描述粒子产生与湮灭建立了形式基础。

---

# 本节知识结构

量子力学与相对论结合
↓
场作为依赖 $(t,\vec x)$ 的基本对象
↓
相对论性薛定谔方程的三个困难：非局域性、负能量、非正定概率密度
↓
Klein–Gordon 方程
↓
产生/湮灭算符
↓
$N$ 粒子 Hilbert 空间 $\mathcal H_N$
↓
Fock 空间 $\mathcal F=\bigoplus_{N=0}^{\infty}\mathcal H_N$

# 核心公式清单

|公式|含义|
|-|-|
|$E_{\mathrm{rest}}=mc^2$|静止能量，可用于说明能量与粒子产生/湮灭的联系|
|$\int d^3x\,|\psi|^2=1$|普通量子力学中的概率归一化|
|$i\partial_t\psi=\sqrt{-\vec\nabla^{\,2}+m^2}\,\psi$|自然单位下的相对论性平方根方程|
|$\hat Df(x)=\int dy\,K(x-y)f(y)$|用核表示一般算符；核只在 $x=y$ 有支撑时为局部|
|$e^{a\frac d{dx}}f(x)=f(x+a)$|无限阶微分算符产生有限距离的平移|
|$-\partial_t^2\psi+\vec\nabla^{\,2}\psi=m^2\psi$|由平方根方程平方得到的 Klein–Gordon 形式|
|$\omega^2-\vec k^{\,2}=m^2$|Klein–Gordon 平面波的色散关系|
|$\rho=i(\psi^*\partial_t\psi-\psi\partial_t\psi^*)$|Klein–Gordon 方程的守恒密度，但不是正定概率密度|
|$\vec j=i(\psi^*\vec\nabla\psi-\psi\vec\nabla\psi^*)$|与上述守恒密度对应的流|
|$\Box=-\partial_t^2+\vec\nabla^{\,2}$|d'Alembert 算符|
|$\Box\psi-m^2\psi=0$|Klein–Gordon 方程|
|$\hat H_S=-\frac1{2m}\sum_{j=1}^N\vec\nabla_j^{\,2}$|$N$ 个自由非相互作用粒子的哈密顿量|
|$\mathcal F=\bigoplus_{N=0}^{\infty}\mathcal H_N$|Fock 空间，由所有粒子数扇区组成|

# 检查报告

## 严重问题

- Klein–Gordon 连续性方程中 $\vec j$ 的整体符号与前面算出的 $\partial_t\rho$ 不一致，可能导致守恒方程方向写反。

## 疑似 OCR 问题

- 暂未发现需要依靠原始板书才能确认的 OCR 识别问题。

## 需要人工确认

- 建议对图 11--12 中电流方向和板书采用的连续性方程约定进行人工复核。

## 总体评价

- 推导可靠性：主体推导基本连贯，但连续性方程的电流符号需确认。
- 内容完整性：覆盖从平方根哈密顿量到 Klein–Gordon 方程及 Fock 空间的主要动机。
- 学习适用性：适合作为课堂记录；使用前应修正或注明电流符号约定。
- 是否建议人工复核：是，重点复核概率流与 Klein–Gordon 流的符号。
