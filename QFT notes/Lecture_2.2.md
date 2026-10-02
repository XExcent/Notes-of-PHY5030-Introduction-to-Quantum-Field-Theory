---
title: "量子场论导论 Lecture 2.2"
date: 2026-09-23
tags:
  - 量子场论导论
  - lecture
  - 洛伦兹变换
  - 平移群
  - 标量场
source: "课堂板书"
---

# Lecture 2.2: 场算符的时空变换与经典场论基础

## 本节内容概览

本节先回顾洛伦兹群、庞加莱群以及场算符的幺正表示。随后讨论标量场和矢量场在洛伦兹变换、时间平移及一般时空平移下的变换规律，并由平移算符引出四动量生成元和海森堡方程。后半部分转入经典场论，介绍实标量场的拉格朗日量、作用量、局域性、平移与洛伦兹不变性。最后通过作用量变分推导 Euler–Lagrange 方程，并讨论二次阶拉格朗日量、场重定义及线性场方程。

# 1. 洛伦兹变换与场算符

对应图片：

- 1
- 2
- 3
- 4

## 板书整理

### 上节回顾与幺正表示（图 1）

![[2.2/1.jpg]]

- 洛伦兹群与庞加莱群：$SO(3,1)$ 或 $ISO(3,1)$。
- 洛伦兹场（Lorentz fields）。
- 洛伦兹算符：对 $\Lambda\in SO(3,1)$，需要用算符表示洛伦兹变换：

$$
\lvert\Psi\rangle \xrightarrow{\ \Lambda\ } U(\Lambda)\lvert\Psi\rangle .
$$

- 表示的乘法规则：

$$
U(\Lambda_2\Lambda_1)=U(\Lambda_2)U(\Lambda_1).
$$

- 本节聚焦幺正表示：

$$
U^{-1}(\Lambda)=U^\dagger(\Lambda).
$$

### 态、内积与标量算符（图 2）

![[2.2/2.jpg]]

态在洛伦兹变换下变为

$$
\lvert\Psi\rangle \xrightarrow{\ \Lambda\ } U(\Lambda)\lvert\Psi\rangle .
$$

若 $U$ 是幺正的，则内积保持不变：

$$
\langle\Psi\vert\Psi\rangle
\xrightarrow{\ \Lambda\ }
\langle\Psi\vert U^\dagger U\vert\Psi\rangle
=\langle\Psi\vert\Psi\rangle .
$$

⚠️ **检查提醒：**

- 类型：符号疑似错误
- 问题：内积第一行的 bra/ket 顺序与下一行不一致。
- 分析：幺正变换应保持同一个内积的顺序；当前写法从 $\langle\Psi\vert\bar\Psi\rangle$ 变成 $\langle\bar\Psi\vert\Psi\rangle$，没有说明交换理由。
- 建议：对照原始板书，统一 $\bar\Psi$ 的 bra 记号和内积顺序。
- 置信度：高

在 Schrödinger 图像中，标量算符 $\hat{\mathbb{1}}$ 满足

$$
\hat{\mathbb{1}}
\xrightarrow{\ \Lambda\ }
\hat{\mathbb{1}}'
=U^\dagger(\Lambda)\hat{\mathbb{1}}U(\Lambda)
=\hat{\mathbb{1}}.
$$

前一等式对任意 Schrödinger 图像算符成立，后一等式给出标量算符的定义。

⚠️ **检查提醒：**

- 类型：表述不严谨
- 问题：前一句声称“前一等式对任意 Schrödinger 图像算符成立”，但这里展示的是单位算符 `$\hat{\mathbb 1}$` 的不变性。
- 分析：一般算符在变换下并不满足 `$U^\dagger\hat O U=\hat O$`；这只对不变算符（特别是单位算符）成立。
- 建议：确认原始板书是否想表达“变换规则适用于任意算符”，并将不变性只归于标量/单位算符。
- 置信度：高

### 标量场算符（图 3）

![[2.2/3.jpg]]

标量场算符的变换写作

$$
\hat\phi(x)\xrightarrow{\ \Lambda\ }
\hat\phi'(x')
=U^{-1}(\Lambda)\hat\phi(x')U(\Lambda)
=\hat\phi(x).
$$

坐标变换为

$$
x'^\mu=\Lambda^\mu{}_{\nu}x^\nu
\quad\Longrightarrow\quad
x'=\Lambda x
\quad\Longrightarrow\quad
x=\Lambda^{-1}x'.
$$

将 $x$ 与 $x'$ 重标记后，得到

$$
x'=\Lambda^{-1}x.
$$

因此标量场的协变变换律为

$$
\boxed{
U^\dagger(\Lambda)\hat\phi(x)U(\Lambda)
=\hat\phi\!\left(\Lambda^{-1}x\right)
}.
$$

### 矢量场算符（图 4）

![[2.2/4.jpg]]

对矢量场算符 $\hat V^\mu(x)$，板书给出

$$
\hat V^\mu(x)\xrightarrow{\ \Lambda\ }
\hat V'{}^\mu(x')
=U^\dagger(\Lambda)\hat V^\mu(x)U(\Lambda)
=\Lambda^\mu{}_{\nu}\hat V^\nu(x).
$$

⚠️ **检查提醒：**

- 类型：符号疑似错误
- 问题：该行把 $U^\dagger\hat V^\mu(x)U$ 直接写成 $\Lambda^\mu{}_{\nu}\hat V^\nu(x)$，但没有同时变换场的自变量。
- 分析：在固定坐标 $x$ 的协变变换律中应出现 $\hat V^\nu(\Lambda^{-1}x)$；下一条框出的公式才补上了这一点。
- 建议：确认图片 4 的等式究竟是在 $x'$ 处比较，还是在固定 $x$ 处比较，避免两种写法混用。
- 置信度：高

结合坐标变换，得到

$$
\boxed{
U^\dagger(\Lambda)\hat V^\mu(x)U(\Lambda)
=\Lambda^\mu{}_{\nu}\hat V^\nu\!\left(\Lambda^{-1}x\right)
}.
$$

板书随后推广到非齐次变换

$$
x'=\Lambda x+c,
$$

并引入相应的表示 $U(\Lambda,c)$。对标量场，例子为

$$
U^\dagger(\Lambda,c)\hat\phi(x)U(\Lambda,c)
=\hat\phi\!\left(\Lambda^{-1}(x-c)\right),
$$

其中

$$
x=\Lambda^{-1}(x'-c).
$$

## 解释

幺正算符保证态的内积和概率解释不变。标量场没有额外的洛伦兹指标，只改变其时空自变量；矢量场除改变自变量外，还由矩阵 $\Lambda^\mu{}_{\nu}$ 混合其分量。非齐次变换在洛伦兹变换之外加入平移 $c$，因此自变量变为 $\Lambda^{-1}(x-c)$。

# 2. 平移群、四动量与场的平移变换

对应图片：

- 5
- 6
- 7
- 8
- 9
- 10

## 板书整理

### 四动量算符与时间平移（图 5）

![[2.2/5.jpg]]

四动量算符定义为

$$
P^\mu=(H,\vec P),
$$

并满足厄米性

$$
P^{\mu\dagger}=P^\mu.
$$

时间平移

$$
t\longmapsto t'=t+c
$$

的关联算符为

$$
U(c)=e^{iHc}.
$$

由 $H^\dagger=H$，

$$
U^\dagger=e^{-iH^\dagger c}=e^{-iHc}=U^{-1},
$$

所以 $U$ 是幺正的。其表示性质为

$$
\begin{aligned}
U(c_1+c_2)
&=e^{iH(c_1+c_2)}\\
&=e^{iHc_1}e^{iHc_2}\\
&=U(c_1)U(c_2).
\end{aligned}
$$

### 时间平移下的标量场（图 6）

![[2.2/6.jpg]]

对标量算符，

$$
U^\dagger(c)\hat\phi(t,\vec x)U(c)
=\hat\phi(t-c,\vec x).
$$

代入 $U(c)=e^{iHc}$，得到

$$
e^{-iHc}\hat\phi(t,\vec x)e^{iHc}
=\hat\phi(t-c,\vec x).
$$

该式对任意 $c,t$ 成立。取 $c\to -t$ 且 $t=0$，得到

$$
\boxed{
e^{iHt}\hat\phi(0,\vec x)e^{-iHt}
=\hat\phi(t,\vec x)
}.
$$

因此 $H$ 是时间平移的生成元。

### 一般时空平移（图 7）

![[2.2/7.jpg]]

任意时空平移写作

$$
x'^{\mu}=x^\mu+c^\mu.
$$

场的变换关系为

$$
\boxed{
e^{-iP\cdot x}\hat\phi(0)e^{iP\cdot x}
=\hat\phi(x)
}.
$$

四维向量点积的记号为

$$
a\cdot b\equiv a^\mu b_\mu
=g_{\mu\nu}a^\mu b^\nu
=-a^0b^0+\vec a\cdot\vec b.
$$

特别地，

$$
P\cdot x=g_{\mu\nu}P^\mu x^\nu
=-Ht+\vec P\cdot\vec x.
$$

### Baker--Campbell--Hausdorff 公式（图 8）

![[2.2/8.jpg]]

板书给出的 BCH 公式为

$$
e^Ae^B
=\exp\!\left[A+B+\frac12[A,B]+\cdots\right].
$$

当

$$
[A,B]=0
$$

时，化为

$$
e^Ae^B=e^{A+B}.
$$

因此，若

$$
[P^\mu,P^\nu]=0,
$$

则

$$
U(c^\mu)=e^{-iP\cdot c}
$$

构成平移群的表示。

### 推导平移后的场（图 9）

![[2.2/9.jpg]]

在 $x+a$ 处评价场：

$$
e^{-iP\cdot(x+a)}\hat\phi(0)e^{iP\cdot(x+a)}
=\hat\phi(x+a).
$$

由于平移生成元彼此对易，

$$
e^{-iP\cdot a}e^{-iP\cdot x}\hat\phi(0)e^{iP\cdot x}e^{iP\cdot a}
=\hat\phi(x+a),
$$

即

$$
e^{-iP\cdot a}\hat\phi(x)e^{iP\cdot a}
=\hat\phi(x+a).
$$

取 $a^\mu$ 为无穷小量，

$$
\left[1-iP\cdot a\right]\hat\phi(x)
\left[1+iP\cdot a\right]
=\hat\phi(x)+a^\mu\partial_\mu\hat\phi(x)+\mathcal O(a^2),
$$

其中 $\mathcal O(a^2)$ 被忽略。

### 海森堡方程（图 10）

![[2.2/10.jpg]]

展开无穷小变换的左端：

$$
\hat\phi(x)-ia^\mu P_\mu\hat\phi(x)
+ia^\mu\hat\phi(x)P_\mu+\mathcal O(a^2)
=\hat\phi(x)+a^\mu\partial_\mu\hat\phi(x).
$$

因此

$$
\boxed{
\partial_\mu\hat\phi(x)=i[\hat\phi(x),P_\mu]
}
$$

这就是海森堡方程的四维形式。板书还注明

$$
P_0=-P^0\equiv-H.
$$

当 $\mu=0$ 时，

$$
\partial_t\hat\phi=-i[\hat\phi,H],
$$

等价地，

$$
i\partial_t\hat\phi=[\hat\phi,H].
$$

## 解释

平移算符由四动量生成。四动量分量彼此对易时，BCH 公式使有限平移可以写成单个指数。对平移参数作一阶展开，就把有限变换关系转化为场与生成元之间的对易关系，即海森堡运动方程。

# 3. 经典场论：作用量、局域性与对称性

对应图片：

- 11
- 12
- 13

## 板书整理

### 实标量场、拉格朗日量与作用量（图 11）

![[2.2/11.jpg]]

考虑实标量场 $\phi(x)$。拉格朗日量为

$$
L[\phi]=\int d^3x\,\mathcal L[\phi],
$$

其中 $\mathcal L[\phi]$ 是拉格朗日密度。作用量为

$$
S[\phi]=\int dt\,L[\phi]
=\int dt\,d^3x\,\mathcal L[\phi]
=\int d^4x\,\mathcal L[\phi].
$$

### 局域性（图 12）

![[2.2/12.jpg]]

一般情况下，板书写作

$$
\mathcal L[\phi]
=\mathcal L\!\left(\phi,\partial_\mu\phi,
\partial_\mu\partial_\nu\phi,\ldots;x^\mu\right).
$$

局域性要求 $\mathcal L$ 是局域泛函：$\phi(x)$、$\partial_\mu\phi(x)$ 等都在同一个 $x^\mu$ 处取值。

局域的例子：

$$
\mathcal L=\phi^2(x)+\partial_t\phi(x)
+\phi(x)\partial_x\phi(x)
\quad\longrightarrow\quad \text{local}.
$$

非局域的例子：

$$
\mathcal L=\phi(x)\phi(x+a)
\quad\longrightarrow\quad \text{not local}.
$$

### 平移不变性（图 13）

![[2.2/13.jpg]]

平移不变性要求对 $x^\mu$ 没有显式依赖。

例如

$$
\mathcal L=\phi^2(x)+t\,\phi(x)
\quad\longrightarrow\quad \text{not transl. invariant}.
$$

### 洛伦兹不变性与导数阶数（图 13）

洛伦兹不变性要求 $\mathcal L$ 是洛伦兹标量。例如

$$
\mathcal L=\phi^2(x)+\partial_t\phi(x)\,\partial_x\phi(x)
\quad\longrightarrow\quad \text{not Lorentz invariant}.
$$

通常假设

$$
\mathcal L=\mathcal L(\phi,\partial_\mu\phi),
$$

即不含二阶或更高阶导数。

## 解释

拉格朗日密度是局域的，意味着理论在一个时空点的密度只依赖该点的场及其导数。没有显式坐标依赖对应平移不变性；把指标按洛伦兹协变方式收缩成标量，则保证洛伦兹不变性。限制到一阶导数后，作用量变分可直接得到通常形式的 Euler–Lagrange 方程。

# 4. Euler–Lagrange 方程与二次阶实标量场

对应图片：

- 14
- 15
- 16
- 17
- 18

## 板书整理

### 最小作用量原理与变分（图 14）

![[2.2/14.jpg]]

Euler–Lagrange（EL）方程来自最小作用量原理：作用量在无穷小变分下必须是 stationary。场的变分为

$$
\phi(x)\longrightarrow\phi(x)+\delta\phi(x),
$$

并要求边界处

$$
\left.\delta\phi(x)\right|_{|x|\to\infty}=0,
\qquad
\left.\partial_\mu\delta\phi(x)\right|_{|x|\to\infty}=0.
$$

作用量的一阶变分为

$$
\begin{aligned}
\delta S
&=\int d^4x\,\delta\mathcal L\\
&=\int d^4x\left[
\frac{\partial\mathcal L}{\partial\phi}\,\delta\phi
+\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\,\partial_\mu\delta\phi
\right].
\end{aligned}
$$

这里使用了

$$
\partial_\mu\delta\phi=\delta(\partial_\mu\phi).
$$

### 分部积分与 EL 方程（图 15）

![[2.2/15.jpg]]

对含有 $\partial_\mu\delta\phi$ 的项分部积分：

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\partial_\mu\delta\phi
=\partial_\mu\left[
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\delta\phi
\right]
-\partial_\mu\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\right)\delta\phi.
$$

边界项记为

$$
J(\partial)=\left.\partial_\mu\left[
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\delta\phi
\right]\right|_{|x|\to\infty}=0.
$$

所以

$$
\delta S
=\int d^4x\left[
\frac{\partial\mathcal L}{\partial\phi}
-\partial_\mu\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\right)
\right]\delta\phi.
$$

由于 $\delta\phi$ 是任意的，得到 EL 方程

$$
\boxed{
\frac{\partial\mathcal L}{\partial\phi}
-\partial_\mu\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\right)=0
}.
$$

### 二次阶拉格朗日量（图 16）

![[2.2/16.jpg]]

在 $\phi$ 中取最一般的二次阶形式时，EL 方程是线性的。板书给出

$$
\mathcal L
=a\,\partial^\mu\phi\,\partial_\mu\phi
+b\,\phi^2+c\,\phi,
$$

其中 $a,b,c$ 是常数，并且

$$
\partial^\mu\phi\,\partial_\mu\phi
=g^{\mu\nu}\partial_\mu\phi\,\partial_\nu\phi
= (\partial\phi)^2.
$$

板书还指出，若 $d^\mu$ 是常数，线性导数项

$$
d^\mu\partial_\mu\phi
$$

不满足这里要求的洛伦兹标量形式（板书以叉号标记）。

### 消去线性项 $c$：场重定义（图 17）

![[2.2/17.jpg]]

板书通过变量变换消去 $c$：

$$
\begin{aligned}
\mathcal L
={}&a\,\partial^\mu\left(\phi+\frac{c}{2b}\right)
\partial_\mu\left(\phi+\frac{c}{2b}\right)
+b\left(\phi+\frac{c}{2b}\right)^2
-\frac{c^2}{4b}.
\end{aligned}
$$

定义场重定义

$$
\widetilde\phi\equiv\phi+\frac{c}{2b}.
$$

则

⚠️ **检查提醒：**

- 类型：缺少条件
- 问题：用 $\widetilde\phi=\phi+c/(2b)$ 消去线性项时没有说明 $b\ne0$。
- 分析：该重定义和常数项 $-c^2/(4b)$ 都要求可以除以 $b$；当 $b=0$ 时必须单独处理线性项。
- 建议：结合原始板书确认是否已假定 $b\ne0$，并在理解推导时保留这一条件。
- 置信度：高

$$
\mathcal L
=a\,\partial^\mu\widetilde\phi\,\partial_\mu\widetilde\phi
+b\,\widetilde\phi^2.
$$

常数项 $-c^2/(4b)$ 不影响 EL 方程，因此可以忽略。板书指出，在 QFT 中通常要求零场构型是 EL 方程的解；这促使我们使用不含 $c$ 的场 $\widetilde\phi$ 作为更基本的变量。

### 原变量的 EL 方程（图 18）

![[2.2/18.jpg]]

对原来的 $\phi$，板书给出的 EL 方程为

$$
-2a\,\square\phi+2b\,\phi+c=0.
$$

⚠️ **检查提醒：**

- 类型：符号疑似错误
- 问题：这里使用 $\square$，而本节前文及相关讲义统一使用 $\Box$ 表示 d'Alembert 算符。
- 分析：若不是有意引入新记号，可能是 OCR 或 LaTeX 转写导致的符号变化；两者不能在未定义时混用。
- 建议：查看图片 18，确认原始符号并统一记号。
- 置信度：中

因此 $\phi=0$ 只有在

$$
c=0
$$

时才是解。于是，在 QFT 中通常考虑 $\widetilde\phi$（即不含 $c$ 的形式），以便零场构型满足 EL 方程并对应零粒子态。

## 解释

EL 方程来自对作用量做任意、且在边界消失的场变分。分部积分把导数从变分 $\delta\phi$ 上移走，边界项因边界条件消失，剩下的系数必须逐点为零。二次阶拉格朗日量给出线性场方程；线性项可通过常数平移进行场重定义，产生的纯常数只改变作用量的整体常数，不改变 EL 方程。

# 本节知识结构

洛伦兹群与幺正表示
↓
标量场、矢量场的协变变换
↓
平移群与四动量生成元
↓
无穷小平移与海森堡方程
↓
经典实标量场的作用量
↓
局域性、平移不变性与洛伦兹不变性
↓
作用量变分与 Euler–Lagrange 方程
↓
二次阶拉格朗日量与场重定义

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $U(\Lambda_2\Lambda_1)=U(\Lambda_2)U(\Lambda_1)$ | 群表示的乘法规则 |
| $U^\dagger(\Lambda)\hat\phi(x)U(\Lambda)=\hat\phi(\Lambda^{-1}x)$ | 标量场的洛伦兹变换 |
| $U^\dagger(\Lambda)\hat V^\mu(x)U(\Lambda)=\Lambda^\mu{}_{\nu}\hat V^\nu(\Lambda^{-1}x)$ | 矢量场的洛伦兹变换 |
| $U(c)=e^{iHc}$ | 时间平移算符 |
| $e^{-iP\cdot x}\hat\phi(0)e^{iP\cdot x}=\hat\phi(x)$ | 四动量生成时空平移 |
| $\partial_\mu\hat\phi=i[\hat\phi,P_\mu]$ | 海森堡方程的四维形式 |
| $S[\phi]=\int d^4x\,\mathcal L[\phi]$ | 场论作用量 |
| $\dfrac{\partial\mathcal L}{\partial\phi}-\partial_\mu\left(\dfrac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\right)=0$ | Euler–Lagrange 方程 |
| $-2a\square\phi+2b\phi+c=0$ | 二次阶实标量场的 EL 方程 |

# 检查报告

## 严重问题

- 暂未发现平移生成元或 Euler–Lagrange 主结论的确定性致命错误。

## 疑似 OCR 问题

- 内积的 bra/ket 顺序前后不一致。
- 矢量场变换的一行省略了自变量变换，可能是板书在不同坐标点之间切换造成的转写问题。
- 场方程中 `$\square$` 与前文 `$\Box$` 的记号不一致。

## 需要人工确认

- 复核图片 2、4、18，确认内积顺序、矢量场比较点和 d'Alembert 算符符号。
- 复核场重定义是否明确假定 `$b\ne0$`。

## 总体评价

- 推导可靠性：平移群、BCH 展开和 EL 方程主体推导基本连贯。
- 内容完整性：覆盖场算符变换、四动量生成元、局域性和场重定义。
- 学习适用性：适合作为学习笔记，但需先统一变换约定和算符记号。
- 是否建议人工复核：是，重点复核上述三处记号问题。
