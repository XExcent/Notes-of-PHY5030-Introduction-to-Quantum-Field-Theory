---
title: "量子场论导论 Lecture 1.2"
date: 2026-09-23
tags:
  - 量子场论导论
  - lecture
  - Fock空间
  - 洛伦兹不变性
source: "课堂板书"
---

# Lecture 1.2: 从多粒子薛定谔方程到洛伦兹不变性

## 本节内容概览

本节首先回顾多粒子态在产生算符表象中的写法，并验证其满足薛定谔方程。随后利用玻色子产生、湮灭算符的对易关系，讨论哈密顿量厄米性、粒子数算符以及粒子数守恒的条件。接着板书转向洛伦兹不变性，介绍四维坐标、闵可夫斯基度规、爱因斯坦求和约定和不变间隔。最后以矩阵形式推导洛伦兹变换的逆矩阵，并说明升降指标的记号。

# 1. 多粒子态与薛定谔方程

对应图片：

- 1
- 2
- 3
- 4
- 5
- 6（与图片 5 内容相同）

## 板书整理

![[1.2/1.png]]

### 上节回顾

板书回顾了相对论性薛定谔方程的问题、Klein–Gordon 方程以及非相对论量子场论中的 $N$ 粒子态。多粒子波函数与态矢写作

$$
\Box\phi-m^2\phi=0,
\qquad
\Box\equiv-\partial_t^2+\vec\nabla^{\,2}.
$$

$$
\lvert\Psi(t)\rangle
\equiv \int d^3x_1\cdots d^3x_N\,
\Psi(\vec x_1,\ldots,\vec x_N;t)
 a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)\lvert0\rangle .
$$

产生、湮灭算符满足

$$
a(\vec x)\lvert0\rangle=0,
$$

$$
[a(\vec x),a(\vec y)]=0,
\qquad
[a^\dagger(\vec x),a^\dagger(\vec y)]=0,
$$

$$
[a(\vec x),a^\dagger(\vec y)]=\delta^3(\vec x-\vec y).
$$

板书在波函数上方标注 state vector，并将最后的产生算符串标为 $N$-particle states。

![[1.2/2.png]]

### 多粒子哈密顿量与薛定谔方程

自由的 $N$ 粒子系统的薛定谔哈密顿量为

$$
\hat H_S=-\frac{1}{2m}\sum_{j=1}^{N}\vec\nabla_j^{\,2}.
$$

薛定谔方程及其 Hilbert 空间形式为

$$
i\frac{\partial\Psi}{\partial t}=\hat H_S\Psi,
$$

$$
i\frac{\partial}{\partial t}\lvert\Psi(t)\rangle
=\hat H\lvert\Psi(t)\rangle .
$$

其中哈密顿量在产生、湮灭算符表象中写成

$$
\hat H
=\int d^3x\,a^\dagger(\vec x)
\left(-\frac{1}{2m}\vec\nabla_x^{\,2}\right)a(\vec x).
$$

这里的空间导数作用在右侧的湮灭算符上。

### 验证态矢满足薛定谔方程

板书从哈密顿量作用在态矢上开始：

$$
\begin{aligned}
\hat H\lvert\Psi(t)\rangle
={}&-\frac{1}{2m}\int d^3x\int d^3x_1\cdots d^3x_N\,
\Psi(\vec x_1,\ldots,\vec x_N;t)\\
&\qquad\times a^\dagger(\vec x)\,\vec\nabla_x^{\,2}a(\vec x)
 a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)\lvert0\rangle .
\end{aligned}
$$

对 $a(\vec x)$ 使用与产生算符的对易关系，并对空间变量做分部积分（IBP），得到

$$
\begin{aligned}
\hat H\lvert\Psi(t)\rangle
=&-\frac{1}{2m}\sum_{j=1}^{N}
\int d^3x\,d^3x_1\cdots d^3x_N\,
\delta^3(\vec x-\vec x_j)\\
&\qquad\times \Psi(\vec x_1,\ldots,\vec x_N;t)
\vec\nabla_x^{\,2}
a^\dagger(\vec x_1)\cdots
a^\dagger(\vec x_{j-1})a^\dagger(\vec x_{j+1})\cdots
a^\dagger(\vec x_N)\lvert0\rangle .
\end{aligned}
$$

利用 $\delta^3(\vec x-\vec x_j)$ 积分掉 $\vec x$，并把导数改写为对第 $j$ 个坐标的导数：

$$
\begin{aligned}
\hat H\lvert\Psi(t)\rangle
=&-\frac{1}{2m}\sum_{j=1}^{N}
\int d^3x_1\cdots d^3x_N\,
\vec\nabla_j^{\,2}\Psi(\vec x_1,\ldots,\vec x_N;t)\\
&\qquad\times a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)\lvert0\rangle .
\end{aligned}
$$

括号中的微分算符正是多粒子哈密顿量，因此

$$
\hat H\lvert\Psi(t)\rangle
=\int d^3x_1\cdots d^3x_N\,
\left(-\frac{1}{2m}\sum_{j=1}^{N}\vec\nabla_j^{\,2}\right)
\Psi(\vec x_1,\ldots,\vec x_N;t)
 a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)\lvert0\rangle .
$$

由多粒子薛定谔方程，最后一式等于

$$
i\frac{\partial}{\partial t}
\int d^3x_1\cdots d^3x_N\,
\Psi(\vec x_1,\ldots,\vec x_N;t)
 a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)\lvert0\rangle
=i\frac{\partial}{\partial t}\lvert\Psi(t)\rangle .
$$

因此态矢确实满足

$$
\hat H\lvert\Psi(t)\rangle
=i\frac{\partial}{\partial t}\lvert\Psi(t)\rangle .
$$

> 此处使用了空间分部积分，并假设无穷远处的边界项为零。

![[1.2/3.png]]

### 分部积分与湮灭算符穿过产生算符

对具有紧支集的算符值函数 $A(\vec x)$、$B(\vec x)$，板书写出

$$
\int d^3x\,A(\vec x)\,\partial_x B(\vec x)
=-\int d^3x\,\partial_xA(\vec x)\,B(\vec x)
+\oint_{|\vec x|\to\infty}dS\,A(\vec x)B(\vec x),
$$

并说明边界项为零。对湮灭算符作用在多个产生算符上的结果，板书给出

$$
\begin{aligned}
&a(\vec x)a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)\lvert0\rangle\\
={}&\sum_{j=1}^{N}\delta^3(\vec x-\vec x_j)
a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_{j-1})
a^\dagger(\vec x_{j+1})\cdots a^\dagger(\vec x_N)\lvert0\rangle .
\end{aligned}
$$

当 $N=2$ 时，具体例子为

$$
\begin{aligned}
a(\vec x)a^\dagger(\vec x_1)a^\dagger(\vec x_2)\lvert0\rangle
={}&a^\dagger(\vec x_1)a(\vec x)a^\dagger(\vec x_2)\lvert0\rangle
+\delta^3(\vec x-\vec x_1)a^\dagger(\vec x_2)\lvert0\rangle\\
={}&\delta^3(\vec x-\vec x_2)a^\dagger(\vec x_1)\lvert0\rangle
+\delta^3(\vec x-\vec x_1)a^\dagger(\vec x_2)\lvert0\rangle .
\end{aligned}
$$

![[1.2/4.png]]

将上述恒等式代入哈密顿量作用的表达式，并对 $\vec x$ 积分：

$$
\begin{aligned}
\hat H\lvert\Psi(t)\rangle
=&-\frac{1}{2m}\sum_{j=1}^{N}\int d^3x\,d^3x_1\cdots d^3x_N\,
\delta^3(\vec x-\vec x_j)\\
&\qquad\times\Psi(\vec x_1,\ldots,\vec x_N;t)
\vec\nabla_x^{\,2}a^\dagger(\vec x)
a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_{j-1})
a^\dagger(\vec x_{j+1})\cdots\lvert0\rangle\\
=&-\frac{1}{2m}\sum_{j=1}^{N}\int d^3x_1\cdots d^3x_N,
\Psi(\vec x_1,\ldots,\vec x_N;t)\\
&\qquad\times\vec\nabla_j^{\,2}
a^\dagger(\vec x_j)a^\dagger(\vec x_1)\cdots
a^\dagger(\vec x_{j-1})a^\dagger(\vec x_{j+1})\cdots\lvert0\rangle .
\end{aligned}
$$

再次分部积分，把 $\vec\nabla_j^{,2}$ 作用到波函数上，得到

⚠️ **检查提醒：**

- 类型：OCR识别风险
- 问题：此处出现 $\vec\nabla_j^{,2}$，逗号位置不符合前文拉普拉斯算符记号。
- 分析：结合上下文，应该是 $\vec\nabla_j^{\,2}$ 或 $\vec\nabla_j^2$；当前写法可能是 OCR 将空格或上标识别成逗号。
- 建议：查看图片 4 的原始公式，确认拉普拉斯算符的上标写法。
- 置信度：高

$$
\hat H\lvert\Psi(t)\rangle
=\int d^3x_1\cdots d^3x_N\,
\left(-\frac{1}{2m}\sum_{j=1}^{N}\vec\nabla_j^{\,2}\Psi\right)
a^\dagger(\vec x_1)\cdots a^\dagger(\vec x_N)\lvert0\rangle
=\hat H_S\lvert\Psi(t)\rangle .
$$

结合 $i\partial_t\Psi=\hat H_S\Psi$，即得到

$$
\hat H\lvert\Psi(t)\rangle
=i\frac{\partial}{\partial t}\lvert\Psi(t)\rangle .
$$

![[1.2/5.png]]

最后两行板书为

$$
\hat H\lvert\Psi(t)\rangle
=i\frac{\partial}{\partial t}\lvert\Psi(t)\rangle .
$$

并给出玻色子性质的说明：

$$
[a^\dagger(\vec x),a^\dagger(\vec y)]\lvert0\rangle=0,
$$

所以

$$
a^\dagger(\vec x)a^\dagger(\vec y)\lvert0\rangle
=a^\dagger(\vec y)a^\dagger(\vec x)\lvert0\rangle .
$$

交换两个粒子的位置给出同一个态。

![[1.2/6.png]]

图片 6 与图片 5 的板书内容相同，保留其在编号序列中的位置，不重复添加新的推导。

## 解释

哈密顿量中的湮灭算符通过对易关系逐个“消去”产生算符，产生的 $\delta$ 函数把积分变量固定在对应粒子位置。分部积分后，空间导数从产生算符转移到多粒子波函数上，于是场论哈密顿量在 $N$ 粒子扇区中还原为熟悉的多粒子薛定谔哈密顿量。产生算符彼此对易则说明这里描述的是玻色子。

# 2. 厄米性、粒子数算符与粒子数守恒

对应图片：

- 7
- 8
- 9

## 板书整理

![[1.2/7.png]]

### 哈密顿量的厄米性

板书列出

$$
\hat H^\dagger=\hat H,
$$

并标注为 Hermitian。

### 粒子数算符

定义粒子数算符

$$
\hat N=\int d^3x\,a^\dagger(\vec x)a(\vec x).
$$

板书把

$$
\hat N\lvert\Psi(t)\rangle=N\lvert\Psi(t)\rangle
$$

作为练习，说明 $N$ 粒子态是粒子数算符的本征态。

一般地，若算符 $\hat O$ 不显含时间，则海森堡图像中

$$
i\frac{d\hat O}{dt}=[\hat H,\hat O].
$$

在本例中板书写出

$$
[\hat N,\hat H]=0
\quad\Longrightarrow\quad
\text{particle number is conserved}.
$$

![[1.2/8.png]]

### 证明 $[\hat N,\hat H]=0$

将 $\hat N$ 和 $\hat H$ 的定义代入：

$$
[\hat N,\hat H]
=-\frac{1}{2m}\int d^3x\,d^3y\,
\left[
a^\dagger(\vec x)a(\vec x),
a^\dagger(\vec y)\vec\nabla_y^{\,2}a(\vec y)
\right].
$$

使用恒等式

$$
[A,BC]=[A,B]C+B[A,C],
$$

先得到

$$
\begin{aligned}
[\hat N,\hat H]
=-\frac{1}{2m}\int d^3x\,d^3y\,\Big(&
[a^\dagger(\vec x)a(\vec x),a^\dagger(\vec y)]\vec\nabla_y^{\,2}a(\vec y)\\
&+a^\dagger(\vec y)\vec\nabla_y^{\,2}
[a^\dagger(\vec x)a(\vec x),a(\vec y)]\Big).
\end{aligned}
$$

再利用

$$
[a^\dagger(\vec x)a(\vec x),a^\dagger(\vec y)]
=a^\dagger(\vec x)\delta^3(\vec x-\vec y),
$$

$$
[a^\dagger(\vec x)a(\vec x),a(\vec y)]
=-a(\vec x)\delta^3(\vec x-\vec y),
$$

得到

$$
[\hat N,\hat H]
=-\frac{1}{2m}\int d^3x\,d^3y\,
\left[
\delta^3(\vec x-\vec y)a^\dagger(\vec x)\vec\nabla_y^{\,2}a(\vec y)
-a^\dagger(\vec y)\vec\nabla_y^{\,2}
\big(a(\vec x)\delta^3(\vec x-\vec y)\big)
\right].
$$

对含有 $\delta$ 函数的项积分并进行分部积分：

$$
[\hat N,\hat H]
=-\frac{1}{2m}\int d^3x\,
\left[
a^\dagger(\vec x)\vec\nabla_x^{\,2}a(\vec x)
-\vec\nabla_x^{\,2}a^\dagger(\vec x)\,a(\vec x)
\right]=0.
$$

最后一个等号使用了空间分部积分以及无穷远处边界项为零的假设。

![[1.2/9.png]]

板书将上式的中间步骤写为

$$
\begin{aligned}
[\hat N,\hat H]
=-\frac{1}{2m}\int d^3x\,d^3y\,\Big(&
\delta^3(\vec x-\vec y)a^\dagger(\vec x)\vec\nabla_y^{\,2}a(\vec y)\\
&-a^\dagger(\vec y)a(\vec x)\vec\nabla_y^{\,2}
\delta^3(\vec x-\vec y)\Big)\\
=-\frac{1}{2m}\int d^3x\,
\left(a^\dagger(\vec x)\vec\nabla_x^{\,2}a(\vec x)
-\vec\nabla_x^{\,2}a^\dagger(\vec x)\,a(\vec x)\right)=0.
\end{aligned}
$$

### 一般相互作用哈密顿量

板书提醒：对更一般的哈密顿量，粒子数未必守恒。例如

$$
\hat H=\alpha\int d^3x\,
\left[a^\dagger(\vec x)a^2(\vec x)+\mathrm{h.c.}\right]
$$

给出

$$
[\hat H,\hat N]\ne0.
$$

因此在一般量子场论中，粒子数不一定是守恒量。

## 解释

自由二次哈密顿量含有一个产生算符和一个湮灭算符，作用只是在不同位置重新分配同一粒子，因此与粒子数算符对易。含有 $a^\dagger a^2$ 的相互作用会把两个粒子转化为一个粒子（其厄米共轭过程则相反），所以通常不再与 $\hat N$ 对易。

# 3. 洛伦兹不变性与闵可夫斯基记号

对应图片：

- 10
- 11
- 12
- 13
- 14
- 15

## 板书整理

![[1.2/10.png]]

板书转入洛伦兹不变性，并指出：

> In general, particle number not conserved in QFT.

取笛卡尔坐标并把时间、空间统一为四维坐标：

$$
x^\mu=(t,x,y,z),
$$

或写成

$$
x^\mu=(x^0,x^1,x^2,x^3).
$$

指标约定为

$$
\mu,\nu,\rho,\ldots\in\{0,1,2,3\},
\qquad
i,j,k,\ell,\ldots\in\{1,2,3\}.
$$

洛伦兹变换写作

$$
x^\mu\longmapsto x'^\mu=\Lambda^\mu{}_{\nu}x^\nu,
$$

其中 $\Lambda^\mu{}_{\nu}$ 称为 Lorentz matrix，满足

$$
g_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}=g_{\mu\nu}.
$$

![[1.2/11.png]]

闵可夫斯基度规取为

$$
g_{\mu\nu}
\equiv
\begin{pmatrix}
-1&0&0&0\\
0&1&0&0\\
0&0&1&0\\
0&0&0&1
\end{pmatrix}.
$$

板书将其标为 Minkowski metric。

爱因斯坦求和约定：一个指标在同一项中重复出现一次上标、一次下标时，表示对该指标求和。例如

$$
g_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}
\equiv
\sum_{\rho=0}^{3}\sum_{\sigma=0}^{3}
g_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}.
$$

第一个命题是不变间隔：

$$
ds^2=g_{\mu\nu}\,dx^\mu dx^\nu.
$$

![[1.2/12.png]]

在坐标变换

$$
dx'^\mu=\Lambda^\mu{}_{\rho}dx^\rho
$$

下，

$$
\begin{aligned}
ds'^2
&=g_{\mu\nu}\,dx'^\mu dx'^\nu\\
&=g_{\mu\nu}
\left(\Lambda^\mu{}_{\rho}dx^\rho\right)
\left(\Lambda^\nu{}_{\sigma}dx^\sigma\right)\\
&=g_{\mu\nu}\Lambda^\mu{}_{\rho}\Lambda^\nu{}_{\sigma}
dx^\rho dx^\sigma\\
&=g_{\rho\sigma}dx^\rho dx^\sigma\\
&=ds^2.
\end{aligned}
$$

因此洛伦兹变换保持 $ds^2$ 不变。洛伦兹变换构成群，板书记为 $O(3,1)$，其中 $3$ 表示空间维数，$1$ 表示时间维数。

恒等元为 Kronecker delta：

$$
\delta^\mu{}_{\nu}
=\begin{cases}
1,&\mu=\nu,\\
0,&\mu\ne\nu,
\end{cases}
$$

并满足

$$
x'^\mu=\delta^\mu{}_{\nu}x^\nu=x^\mu.
$$

![[1.2/13.png]]

### 矩阵乘积与逆变换

板书把两个洛伦兹变换的乘积写成

$$
\widetilde\Lambda^\mu{}_{\nu}
=\Lambda^\mu{}_{\rho}\Lambda^\rho{}_{\nu},
$$

并作为练习指出这仍是一个洛伦兹变换。

在省略指标的矩阵记号中，洛伦兹条件为

$$
g=\Lambda^{\mathrm T}g\Lambda.
$$

因此逆矩阵满足

$$
\Lambda^{-1}=g^{-1}\Lambda^{\mathrm T}g.
$$

板书的指标证明从

$$
g_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}=g_{\mu\nu}
$$

开始，将左、右两侧分别看作矩阵乘积，即得到上面的矩阵关系。

![[1.2/14.png]]

板书进一步说明：洛伦兹条件就是矩阵乘积

$$
g=\Lambda^{\mathrm T}g\Lambda,
$$

从而

$$
\Lambda^{-1}=g^{-1}\Lambda^{\mathrm T}g.
$$

这里 $g^{-1}$ 表示逆度规。

指标升降记号为

$$
g^{\mu\nu}\longrightarrow g^{-1},
$$

$$
g_{\mu\nu}V^\nu\equiv V_\mu,
$$

即用度规降低指标。

![[1.2/15.png]]

相应地，用逆度规升高指标：

$$
g^{\mu\nu}V_\nu\equiv V^\mu.
$$

## 解释

四维记号把时间和空间坐标统一为一个带指标对象。闵可夫斯基度规的符号差异保留了相对论时空间隔的结构；洛伦兹变换正是保持该二次型不变的线性变换。矩阵关系 $g=\Lambda^{\mathrm T}g\Lambda$ 既给出不变间隔，也直接导出逆变换公式。度规还负责在协变分量和逆变分量之间升降指标。

# 本节知识结构

多粒子波函数与产生算符态
↓
场论哈密顿量作用及分部积分
↓
玻色子对易关系
↓
粒子数算符 $\hat N$
↓
自由哈密顿量满足 $[\hat N,\hat H]=0$
↓
一般相互作用中粒子数可不守恒
↓
四维坐标与闵可夫斯基度规
↓
洛伦兹变换保持 $ds^2$ 不变
↓
矩阵形式与指标升降

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $\lvert\Psi(t)\rangle=\int d^3x_1\cdots d^3x_N\,\Psi\,a^\dagger_1\cdots a^\dagger_N\lvert0\rangle$ | $N$ 粒子波函数对应的 Fock 空间态 |

⚠️ **检查提醒：**

- 类型：定义问题
- 问题：公式清单中的 `$a^\dagger_1$`、`$a^\dagger_N$` 没有在清单或正文中定义为 `$a^\dagger(\vec x_1)$`、`$a^\dagger(\vec x_N)$` 的缩写。
- 分析：读者可能将下标理解为内部指标，而正文使用的是位置参数；这会造成记号不一致。
- 建议：确认原始板书是否明确了该缩写，并在正文中给出定义。
- 置信度：中
| $\hat H_S=-\frac{1}{2m}\sum_{j=1}^{N}\vec\nabla_j^{\,2}$ | 自由 $N$ 粒子薛定谔哈密顿量 |
| $\hat H=\int d^3x\,a^\dagger(\vec x)(-\frac{1}{2m}\vec\nabla^2)a(\vec x)$ | 场算符形式的自由哈密顿量 |
| $[a(\vec x),a^\dagger(\vec y)]=\delta^3(\vec x-\vec y)$ | 玻色子产生、湮灭算符的基本对易关系 |
| $\hat N=\int d^3x\,a^\dagger(\vec x)a(\vec x)$ | 粒子数算符 |
| $[\hat N,\hat H]=0$ | 自由理论中粒子数守恒 |
| $\hat H=\alpha\int d^3x[a^\dagger a^2+\mathrm{h.c.}]$ | 一个使粒子数一般不守恒的相互作用例子 |
| $x'^\mu=\Lambda^\mu{}_{\nu}x^\nu$ | 洛伦兹坐标变换 |
| $g_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}=g_{\mu\nu}$ | 洛伦兹变换保持度规不变的条件 |
| $ds^2=g_{\mu\nu}dx^\mu dx^\nu$ | 不变时空间隔 |
| $g=\Lambda^{\mathrm T}g\Lambda$ | 洛伦兹条件的矩阵形式 |
| $\Lambda^{-1}=g^{-1}\Lambda^{\mathrm T}g$ | 洛伦兹变换的逆矩阵 |
| $V_\mu=g_{\mu\nu}V^\nu$，$V^\mu=g^{\mu\nu}V_\nu$ | 指标降低与升高 |

# 推导逻辑与内容正确性检查

- 图片 2–5 中从 $\hat H\lvert\Psi\rangle$ 到 $i\partial_t\lvert\Psi\rangle$ 的步骤使用了玻色子对易关系、空间分部积分和边界项为零的假设；这些步骤与板书给出的自由多粒子薛定谔方程一致。
- 图片 8–9 中 $[\hat N,\hat H]=0$ 的结论依赖自由二次哈密顿量以及无穷远边界项消失；板书原推导已完整保留。
- 图片 10–15 中洛伦兹条件、矩阵关系和逆矩阵公式相互一致。以上为对板书推导的检查，不修改板书原内容。

# 检查报告

## 严重问题

- 暂未发现会直接改变主要结论的确定性公式错误。

## 疑似 OCR 问题

- $\vec\nabla_j^{,2}$ 的逗号疑似由 OCR 或排版转换产生。
- 公式清单中的 $a^\dagger_1$ 等缩写未明确定义，可能只是省略记号。

## 需要人工确认

- 请结合图片 4 确认拉普拉斯算符上标。
- 请确认公式清单中的产生算符下标是否仅表示位置参数的缩写。

## 总体评价

- 推导可靠性：多粒子哈密顿量、粒子数守恒和洛伦兹矩阵部分总体连贯。
- 内容完整性：覆盖产生算符表象、Fock 空间和闵可夫斯基记号的主要步骤。
- 学习适用性：适合作为学习笔记，但应先消除上述记号歧义。
- 是否建议人工复核：是，重点检查图片 4 的拉普拉斯算符记号。
