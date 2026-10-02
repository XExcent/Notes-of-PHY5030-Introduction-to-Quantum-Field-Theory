---
title: "量子场论导论 Lecture 2.1"
date: 2026-09-23
tags:
  - 量子场论导论
  - lecture
  - 洛伦兹变换
  - 洛伦兹场
source: "课堂板书"
---

# Lecture 2.1: 洛伦兹变换、洛伦兹场与场的表示

## 本节内容概览

本节从上节的闵可夫斯基度规和洛伦兹变换出发，先整理行列式、proper/ improper 以及 orthochronous 的分类。随后引入无穷小洛伦兹变换，得到生成元矩阵的反对称性，并数出三维旋转与 boost 一共六个独立参数。板书接着介绍 Poincaré 群和标量、矢量、协矢量及张量场的变换规律，说明指标收缩给出洛伦兹标量，并以 Klein–Gordon、Gauss 和 Maxwell 方程为例。最后提出相对论性基本方程的洛伦兹不变性公设，并引入 Hilbert 空间上的幺正表示 $U(\Lambda)$。

# 1. 洛伦兹变换的回顾与分类

对应图片：

- 1
- 2
- 3
- 4
- 5

## 板书整理

![[2.1/1.jpg]]

### 上节回顾

板书将量子场论类比为无限多个（连续的）量子谐振子，并回顾洛伦兹不变性。采用

$$
g=\operatorname{diag}(-1,1,1,1),
$$

洛伦兹矩阵满足

$$
g_{\mu\nu}\Lambda^{\mu}{}_{\rho}\Lambda^{\nu}{}_{\sigma}=g_{\rho\sigma}.
$$

矩阵属于 $O(3,1)$，也可写成

$$
g^{-1}\Lambda^{T}g=\Lambda^{-1}.
$$

这里的 $g$ 被板书称为 pseudo-orthogonal matrix（伪正交矩阵）；与普通正交矩阵相应的关系是 $R^{-1}=R^T$。升降指标例如

$$
V^{\mu}=g^{\mu\nu}V_{\nu}.
$$

![[2.1/2.jpg]]

### 混合指标与逆矩阵

考虑混合指标的洛伦兹矩阵：

$$
\Lambda_{\mu}{}^{\nu}
=g_{\mu\rho}g^{\nu\sigma}\Lambda^{\rho}{}_{\sigma}
=g_{\mu\rho}\Lambda^{\rho}{}_{\sigma}g^{\sigma\nu}
=\left[g\Lambda g^{-1}\right]_{\mu}{}^{\nu}.
$$

按照矩阵乘法的行、列顺序，板书进一步写成

$$
\Lambda_{\mu}{}^{\nu}
=\left[g^{-1}\Lambda^Tg\right]^{\nu}{}_{\mu}
=\left(\Lambda^{-1}\right)^{\nu}{}_{\mu}.
$$

因此

$$
\boxed{\Lambda_{\mu}{}^{\nu}=\left(\Lambda^{-1}\right)^{\nu}{}_{\mu}}.
$$

#### 行列式

对 $g^{-1}\Lambda^Tg=\Lambda^{-1}$ 取行列式：

$$
\det(g^{-1})\det(\Lambda^T)\det(g)=\det(\Lambda^{-1}).
$$

利用

$$
\det(M^T)=\det(M),\qquad \det(M^{-1})=\frac{1}{\det M},\qquad \det g=-1,
$$

得到

$$
\det\Lambda=\frac{1}{\det\Lambda},
\qquad
(\det\Lambda)^2=1.
$$

![[2.1/3.jpg]]

因此

$$
\det\Lambda=
\begin{cases}
+1,&\text{proper},\\
-1,&\text{improper}.
\end{cases}
$$

proper Lorentz transformations 构成子群

$$
SO(3,1).
$$

板书随后区分时间方向。取 $\rho=\sigma=0$，由不变性条件得到

$$
g_{\mu\nu}\Lambda^{\mu}{}_{0}\Lambda^{\nu}{}_{0}=g_{00}=-1.
$$

展开为

$$
g_{00}(\Lambda^{0}{}_{0})^2
+g_{11}(\Lambda^{1}{}_{0})^2
+g_{22}(\Lambda^{2}{}_{0})^2
+g_{33}(\Lambda^{3}{}_{0})^2=-1,
$$

即

$$
-(\Lambda^{0}{}_{0})^2+\delta_{ij}\Lambda^{i}{}_{0}\Lambda^{j}{}_{0}=-1,
\qquad i,j\in\{1,2,3\}.
$$

所以

$$
(\Lambda^{0}{}_{0})^2
=1+\delta_{ij}\Lambda^{i}{}_{0}\Lambda^{j}{}_{0}\ge 1.
$$

因此

$$
\Lambda^{0}{}_{0}\ge 1
\quad\Longrightarrow\quad
\text{orthochronous},
$$

表示保持时间方向；而

$$
\Lambda^{0}{}_{0}\le -1
\quad\Longrightarrow\quad
\text{non-orthochronous}.
$$

![[2.1/4.jpg]]

### 正常洛伦兹群

板书定义同时 proper 且 orthochronous 的变换构成的子群：

$$
SO^+(3,1).
$$

![[2.1/5.jpg]]

该子群是一个连续的 Lie group。若

$$
\Lambda\in SO^+(3,1),
$$

则 $\Lambda$ 可以沿连续路径连接到单位元。

## 解释

$O(3,1)$ 保持闵可夫斯基度规，但可能同时改变空间取向或时间方向。$\det\Lambda=+1$ 选出 proper 变换；$\Lambda^0{}_0\ge1$ 选出保持未来时间方向的 orthochronous 变换。两项条件同时满足时得到物理中最常用的 $SO^+(3,1)$。

# 2. 无穷小变换与洛伦兹群的参数

对应图片：

- 6
- 7
- 8

## 板书整理

![[2.1/6.jpg]]

在单位元附近写无穷小变换：

$$
\Lambda^{\mu}{}_{\nu}
=\delta^{\mu}{}_{\nu}+\varepsilon\,\Omega^{\mu}{}_{\nu},
$$

其中 $\Omega^{\mu}{}_{\nu}$ 是某个矩阵，$\varepsilon$ 为无穷小参数。其逆矩阵写作

$$
\left(\Lambda^{-1}\right)^{\mu}{}_{\nu}
=\delta^{\mu}{}_{\nu}-\varepsilon\,\Omega^{\mu}{}_{\nu},
$$

忽略 $O(\varepsilon^2)$。

由 $\Lambda^{-1}\Lambda=1$ 验证：

$$
\begin{aligned}
\left(\Lambda^{-1}\right)^{\mu}{}_{\rho}\Lambda^{\rho}{}_{\nu}
&=(\delta^{\mu}{}_{\rho}-\varepsilon\Omega^{\mu}{}_{\rho})
(\delta^{\rho}{}_{\nu}+\varepsilon\Omega^{\rho}{}_{\nu})\\
&=\delta^{\mu}{}_{\nu}
-\varepsilon\Omega^{\mu}{}_{\nu}
+\varepsilon\Omega^{\mu}{}_{\nu}
+O(\varepsilon^2)\\
&=\delta^{\mu}{}_{\nu}.
\end{aligned}
$$

![[2.1/7.jpg]]

洛伦兹条件给出

$$
\Lambda_{\mu\rho}
=g_{\mu\rho}+\varepsilon\Omega_{\mu\rho}
=g_{\rho\mu}-\varepsilon\Omega_{\rho\mu},
$$

从而

$$
\boxed{\Omega_{\mu\rho}=-\Omega_{\rho\mu}}.
$$

![[2.1/8.jpg]]

因此 $\Omega_{\mu\nu}$ 是一个 $4\times4$ 的反对称矩阵，只有

$$
\frac{4(4-1)}{2}=6
$$

个独立分量。对 $\Lambda\in SO^+(3,1)$，这六个参数可分为：

- 三个三维旋转参数；
- 三个三维 boost 参数。

板书旁注还写有 “QQ group with TA”，未在图片中进一步定义。

## 解释

反对称性是无穷小洛伦兹条件的一阶形式。六个独立生成方向对应三维空间中的三个旋转和三个 boost；有限洛伦兹变换可由这些无穷小变换连续生成。

# 3. Improper 变换、Poincaré 群与 Lorentz fields

对应图片：

- 9
- 10

## 板书整理

![[2.1/9.jpg]]

### Improper transformations

板书指出 improper transformations 只增加两个离散的独立变换：

1. parity transformation $P$（空间反演）；
2. time-reversal transformation $T$（时间反演）。

通常可写为

$$
P^{\mu}{}_{\nu}=\operatorname{diag}(1,-1,-1,-1),
$$

$$
T^{\mu}{}_{\nu}=\operatorname{diag}(-1,1,1,1).
$$

板书将含有平移的群记作 Poincaré group：

$$
ISO(3,1).
$$

其作用为

$$
x^{\mu}\longmapsto x'^{\mu}
=\Lambda^{\mu}{}_{\nu}x^{\nu}+C^{\mu},
$$

其中 $C^{\mu}$ 是 constant vector。

![[2.1/10.jpg]]

### Lorentz fields

时空坐标记作

$$
x=(t,x,y,z)\quad\text{或}\quad (t,\vec x).
$$

标量场 $\phi(x)$ 在洛伦兹变换下满足

$$
\phi(x)\longmapsto \phi'(x')=\phi(x).
$$

矢量场和协矢量场分别记作 $V^{\mu}(x)$ 与 $W_{\mu}(x)$，变换规律为

$$
V^{\mu}(x)\longmapsto V'^{\mu}(x')
=\Lambda^{\mu}{}_{\nu}V^{\nu}(x),
$$

$$
W_{\mu}(x)\longmapsto W'_{\mu}(x')
=\Lambda_{\mu}{}^{\nu}W_{\nu}(x).
$$

## 解释

标量没有 Lorentz 指标，因此变换后数值相同；矢量的上指标乘以 $\Lambda$，协矢量的下指标乘以带混合指标的 $\Lambda_{\mu}{}^{\nu}$。Poincaré 群在 Lorentz 变换之外还包括时空平移。

# 4. 指标收缩、四动量与不变微分算子

对应图片：

- 11
- 12

## 板书整理

![[2.1/11.jpg]]

板书定义 $V^{\mu}$ 与 $W_{\mu}$ 的 contraction：

$$
V^{\mu}W_{\mu}.
$$

验证其为标量：

$$
\begin{aligned}
V'^{\mu}W'_{\mu}
&=\Lambda^{\mu}{}_{\rho}V^{\rho}\,
\Lambda_{\mu}{}^{\sigma}W_{\sigma}\\
&=\Lambda^{\mu}{}_{\rho}
\left(\Lambda^{-1}\right)^{\sigma}{}_{\mu}
V^{\rho}W_{\sigma}\\
&=\delta^{\sigma}{}_{\rho}V^{\rho}W_{\sigma}
=V^{\rho}W_{\rho}.
\end{aligned}
$$

因此一次上、下指标收缩得到 Lorentz scalar。

![[2.1/12.jpg]]

### 四动量和标量梯度

四动量为

$$
p^{\mu}=(E,\vec p),
\qquad E\equiv p^0,
$$

其中 $E$ 是粒子的能量。标量的梯度写作

$$
\partial_{\mu}\phi
=\left(\frac{\partial\phi}{\partial t},\nabla\phi\right),
$$

⚠️ **检查提醒：**

- 类型：定义问题
- 问题：这里将 $\partial_\mu\phi$“按板书作为矢量场处理”，但带下标的 $\partial_\mu$ 在指标记号中是协变矢量（covector）。
- 分析：在度规 $(-,+,+,+)$ 下，$\partial^\mu\phi=g^{\mu\nu}\partial_\nu\phi$ 才是上指标对象；后文的收缩和升降指标依赖这一区别。
- 建议：确认板书是否只是口语化称呼，并在学习时区分梯度的协变分量与逆变分量。
- 置信度：高

它按板书作为矢量场处理。

### D'Alembertian

$$
\Box\phi\equiv g^{\mu\nu}\partial_{\mu}\partial_{\nu}\phi
=\partial^{\mu}\partial_{\mu}\phi.
$$

展开为

$$
\begin{aligned}
\Box\phi
&=g^{00}\partial_0\partial_0\phi
+g^{ij}\partial_i\partial_j\phi\\
&=-\frac{\partial^2\phi}{\partial t^2}+\nabla^2\phi.
\end{aligned}
$$

它是一个 Lorentz scalar，通常称为 wave operator。

## 解释

收缩中的重复指标是求和指标（dummy index），而未被求和的指标是 free index。洛伦兹变换矩阵与其逆矩阵相乘产生 Kronecker delta，从而使收缩量不变。

# 5. 张量场与洛伦兹不变方程

对应图片：

- 13
- 14

## 板书整理

![[2.1/13.jpg]]

板书给出 Klein–Gordon 方程的例子：

$$
\Box\phi=0.
$$

该方程是 Lorentz invariant。

张量场的例子包括

$$
A^{\mu\nu}(x),
\qquad B_{\mu\nu}(x),
\qquad C^{\mu}{}_{\nu}(x),
\qquad D^{\mu\nu}{}_{\rho\sigma\tau}(x).
$$

一般的二阶张量场变换为

$$
A^{\mu\nu}(x)\longmapsto A'^{\mu\nu}(x')
=\Lambda^{\mu}{}_{\rho}\Lambda^{\nu}{}_{\sigma}
A^{\rho\sigma}(x).
$$

更一般地，$n$ 个指标的张量经梯度运算后成为具有 $n+1$ 个指标的张量。板书写作

$$
D^{\mu\nu}{}_{\rho\sigma\tau}(x)
\longmapsto
D'^{\mu\nu}{}_{\rho\sigma\tau}(x')
=\Lambda^{\mu}{}_{\alpha}\Lambda^{\nu}{}_{\beta}
\Lambda_{\rho}{}^{\gamma}\Lambda_{\sigma}{}^{\delta}
\Lambda_{\tau}{}^{\epsilon}
D^{\alpha\beta}{}_{\gamma\delta\epsilon}(x).
$$

![[2.1/14.jpg]]

### Faraday tensor

电磁场的 Faraday tensor 记作 $F_{\mu\nu}$。其齐次 Maxwell（Gauss）方程为

$$
\partial_{\mu}F_{\rho\sigma}
+\partial_{\rho}F_{\sigma\mu}
+\partial_{\sigma}F_{\mu\rho}=0.
$$

⚠️ **检查提醒：**

- 类型：表述不严谨
- 问题：该三指标恒等式被称作“齐次 Maxwell（Gauss）方程”，但它是 Faraday 张量的 Bianchi 恒等式，不能只等同于 Gauss 定律。
- 分析：展开到三维分量后才分别包含磁 Gauss 定律和 Faraday 感应定律；“Gauss 方程”通常只指其中一个分量关系。
- 建议：结合原始板书确认标题，学习时将其标为齐次 Maxwell 方程或 Bianchi 恒等式。
- 置信度：高

这里梯度指标与 $F$ 的两个指标一起构成三个指标；重复指标按求和规则处理。

非齐次 Maxwell 方程（板书所示无源形式）为

$$
\partial_{\mu}F^{\mu\nu}=0.
$$

其中 $\mu$ 被 contraction，$\nu$ 是一个 free index，因此左边是 vector field。

验证其洛伦兹不变性：

$$
\left(\partial_{\mu}F^{\mu\nu}\right)'
=\Lambda^{\nu}{}_{\rho}\partial_{\mu}F^{\mu\rho}=0,
$$

所以 Maxwell equation 是 Lorentz invariant。

## 解释

张量方程的指标结构决定其变换性质：所有指标都收缩时得到标量；保留一个 free index 时得到矢量；保留更多 free indices 时得到相应阶数的张量。因此方程两边具有相同的张量类型，等式在洛伦兹变换下保持成立。

# 6. 相对论性公设与 Hilbert 空间中的幺正表示

对应图片：

- 15
- 16

## 板书整理

![[2.1/15.jpg]]

### Relativity 的公设

板书写出相对论性公设：

> 物理学中的所有基本方程都是 Lorentz invariant。

### Lorentz operators

板书将 $SO(3,1)$ 的表示描述为作用在 Hilbert space 中的算符集合 $U(\Lambda)$。对每一个

$$
\Lambda\in SO(3,1)
$$

关联一个算符 $U(\Lambda)$。

![[2.1/16.jpg]]

表示满足群乘法：

$$
\boxed{U(\Lambda_1\Lambda_2)=U(\Lambda_1)U(\Lambda_2)}.
$$

在 QFT 中主要关心幺正表示：

$$
\boxed{U^{\dagger}(\Lambda)=U^{-1}(\Lambda)}.
$$

板书最后注明，对于 Poincaré 群同样可写

$$
U(\Lambda,C).
$$

## 解释

幺正性保证 Hilbert 空间内积和概率解释在洛伦兹变换下保持不变。表示的乘法关系把时空中的群乘法转化为 Hilbert 空间算符的乘法。

# 本节知识结构

闵可夫斯基度规与洛伦兹条件
↓
行列式、proper/improper 与 orthochronous 分类
↓
无穷小变换与反对称生成元
↓
$SO^+(3,1)$ 的六个参数（旋转与 boost）
↓
Poincaré 群与 Lorentz fields
↓
指标收缩、标量、矢量和张量变换
↓
Lorentz 不变方程与 Hilbert 空间幺正表示

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $g_{\mu\nu}\Lambda^{\mu}{}_{\rho}\Lambda^{\nu}{}_{\sigma}=g_{\rho\sigma}$ | 洛伦兹变换保持闵可夫斯基度规 |
| $g^{-1}\Lambda^Tg=\Lambda^{-1}$ | 洛伦兹矩阵的逆矩阵关系 |
| $(\det\Lambda)^2=1$ | 洛伦兹变换的行列式为 $\pm1$ |
| $(\Lambda^0{}_0)^2=1+\delta_{ij}\Lambda^i{}_0\Lambda^j{}_0$ | orthochronous 分类的依据 |
| $\Lambda^{\mu}{}_{\nu}=\delta^{\mu}{}_{\nu}+\varepsilon\Omega^{\mu}{}_{\nu}$ | 无穷小洛伦兹变换 |
| $\Omega_{\mu\nu}=-\Omega_{\nu\mu}$ | 无穷小生成元的反对称性 |
| $x'^{\mu}=\Lambda^{\mu}{}_{\nu}x^{\nu}+C^{\mu}$ | Poincaré 群作用 |
| $\phi'(x')=\phi(x)$ | 标量场变换 |
| $V'^{\mu}(x')=\Lambda^{\mu}{}_{\nu}V^{\nu}(x)$ | 矢量场变换 |
| $W'_{\mu}(x')=\Lambda_{\mu}{}^{\nu}W_{\nu}(x)$ | 协矢量场变换 |
| $\Box\phi=-\partial_t^2\phi+\nabla^2\phi$ | D'Alembertian |
| $\partial_{\mu}F^{\mu\nu}=0$ | 无源 Maxwell 方程 |
| $U(\Lambda_1\Lambda_2)=U(\Lambda_1)U(\Lambda_2)$ | 群的算符表示 |
| $U^{\dagger}(\Lambda)=U^{-1}(\Lambda)$ | 幺正表示条件 |

# 推导逻辑与内容正确性检查

- 图片 2 中从 $g^{-1}\Lambda^Tg=\Lambda^{-1}$ 到 $\Lambda_{\mu}{}^{\nu}=(\Lambda^{-1})^{\nu}{}_{\mu}$ 的步骤依赖行、列指标的排列；按板书的混合指标定义，矩阵乘法顺序是一致的。
- 图片 3 的行列式推导使用 $\det(M^T)=\det M$ 和 $\det(M^{-1})=1/\det M$，因此得到 $(\det\Lambda)^2=1$。
- 图片 4 中空间项 $\delta_{ij}\Lambda^i{}_0\Lambda^j{}_0$ 非负，所以确实推出 $|\Lambda^0{}_0|\ge1$。
- 图片 6–7 的无穷小逆矩阵只保留 $O(\varepsilon)$，$O(\varepsilon^2)$ 项按板书标记为忽略；一阶交叉项相消。
- 图片 11 的收缩不变性使用 $\Lambda^{\mu}{}_{\rho}(\Lambda^{-1})^{\sigma}{}_{\mu}=\delta^{\sigma}{}_{\rho}$，推导成立。
- 图片 12 的度规符号为 $(-,+,+,+)$，因此 D'Alembertian 的时间项带负号，与板书展开一致。
- 图片 14 的 Maxwell 方程在无源情形写成 $\partial_{\mu}F^{\mu\nu}=0$；板书没有引入电流项，因此未自行添加源项。

以上检查只用于核对推导，未修改任何板书公式。

# 检查报告

## 严重问题

- 暂未发现主要洛伦兹群推导中会直接改变结论的确定性错误。

## 疑似 OCR 问题

- $\partial_\mu\phi$ 被称为矢量场可能是板书口语或转写造成的术语混用。
- 齐次 Maxwell 方程被标为“Gauss”可能是板书标题的简写，需核对图片。

## 需要人工确认

- 复核图片 12 中梯度对象的指标位置。
- 复核图片 14 中 Maxwell 方程的原始标题和所指的具体分量。

## 总体评价

- 推导可靠性：洛伦兹条件、无穷小变换和六个生成参数的推导基本可靠。
- 内容完整性：覆盖 proper/improper、Poincaré 群、张量变换和幺正表示。
- 学习适用性：适合作为学习笔记，但需严格区分协变/逆变指标及齐次 Maxwell 方程的名称。
- 是否建议人工复核：是，重点复核上述术语和指标位置。
