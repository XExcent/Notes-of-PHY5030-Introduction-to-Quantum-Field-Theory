---
title: "量子场论导论 Lecture 3.1"
date: 2026-09-23
tags:
  - 量子场论导论
  - lecture
  - Hamiltonian
  - Noether定理
  - 守恒流
  - 时空平移
source: "课堂板书"
---

# Lecture 3.1: Hamiltonian 与 Noether 定理

## 本节内容概览

本节先回顾标量场和矢量场的拉格朗日量，并从拉格朗日量定义共轭动量和 Hamiltonian 密度。随后把定义推广到带指标的张量场和复标量场。课程主体是连续对称性：从无穷小场变换和拉格朗日量的全导数变化出发，得到 Noether 流及其守恒方程。最后以复标量场的 $U(1)$ 对称性和时空平移为例，计算相应的守恒流、电荷以及能动张量。

# 1. Hamiltonian 与共轭动量

对应图片：

- 1
- 2
- 3
- 4
- 5

## 板书整理

### 上节回顾：标量场和矢量场（图 1）

![[3.1/1.jpg]]

实标量场的拉格朗日量写作

$$
\mathcal L=-\frac12(\partial\phi)^2-V(\phi),
\qquad
V(\phi)=-\frac{m^2}{2}\phi^2+V_{\rm int}(\phi).
$$

⚠️ **检查提醒：**

- 类型：符号疑似错误
- 问题：这里将势能的二次项写成 $-m^2\phi^2/2$，但本节后面对自由实标量场使用的是 $\mathcal L=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2$，对应 $V=+m^2\phi^2/2$。
- 分析：按当前定义 $\mathcal L=-\frac12(\partial\phi)^2-V$，该处负号会给出相反的质量项/不稳定势，和后文正定 Hamiltonian 的自由场形式不一致。
- 建议：对照图片 1 确认质量项符号是否为板书或 OCR 错误，并区分普通质量项与对称性破缺势能。
- 置信度：高

复标量场写作

$$
\mathcal L=-\partial^\mu\phi^*\partial_\mu\phi-V(|\phi|^2).
$$

矢量场的形式为

$$
\mathcal L=-\frac14F^{\mu\nu}F_{\mu\nu}-V(A^\mu A_\mu),
$$

其中

$$
V(A^\mu A_\mu)=-\frac{m^2}{2}A^\mu A_\mu+V_{\rm int}(A^\mu A_\mu).
$$

⚠️ **检查提醒：**

- 类型：符号疑似错误
- 问题：按 $\mathcal L=-\frac14F^2-V(A^2)$，这里的负号会使质量项变成 $+\frac{m^2}{2}A^2$，而前文 Proca 拉格朗日量采用的是 $-\frac{m^2}{2}A^2$。
- 分析：两种符号对应不同的质量项和稳定性，不能在未说明约定时并列使用。
- 建议：结合图片 1 确认 $V(A^2)$ 的符号，并与 Lecture 2.3 的 Proca 约定统一核对。
- 置信度：高

板书指出，若相互作用项只由不含导数的标量构成，则可以用 $A_\mu$ 的指标缩并构造；若写成

$$
\mathcal L_{\rm int}=(\partial_\mu A^\mu)^3
\quad\text{或}\quad
\bigl(F^{\mu\nu}F_{\mu\nu}\bigr)^2,
$$

就会含有过多（高于二阶）的导数。

⚠️ **检查提醒：**

- 类型：表述不严谨
- 问题：$(F^{\mu\nu}F_{\mu\nu})^2$ 虽含有较高阶的导数乘积，但其 Euler–Lagrange 方程对 $A_\mu$ 仍通常至多含二阶导数。
- 分析：导数“次数/阶数”和运动方程的“微分阶数”不是同一概念；当前表述容易把高维导数相互作用误说成高阶导数方程。
- 建议：确认板书是在讨论导数相互作用的阶数、算符维数，还是运动方程的微分阶数。
- 置信度：高

### 张量场、自旋与 Hamiltonian（图 2）

![[3.1/2.jpg]]

板书将张量场的秩（指标数）与场所描述粒子的自旋联系起来：

- 标量场 $\phi$ 描述自旋 $0$ 粒子（例如 Higgs，玻色子）；
- 矢量场 $A_\mu$ 描述自旋 $1$ 粒子（例如 photon）。

Hamiltonian 定义为 Hamiltonian 密度的空间积分：

$$
H[\phi]=\int d^3x\,\mathcal H[\phi].
$$

对标量场，正则动量（动量密度）定义为

$$
\pi(x)\equiv\frac{\partial\mathcal L}{\partial\dot\phi(x)}.
$$

### Legendre 变换和自由实标量场（图 3）

![[3.1/3.jpg]]

Hamiltonian 密度由 Legendre 变换给出：

$$
\mathcal H(\phi,\pi)\equiv\pi\dot\phi-\mathcal L,
$$

其中必须把 $\dot\phi$ 表成 $(\phi,\pi)$ 的函数；$\mathcal H$ 可以依赖 $\phi,\pi$，但不应显含时间导数。

板书对

$$
\mathcal L=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2
=\frac12\dot\phi^{\,2}-\frac12(\vec\nabla\phi)^2-\frac{m^2}{2}\phi^2
$$

进行计算。固定 $\phi$ 和 $\vec\nabla\phi$ 后，

$$
\pi=\left.\frac{\partial\mathcal L}{\partial\dot\phi}\right|_{\phi,\,\vec\nabla\phi\,{\rm fixed}}
=\dot\phi.
$$

因此

$$
\dot\phi=\pi.
$$

### Hamiltonian 的显式形式与正定性（图 4）

![[3.1/4.jpg]]

代入 Legendre 变换：

$$
\begin{aligned}
\mathcal H
&=\pi^2-\left[\frac12\pi^2-\frac12(\vec\nabla\phi)^2-\frac{m^2}{2}\phi^2\right]\\
&=\frac12\pi^2+\frac12(\vec\nabla\phi)^2+\frac{m^2}{2}\phi^2.
\end{aligned}
$$

⚠️ **检查提醒：**

- 类型：缺少条件
- 问题：这里直接称 Hamiltonian“正定”，但至少需要 $m^2\ge0$，并且正定性还涉及零模和边界条件。
- 分析：若 $m^2<0$，势能项为负；即使 $m^2=0$，Hamiltonian 也只是半正定而非严格正定。
- 建议：结合图片 4 确认质量参数的假设，并将“正定”理解为在 $m^2>0$ 等条件下成立。
- 置信度：高

板书将三项分别标为：动能密度、梯度能量密度和势能密度。于是 $\mathcal H$ 为正定，且由 $0$ 向下有界。

若把动能项在拉格朗日量中的符号反过来，例如

$$
\mathcal L=+\frac12(\partial\phi)^2-\cdots
=-\frac12\dot\phi^{\,2}+\frac12(\vec\nabla\phi)^2-\cdots,
$$

则

$$
\pi=-\dot\phi,
\qquad
\dot\phi=-\pi,
$$

从而

$$
\mathcal H=-\frac12\pi^2-\frac12(\vec\nabla\phi)^2+\frac{m^2}{2}\phi^2,
$$

板书标记为 unbounded below。

### 任意张量场和复标量场（图 5、图 6）

![[3.1/5.jpg]]

对带 $s$ 个指标的张量场

$$
\psi_{\mu_1\cdots\mu_s}(x),
$$

正则动量为

$$
\pi^{\mu_1\cdots\mu_s}
\equiv
\frac{\partial\mathcal L}
{\partial\dot\psi_{\mu_1\cdots\mu_s}},
$$

Hamiltonian 密度为

$$
\mathcal H=\pi^{\mu_1\cdots\mu_s}\dot\psi_{\mu_1\cdots\mu_s}-\mathcal L.
$$

对于复标量场，板书把 $\phi$ 和 $\phi^*$ 视作独立变量：

![[3.1/6.jpg]]

$$
\pi\equiv\frac{\partial\mathcal L}{\partial\dot\phi},
\qquad
\pi^*\equiv\frac{\partial\mathcal L}{\partial\dot\phi^*}.
$$

若写成两个实场 $\phi=\phi_1+i\phi_2$，则

$$
\pi_1\equiv\frac{\partial\mathcal L}{\partial\dot\phi_1},
\qquad
\pi_2\equiv\frac{\partial\mathcal L}{\partial\dot\phi_2}.
$$

板书说明，$\pi^*$ 确实是 $\pi$ 的复共轭。

## 解释

Hamiltonian 是把速度变量换成正则动量后的能量密度。标准实标量场的三个贡献都为非负，因此总 Hamiltonian 向下有界；反号的动能会产生负的 $\pi^2$ 项，使能量无下界。复场的两个正则动量来自把场和共轭场作为独立变量进行变分。

# 2. Noether 定理：一般形式

对应图片：

- 7
- 8
- 9
- 10
- 11
- 12
- 13

## 板书整理

### 无穷小连续对称变换（图 7、图 8）

![[3.1/7.jpg]]

连续对称变换是参数的无穷小变化。板书用 $\epsilon$ 表示无穷小参数，场的变换写成

$$
\phi(x)\longrightarrow\phi'(x)
=\phi(x)+\epsilon\,\Delta_\epsilon[\phi(x)],
$$

其中 $\Delta_\epsilon[\phi]$ 是由场构成的某个泛函。

若拉格朗日量在变换下变化为一个全导数，

$$
\mathcal L\longrightarrow\mathcal L'
=\mathcal L+\epsilon\,\partial_\mu K_\epsilon^\mu[\phi],
$$

则定义 Noether 流

$$
\boxed{
J_\epsilon^\mu(x)
\equiv
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_\epsilon[\phi]-K_\epsilon^\mu
}.
$$

### Noether 流定义与连续性方程（图 8、图 9）

![[3.1/8.jpg]]

板书把无穷小变换和全导数变化写成

$$
\phi'(x)=\phi(x)+\epsilon\Delta_\epsilon[\phi(x)],
\qquad
\mathcal L'=\mathcal L+\epsilon\partial_\mu K_\epsilon^\mu[\phi].
$$

于是

$$
J_\epsilon^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_\epsilon[\phi]-K_\epsilon^\mu.
$$

![[3.1/9.jpg]]

在使用 Euler--Lagrange 方程（on-shell）后，

$$
\left.\partial_\mu J_\epsilon^\mu\right|_{\rm EL\ eq.}=0,
\qquad
\frac{\partial J_\epsilon^0}{\partial t}
=-\vec\nabla\cdot\vec J_\epsilon.
$$

### 变分展开和 Noether 流的守恒（图 10、图 11、图 12）

![[3.1/10.jpg]]
![[3.1/11.png]]
![[3.1/12.jpg]]

假定 $\mathcal L=\mathcal L(\phi,\partial_\mu\phi)$，并对无穷小参数保留一阶：

$$
\begin{aligned}
\mathcal L[\phi']
&=\mathcal L\left[\phi+\epsilon\Delta_\epsilon\right]\\
&=\mathcal L[\phi]
+\frac{\partial\mathcal L}{\partial\phi}
\epsilon\Delta_\epsilon
+\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\partial_\mu(\epsilon\Delta_\epsilon).
\end{aligned}
$$

因此

$$
\epsilon\,\partial_\mu K_\epsilon^\mu
=\epsilon\left[
\frac{\partial\mathcal L}{\partial\phi}\Delta_\epsilon
+\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\partial_\mu\Delta_\epsilon
\right].
$$

将第一项改写为

$$
\frac{\partial\mathcal L}{\partial\phi}\Delta_\epsilon
=\partial_\mu\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_\epsilon
\right)
-\partial_\mu\left(\frac{\partial\mathcal L}
{\partial(\partial_\mu\phi)}\right)
\Delta_\epsilon
$$

⚠️ **检查提醒：**

- 类型：推导错误
- 问题：这里声称 $\frac{\partial\mathcal L}{\partial\phi}\Delta_\epsilon=\partial_\mu(p^\mu\Delta_\epsilon)-\partial_\mu(p^\mu)\Delta_\epsilon$，但右侧按乘积法则等于 $p^\mu\partial_\mu\Delta_\epsilon$，并不等于左侧。
- 分析：正确的 Noether 推导应直接计算 $\partial_\mu(p^\mu\Delta_\epsilon-K^\mu)=(\partial_\mu p^\mu-\partial\mathcal L/\partial\phi)\Delta_\epsilon$；当前中间等式会造成后续符号和逻辑混乱。
- 建议：对照图片 10--12 逐行核对该等式，保留 $K^\mu$ 和 $p^\mu\partial_\mu\Delta_\epsilon$ 项后再使用 EL 方程。
- 置信度：高

后，得到

$$
\partial_\mu K_\epsilon^\mu
=-\left[
\partial_\mu\left(\frac{\partial\mathcal L}
{\partial(\partial_\mu\phi)}\right)
-\frac{\partial\mathcal L}{\partial\phi}
\right]\Delta_\epsilon.
$$

所以在 Euler–Lagrange 方程成立时，

$$
\boxed{\partial_\mu J_\epsilon^\mu=0}.
$$

图 11（11.png）把中间步骤写成

$$
\partial_\mu J_\epsilon^\mu
=\partial_\mu\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_\epsilon\right)
+\Delta_\epsilon\left[
\frac{\partial\mathcal L}{\partial\phi}
-\partial_\mu\left(\frac{\partial\mathcal L}
{\partial(\partial_\mu\phi)}\right)
\right],
$$

并在使用 EL 方程后得到

$$
\partial_\mu\left[
K_\epsilon^\mu
-\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_\epsilon
\right]=0.
$$

这里括号内正是 $-J_\epsilon^\mu$，因为

$$
J_\epsilon^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_\epsilon-K_\epsilon^\mu.
$$

因此该式与 $\partial_\mu J_\epsilon^\mu=0$ 等价；$K_\epsilon^\mu$ 是拉格朗日量变化中的全导数项，不能与 Noether 流 $J_\epsilon^\mu$ 混用。

### 作用量不变（图 13）

![[3.1/13.jpg]]

对作用量 $S=\int d^4x\,\mathcal L$，在对称变换下

$$
S'=
\int d^4x\,\mathcal L'
=\int d^4x\,\mathcal L
+\epsilon\int d^4x\,\partial_\mu K_\epsilon^\mu
=S,
$$

因为最后一项是边界项，并假设场在无穷远处足够快地消失：

$$
\int d^3x\,\vec\nabla\cdot\vec K
=\oint_{|\vec x|\to\infty}d\vec S\cdot\vec K=0.
$$

⚠️ **检查提醒：**

- 类型：缺少条件
- 问题：这里由空间无穷远的边界项为零直接推出四维作用量不变，但时间端点的边界条件没有单独说明。
- 分析：对 $\int d^4x\,\partial_\mu K^\mu$ 还需要时间方向的端点项消失，或固定变分在初末时刻为零；仅给出空间表面项不足以覆盖全部边界。
- 建议：结合图片 13 确认课程是否默认时间端点条件，并在使用 Noether 电荷时明确边界假设。
- 置信度：高

板书还指出，有限（非无穷小）对称变换不一定适用同样的无穷小推导。例：

$$
\mathcal L=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2
$$

具有离散变换 $\phi\mapsto-\phi$，此时 $\mathcal L'=\mathcal L$，相应 $K^\mu=0$。

## 解释

Noether 定理把“拉格朗日量只改变一个全导数”转化为一个在运动方程成立时守恒的四维流。全导数不改变作用量的条件依赖边界项消失；因此“对称性”和“守恒”之间的联系是在适当边界条件下建立的。

# 3. $U(1)$ 对称性、电流与电荷

对应图片：

- 14
- 15
- 16
- 17

## 板书整理

### 复标量场的 $U(1)$ 变换（图 14、图 15）

![[3.1/14.jpg]]
![[3.1/15.jpg]]

考虑复标量场的 $U(1)$ 对称性：

$$
\phi\longrightarrow\phi'=e^{i\alpha}\phi,
\qquad
\phi^*\longrightarrow\phi^{*\prime}=e^{-i\alpha}\phi^*,
$$

其中 $\alpha$ 是实常数。无穷小展开给出

$$
\phi'=\phi+i\alpha\phi,
\qquad
\Delta_\alpha=i\phi,
$$

$$
\phi^{*\prime}=\phi^*-i\alpha\phi^*,
\qquad
\Delta_\alpha^*=-i\phi^*.
$$

对

$$
\mathcal L=-\partial^\mu\phi^*\partial_\mu\phi-V(|\phi|^2)
$$

应用 Noether 公式（这里 $K_\alpha^\mu=0$）：

$$
\begin{aligned}
J_\alpha^\mu
&=-\partial^\mu\phi^*(i\phi)
 +(-\partial^\mu\phi)(-i\phi^*)\\
&=i\left(\phi^*\partial^\mu\phi
 -\phi\partial^\mu\phi^*\right).
\end{aligned}
$$

板书的逐步结果为

$$
\boxed{J_\alpha^\mu
=i\left[\phi^*\partial^\mu\phi
-\phi\partial^\mu\phi^*\right]}.
$$

### 检查 Noether 流的守恒（图 16）

![[3.1/16.jpg]]

直接取散度（混合的一阶导数项相互抵消）：

$$
\partial_\mu J_\alpha^\mu
=i\left[
\phi^*\,\Box\phi-\phi\,\Box\phi^*
\right],
$$

板书用复标量场的 EL 方程

$$
\Box\phi=\frac{dV}{d(|\phi|^2)}\phi,
\qquad
\Box\phi^*=\frac{dV}{d(|\phi|^2)}\phi^*
$$

代入后得到

$$
\partial_\mu J_\alpha^\mu=0.
$$

板书备注：这里假定有关积分收敛，这一假定并非总是成立。

### Noether 电荷及其守恒（图 16、图 17）

![[3.1/17.jpg]]

定义 Noether 电荷

$$
\boxed{Q_\epsilon\equiv\int d^3x\,J_\epsilon^0}.
$$

由连续性方程

$$
\frac{dQ_\epsilon}{dt}
=\frac{d}{dt}\int d^3x\,J_\epsilon^0
=-\int d^3x\,\vec\nabla\cdot\vec J_\epsilon
=-\oint d\vec S\cdot\vec J_\epsilon=0,
$$

其中最后一步使用 $|\vec x|\to\infty$ 时流消失的边界条件。因此

$$
\boxed{\frac{dQ_\epsilon}{dt}=0}.
$$

## 解释

复标量场的整体相位旋转保持 $|\phi|^2$ 不变，所以势能和动能都不变。对应的 Noether 流是一个实的四维流，其时间分量积分给出守恒电荷。守恒电荷的时间不变性仍然需要空间无穷远处没有净流出。

# 4. 时空平移与能动张量

对应图片：

- 18
- 19

## 板书整理

### 时空平移的无穷小变换（图 18）

![[3.1/18.jpg]]

考虑平移参数 $a^\mu$：

$$
\phi(x)\longrightarrow\phi'(x)=\phi(x+a)
=\phi(x)+a^\mu\partial_\mu\phi(x).
$$

板书将 $a^\mu$ 标为四个分量对应的参数，并写出

$$
\Delta_{a,\nu}=\partial_\nu\phi.
$$

相应的 Noether 流带有两个指标（一个来自时空方向 $\mu$，一个来自平移参数的方向 $\nu$）：

$$
J_{a,\nu}^{\mu}
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_{a,\nu}-K_{a,\nu}^{\mu}.
$$

### 平移下拉格朗日量的变化（图 19）

![[3.1/19.jpg]]

因为 $\mathcal L$ 是标量，平移下

$$
\mathcal L'[\phi]=\mathcal L(x+a)
=\mathcal L+a^\mu\partial_\mu\mathcal L.
$$

另一方面，Noether 形式的变化规则为

$$
\mathcal L'=\mathcal L+\epsilon\partial_\mu K_\epsilon^\mu.
$$

比较两式得到

$$
K_{a,\nu}^{\mu}=\delta_\nu^{\mu}\mathcal L.
$$

于是定义能动张量（板书中的平移 Noether 流）

$$
\boxed{
J_{a,\nu}^{\mu}
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\partial_\nu\phi-\delta_\nu^{\mu}\mathcal L
}.
$$

通常把它记为

$$
T^\mu{}_{\nu}
\equiv
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\partial_\nu\phi-\delta^\mu{}_{\nu}\mathcal L.
$$

其守恒方程为

$$
\boxed{\partial_\mu T^\mu{}_{\nu}=0}.
$$

## 解释

平移对称性表示物理定律不依赖绝对时空位置。时间平移对应能量守恒，空间平移对应动量守恒；二者合并后，Noether 流自然成为带两个指标的能动张量。

# 本节知识结构

拉格朗日量与共轭动量
↓
Legendre 变换得到 Hamiltonian
↓
连续对称变换与全导数变化
↓
Noether 流及在壳守恒方程
↓
$U(1)$ 相位对称性与守恒电流
↓
Noether 电荷的守恒
↓
时空平移与能动张量

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $\pi=\partial\mathcal L/\partial\dot\phi$ | 标量场的正则动量 |
| $\mathcal H=\pi\dot\phi-\mathcal L$ | Hamiltonian 密度 |
| $\mathcal H=\frac12\pi^2+\frac12(\vec\nabla\phi)^2+\frac{m^2}{2}\phi^2$ | 自由实标量场的正定 Hamiltonian |
| $\phi'=\phi+\epsilon\Delta_\epsilon[\phi]$ | 无穷小场变换 |
| $\mathcal L'=\mathcal L+\epsilon\partial_\mu K_\epsilon^\mu$ | 拉格朗日量的全导数变化 |
| $J_\epsilon^\mu=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\Delta_\epsilon-K_\epsilon^\mu$ | Noether 流 |
| $\partial_\mu J_\epsilon^\mu=0$ | EL 方程成立时的守恒律 |
| $Q_\epsilon=\int d^3x\,J_\epsilon^0$ | Noether 电荷 |
| $J_\alpha^\mu=i(\phi^*\partial^\mu\phi-\phi\partial^\mu\phi^*)$ | 复标量场 $U(1)$ 电流 |
| $\phi(x+a)=\phi(x)+a^\mu\partial_\mu\phi(x)$ | 无穷小时空平移 |
| $T^\mu{}_{\nu}=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\partial_\nu\phi-\delta^\mu{}_{\nu}\mathcal L$ | 平移对称性对应的能动张量 |

# 推导逻辑与内容正确性检查

- Hamiltonian 部分保留了由 $\pi=\dot\phi$ 到 $\mathcal H$ 的 Legendre 变换，并记录了反号动能导致 Hamiltonian 无下界的板书结论。
- Noether 流的推导保留了对 $\mathcal L(\phi,\partial_\mu\phi)$ 的一阶展开，以及使用 EL 方程后得到 $\partial_\mu J^\mu=0$ 的步骤。
- $U(1)$ 电流的守恒检查使用了复标量场的两个 EL 方程；原板书中的“假定积分收敛”条件已保留。
- 时空平移部分保留了 $K_{a,\nu}^{\mu}=\delta_\nu^{\mu}\mathcal L$ 的比较步骤，并据此得到能动张量。
- 板书中个别指标位置（如 $J_{a,\nu}^{\mu}$ 与 $T^\mu{}_{\nu}$ 的升降）依赖所采用的度规约定；本文保留板书记号，不擅自改变指标。

# 检查报告

## 严重问题

- 实标量势能的质量项符号与本节后面的自由标量拉格朗日量不一致。
- 矢量场势能的质量项符号与 Proca 拉格朗日量的约定不一致。
- Noether 流推导中“将第一项改写”的等式不满足乘积法则，导致中间推导逻辑不成立。
- 导数相互作用的“高于二阶”表述混淆了导数乘积次数和运动方程阶数。

## 疑似 OCR 问题

- 两处质量项符号可能来自板书转写或不同质量平方约定，需核对原图。
- Noether 推导的错误等式可能是抄录时漏写了 $K^\mu$ 或 $p^\mu\partial_\mu\Delta$ 项。
- 两处势能符号也可能来自板书中不同的质量平方约定，不能仅凭正文判定。

## 需要人工确认

- 复核图片 1 的标量/矢量势能符号。
- 复核图片 10--12 的 Noether 流中间步骤。
- 复核图片 13 是否默认时间端点边界条件。
- 复核图片 2--4 对导数阶数和 Hamiltonian 正定性的原始措辞。

## 总体评价

- 推导可靠性：Hamiltonian 的基本 Legendre 变换和 Noether 流最终形式可用，但中间推导存在确定性等式错误。
- 内容完整性：覆盖共轭动量、连续对称性、$U(1)$ 电流和时空平移。
- 学习适用性：可作为课堂记录，但质量项符号和 Noether 推导必须先核对。
- 是否建议人工复核：是，建议优先复核图片 1、10--12 和 13。
