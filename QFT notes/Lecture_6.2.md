---
title: "量子场论导论 Lecture 6.2"
date: 2026-10-16
tags:
  - 量子场论导论
  - lecture
  - 推迟传播子
  - 费曼传播子
  - 时间排序
  - 散射矩阵
  - 散射截面
source: "课堂板书"
---

# Lecture 6.2: 推迟传播子的初值解、费曼传播子与散射截面

## 本节内容概览

本节先回顾推迟传播子的定义与格林函数方程，在空间 Fourier 表象中通过连续性和导数跳跃条件求解，并讨论脉冲源作用下的标量场。随后引入费曼传播子的极点处方，通过围道积分将其写成两个真空二点函数的组合，再定义时间排序符号。课程接着转向散射实验中的渐近态、跃迁概率与散射矩阵。最后定义散射截面和入射强度，并将散射粒子数与入射粒子数之比解释为散射概率。

<!-- date 为整理日期；原板书未标明授课日期。正文按 Picture/6.2/1.jpg 至 14.jpg 的顺序整理。板书采用 p²=−(p⁰)²+⃗p² 的度规约定。检查注释与板书原文分开，未用建议公式替换原式。 -->

---

# 1. 上节回顾：波函数、多粒子态与推迟传播子

对应图片：

- 1

## 板书整理

![[Picture/6.2/1.jpg]]

上节内容（Last time）：

- 波函数与 $N$ 粒子态（Wave-function and $N$-particle states）。
- 传播子即格林函数（Propagators = Green functions）。

推迟传播子（Retarded propagator）：

$$
D_R(x-y)=\Theta(x^0-y^0)\langle0|[\phi(x),\phi(y)]|0\rangle.
$$

它满足：

$$
(\Box-m^2)D_R(x)=i\delta^4(x).
\tag{*}
$$

推迟边界条件为：

$$
D_R(t,\vec x)=0,\qquad t<0.
$$

因此可用于初值问题（initial value problems），初始条件设在 $t=0$。

## 解释

$\Theta$ 是阶跃函数，保证推迟传播子在负时间差时为零。本课的 $D_R$ 定义中没有额外的整体 $i$ 因子，格林函数方程右边相应为 $i\delta^4(x)$；后续计算需沿用这一归一化。

---

# 2. 空间 Fourier 变换与初始时刻的匹配条件

对应图片：

- 2

## 板书整理

![[Picture/6.2/2.jpg]]

在 Fourier 空间中：

$$
D_R(t,\vec x)
=\int\frac{d^3k}{(2\pi)^3}\,
\widetilde D_R(t,\vec k)e^{i\vec k\cdot\vec x},
\qquad
\delta(\vec x)=\int\frac{d^3k}{(2\pi)^3}e^{i\vec k\cdot\vec x}.
$$

由式 $(*)$ 得：

$$
\left[-\partial_t^2-\omega_k^2\right]\widetilde D_R
=i\delta(t),
\qquad
\widetilde D_R=0\quad(t<0).
$$

当 $t>0$ 时，解为：

$$
\widetilde D_R=A\sin\omega_k t+B\cos\omega_k t.
$$

在 $t=0$ 处要求连续：

$$
\widetilde D_R(0^+,\vec k)
=\widetilde D_R(0^-,\vec k)=0
\quad\Longrightarrow\quad B=0.
$$

在 $t=0$ 两侧积分，并取 $\epsilon\to0$：

$$
\int_{-\epsilon}^{\epsilon}dt\,
\left[\partial_t^2\widetilde D_R+
\omega_k^2\widetilde D_R\right]=-i.
$$

板书将 $\omega_k^2\widetilde D_R$ 的积分项标为趋于零，因此：

$$
\partial_t\widetilde D_R(0^+,\vec k)
-\partial_t\widetilde D_R(0^-,\vec k)=-i.
$$

最终得到：

$$
A=-\frac{i}{\omega_k}.
$$

> 此处使用了 $\delta(t)$ 在原点邻域积分为 $1$ 的性质，以及 $t<0$ 时解及其时间导数均为零的条件。

## 解释

空间 Fourier 变换把场方程化为每个动量模的常微分方程。连续性确定余弦项系数，而脉冲源导致一阶时间导数发生跳跃，从而确定正弦项系数。

---

# 3. 推迟解与脉冲源标量场例题

对应图片：

- 3

## 板书整理

![[Picture/6.2/3.jpg]]

承接上一张板书：

$$
\widetilde D_R(t,\vec k)
=-i\Theta(t)\frac{\sin\omega_k t}{\omega_k},
\qquad
\omega_k\equiv\sqrt{\vec k^{\,2}+m^2}.
$$

例题：带脉冲源的标量场（Scalar field with impulse source）。给定：

$$
J(x)=j(\vec x)\delta(t),
\qquad
\phi(t,\vec x)=0\quad(t<0),
$$

求 $t>0$ 时的 $\phi$。

拉格朗日量密度与运动方程为：

$$
\mathcal L=-\frac12(\partial\phi)^2
-\frac{m^2}{2}\phi^2+\phi J
\quad\Longrightarrow\quad
(\Box-m^2)\phi=-J.
$$

板书给出的结果为：

$$
\phi_{\vec k}(t)
=\Theta(t)j_{\vec k}\frac{\sin\omega_k t}{\omega_k},
$$

其中：

$$
j_{\vec k}
=\int d^3x\,j(\vec x)e^{-i\vec k\cdot\vec x}.
$$

> 此处使用了 Euler–Lagrange 方程，并沿用上一部分对脉冲源方程的匹配条件；板书直接给出各动量模的解，未展开进一步计算。

## 解释

脉冲源只在 $t=0$ 起作用；此后每个动量模按频率 $\omega_k$ 自由振荡。场的响应与 $\widetilde D_R$ 相差相应的源系数和 $i$ 因子，这是由两者方程右边分别为 $-J$ 与 $i\delta$ 决定的。

---

# 4. 从推迟极点处方引入费曼传播子

对应图片：

- 4

## 板书整理

![[Picture/6.2/4.jpg]]

板书原述：初值问题需要选择时间方向，因此“破坏”洛伦兹不变性（Initial value problems “break” Lorentz invariance because they require a choice of time direction）。由此写出：

> Retarded propagator is not Lorentz invariant.
>
> 推迟传播子不是洛伦兹不变的。

推迟传播子的积分表示为：

$$
D_R(x-y)
=i\int\frac{d^4p}{(2\pi)^4}
\frac{e^{ip\cdot(x-y)}}
{(p^0+i\epsilon)^2-(\vec p^{\,2}+m^2)}.
$$

板书旁注：$\epsilon$ 只进入 $p^0+i\epsilon$，因此它破坏洛伦兹不变性。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 4，关于推迟传播子洛伦兹不变性的结论及其旁注。
>
> 板书内容：“Retarded propagator is not Lorentz invariant”，并将原因归于 $p^0+i\epsilon$ 处方。
>
> 检查结果：这里需要区分洛伦兹变换的范围，以及有限 $\epsilon$ 的正则化表达式与 $\epsilon\to0^+$ 的分布极限。
>
> 说明：对本课的局域标量场，类空间隔处的场对易子为零；在其余因果支集上，保持时间定向的洛伦兹变换不改变未来与过去。因此推迟传播子在保持时间定向的正常洛伦兹变换下仍是标量不变分布。时间反演会交换推迟与超前边界条件；有限 $\epsilon$ 的写法不显式协变，也不等同于其极限破坏上述不变性。选择初始超曲面本身亦不意味着场方程失去洛伦兹协变性。
>
> 注意：以上为检查提示，未修改原板书内容。

板书随后提出：定义一个尊重洛伦兹不变性的格林函数，即费曼传播子（Feynman propagator）：

$$
\boxed{
D_F(x-y)
=i\int\frac{d^4p}{(2\pi)^4}
\frac{e^{ip\cdot(x-y)}}{-p^2-m^2+i\epsilon}
}.
$$

这里采用：

$$
p^2\equiv-(p^0)^2+\vec p^{\,2}.
$$

## 解释

两种表达式的关键区别在于极点如何避开实能量轴。费曼处方把 $i\epsilon$ 加在由 $p^2$ 和质量构成的分母上；这将给出与推迟处方不同的时间边界条件。

---

# 5. 费曼传播子的能量积分与极点

对应图片：

- 5

## 板书整理

![[Picture/6.2/5.jpg]]

板书注记：选择 $-i\epsilon$ 会得到反费曼传播子（anti-Feynman propagator），不常使用。

回顾真空二点函数：

$$
\langle0|\phi(x)\phi(y)|0\rangle
=\int\frac{d^3p}{(2\pi)^3}
\frac{e^{ip\cdot(x-y)}}{2\omega_p}.
$$

将费曼传播子中的空间动量积分和能量积分分开：

$$
D_F(x)
=i\int\frac{d^3p}{(2\pi)^3}e^{i\vec p\cdot\vec x}
\int_{-\infty}^{\infty}\frac{dp^0}{2\pi}
\frac{e^{-ip^0x^0}}{(p^0)^2-\omega_p^2+i\epsilon}.
$$

板书写出的极点位置为：

$$
p^0=\pm\sqrt{\omega_p^2-i\epsilon}
=\pm(\omega_p-i\epsilon').
$$

复 $p^0$ 平面图示：

- 正能量极点位于实轴下方，标为 $\omega_p-i\epsilon$。
- 负能量极点位于实轴上方，标为 $-(\omega_p-i\epsilon)$。
- 当 $x^0<0$ 时，围道向上半平面闭合，方向为逆时针。
- 当 $x^0>0$ 时，围道向下半平面闭合，方向为顺时针。

## 解释

闭合方向由 $e^{-ip^0x^0}$ 在大半圆上的衰减决定。板书的 $\epsilon'$ 表示重新缩放的正无穷小量：当 $\omega_p>0$ 时，一阶展开给出 $\epsilon'=\epsilon/(2\omega_p)$；极点等式应按 $\epsilon\to0^+$ 的处方理解，图中再次简写为 $\epsilon$。

---

# 6. 留数计算与正、负时间的两项

对应图片：

- 6

## 板书整理

![[Picture/6.2/6.jpg]]

承接上一张板书的能量积分，分别对两个半平面应用留数定理：

$$
\begin{aligned}
D_F(x)
={}&i\int\frac{d^3p}{(2\pi)^3}e^{i\vec p\cdot\vec x}
\frac{1}{2\pi}\Bigg\{
\Theta(-x^0)\,2\pi i\,
\underset{p^0=-\omega_p}{\operatorname{Res}}
\frac{e^{-ip^0x^0}}{(p^0)^2-\omega_p^2}
\\
&\hspace{35mm}
+\Theta(x^0)(-2\pi i)\,
\underset{p^0=\omega_p}{\operatorname{Res}}
\frac{e^{-ip^0x^0}}{(p^0)^2-\omega_p^2}
\Bigg\}.
\end{aligned}
$$

> 此处使用了留数定理；下半平面围道为顺时针，因此出现 $-2\pi i$。板书在选定极点所在半平面后，以 $\epsilon\to0^+$ 的极限值书写留数。

代入留数，得到：

$$
D_F(x)
=\int\frac{d^3p}{(2\pi)^3}e^{i\vec p\cdot\vec x}
\left\{
-\Theta(-x^0)\frac{e^{+i\omega_p x^0}}{-2\omega_p}
+\Theta(x^0)\frac{e^{-i\omega_p x^0}}{2\omega_p}
\right\}.
$$

进一步写为：

$$
\begin{aligned}
D_F(x)
={}&\Theta(-x^0)\int\frac{d^3p}{(2\pi)^3}
\frac{e^{i\omega_p x^0+i\vec p\cdot\vec x}}{2\omega_p}
\\
&+\Theta(x^0)\int\frac{d^3p}{(2\pi)^3}
\frac{e^{-i\omega_p x^0+i\vec p\cdot\vec x}}{2\omega_p}.
\end{aligned}
$$

板书在第一项上标出换元 $\vec p\to-\vec p$，并用 $-p\cdot x$ 标注换元后的相位；第二项的相位标为 $p\cdot x$。

> 此处使用了 $\omega_{-\vec p}=\omega_{\vec p}$ 和全空间积分在 $\vec p\to-\vec p$ 下不变的性质。第一项换元后的指数为 $-ip\cdot x$，第二项为 $ip\cdot x$，其中 $p^0=\omega_p$。

## 解释

两个时间区域分别选中一个极点。负能量极点的留数分母和外部系数各带一个负号，二者抵消，所以最终两个时间分支均为正号。

---

# 7. 将费曼传播子写成真空二点函数

对应图片：

- 7

## 板书整理

![[Picture/6.2/7.jpg]]

恢复两点坐标 $x,y$：

$$
\begin{aligned}
D_F(x-y)
={}&\Theta(y^0-x^0)\int\frac{d^3p}{(2\pi)^3}
\frac{e^{-ip\cdot(x-y)}}{2\omega_p}
\\
&+\Theta(x^0-y^0)\int\frac{d^3p}{(2\pi)^3}
\frac{e^{ip\cdot(x-y)}}{2\omega_p}.
\end{aligned}
$$

板书在第一项指数旁标注：

$$
-ip\cdot(x-y)=ip\cdot(y-x).
$$

利用前面回顾的二点函数，得到：

$$
\begin{aligned}
D_F(x-y)
={}&\Theta(x^0-y^0)\langle0|\phi(x)\phi(y)|0\rangle
\\
&+\Theta(y^0-x^0)\langle0|\phi(y)\phi(x)|0\rangle.
\end{aligned}
$$

接着定义时间排序符号（Time ordering symbol）$T$。板书先给出时间顺序条件：

$$
t_1<t_2<\cdots<t_N,
$$

具体定义接下一张板书。

## 解释

无论 $x^0$ 和 $y^0$ 哪个较大，非零项中较晚时刻的场算符总在左边。这正是接下来时间排序定义所概括的规则。

---

# 8. 多个算符的时间排序定义与例子

对应图片：

- 8

## 板书整理

![[Picture/6.2/8.jpg]]

在 $t_1<t_2<\cdots<t_N$ 的条件下，对 $\{1,2,\ldots,N\}$ 的任意排列 $\sigma$，定义：

$$
T\left\{O(t_{\sigma(1)})O(t_{\sigma(2)})\cdots
O(t_{\sigma(N)})\right\}
=O(t_N)\cdots O(t_1).
$$

板书标注：$O$ 表示某个算符（some operator），$O(t_N)$ 对应最晚时刻（latest $t$），$O(t_1)$ 对应最早时刻（earliest $t$）。

例子：

$$
T\{O(t_2)O(t_1)O(t_3)\}
=O(t_3)O(t_2)O(t_1).
$$

## 解释

在本课标量场的语境中，$T$ 将乘积按时间从左到右由晚到早排列。这个例子沿用 $t_1<t_2<t_3$，而不是按括号中原有的书写顺序相乘。

---

# 9. 两个算符的时间排序与费曼传播子

对应图片：

- 9

## 板书整理

![[Picture/6.2/9.jpg]]

当 $t_1,t_2$ 不预先指定先后时：

$$
T\{O(t_1)O(t_2)\}
=\begin{cases}
O(t_2)O(t_1),&t_1<t_2,\\
O(t_1)O(t_2),&t_1>t_2.
\end{cases}
$$

等价地：

$$
\begin{aligned}
T\{O(t_1)O(t_2)\}
={}&\Theta(t_2-t_1)O(t_2)O(t_1)
\\
&+\Theta(t_1-t_2)O(t_1)O(t_2).
\end{aligned}
$$

因此：

$$
\boxed{
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle
}.
$$

## 解释

费曼传播子就是两个场算符的时间排序真空期望值。这一式子汇总了前面的两种时间分支；板书未另行规定等时点的排序约定。

---

# 10. 截面与衰变率：散射实验的初态和末态

对应图片：

- 10

## 板书整理

![[Picture/6.2/10.jpg]]

新主题：截面与衰变率（Cross sections and decay rates）。

主要关心散射实验（scattering experiments）。板书图示中，若干入射粒子从左边进入中央相互作用区域（interactions），随后若干出射粒子从右边离开：

$$
\underbrace{|i;t_i\rangle}_{\text{initial state}}
\quad\longrightarrow\quad
\text{相互作用区域}
\quad\longrightarrow\quad
\underbrace{|f;t_f\rangle}_{\text{final state}}.
$$

左下角的小图再次画出两条入射线和两条出射线，并标明时间方向向右。

由于相互作用的时间尺度相对于实验持续时间非常短，可以假设：

$$
t_i=-\infty,\qquad t_f=+\infty.
$$

假设在 $t=\pm\infty$ 时相互作用可以忽略，即粒子是自由的。

## 解释

这里用无限早、无限晚的理想化时刻描述准备初态和测量末态。相互作用集中在中间区域，远离该区域时可用自由粒子态描述。

---

# 11. 渐近态、Born 规则与散射矩阵

对应图片：

- 11

## 板书整理

![[Picture/6.2/11.jpg]]

将：

$$
|i;-\infty\rangle,\qquad |f;+\infty\rangle
$$

称为渐近态（asymptotic states），板书注明为 Schrödinger 绘景。

核心问题：给定 $|i;-\infty\rangle$，找到某个末态 $|f;+\infty\rangle$ 的概率是多少？

板书依据 Born 规则写出：

$$
P_{i\to f}
\propto\left|\langle i;-\infty|f;+\infty\rangle\right|^2.
$$

进一步定义：

$$
\boxed{
\langle i;-\infty|f;+\infty\rangle
\equiv\langle i|\hat S|f\rangle
}.
$$

$\hat S$ 称为散射矩阵（S-matrix）。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 11，渐近态的绘景说明及 $\hat S$ 的定义。
>
> 板书内容：将两端态标为 Schrödinger 绘景，并写 $P_{i\to f}\propto|\langle i;-\infty|f;+\infty\rangle|^2$、$\langle i;-\infty|f;+\infty\rangle\equiv\langle i|\hat S|f\rangle$。
>
> 检查结果：需要明确时间演化是否已包含在态的定义中，并留意初、末态指标次序。
>
> 说明：若两者只是分别在 $t_i,t_f$ 指定的 Schrödinger 态，跃迁振幅通常写成 $\langle f;t_f|U(t_f,t_i)|i;t_i\rangle$，不能直接省去连接两时刻的演化算符。若此处实际表示已纳入演化的 in/out 态重叠，则反向内积是通常振幅的复共轭，模平方相同；但在同一自由态基底上，它对应通常 $S$ 矩阵的伴随约定，而不是只交换指标就仍为同一个矩阵元。板书尚未明确这些约定，后续使用时需核对。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

这一部分将实验中的“从某初态得到某末态”转写为量子振幅问题。板书使用比例号，尚未给出态归一化等因素，因此此处保留 $\propto$。

---

# 12. 散射矩阵的幺正性与截面的实验定义

对应图片：

- 12

## 板书整理

![[Picture/6.2/12.jpg]]

承接上一张板书，$|i\rangle,|f\rangle$ 被称为 Heisenberg 绘景中的渐近态。

$\hat S$ 是幺正的：

$$
\boxed{\hat S^{-1}=\hat S^\dagger}.
$$

板书另列出态与时间的关系：

$$
|\psi;t\rangle=e^{iHt}|\psi\rangle.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 12，$|\psi;t\rangle=e^{iHt}|\psi\rangle$。
>
> 板书内容：时间演化指数为 $+iHt$。
>
> 检查结果：若左边是 Schrödinger 绘景态、右边是对应的时间无关 Heisenberg 态，则指数符号疑似有误。
>
> 说明：在 $\hbar=1$、$H$ 不显含时间且参考时刻为 $0$ 时，由 $i\partial_t|\psi_S(t)\rangle=H|\psi_S(t)\rangle$ 得到 $|\psi_S(t)\rangle=e^{-iHt}|\psi_H\rangle$；反向关系才是 $|\psi_H\rangle=e^{+iHt}|\psi_S(t)\rangle$。若板书采用其他映射定义，需要另行说明。
>
> 注意：以上为检查提示，未修改原板书内容。

右上角图示为衰变（Decay）：一个入射粒子进入相互作用区域，产生三个出射粒子。板书将其称为散射的一种特殊情形（particular case of scattering）。

随后定义截面（Cross section）：

$$
d\sigma(\vec\Omega)
\equiv
\frac{
\text{单位时间内散射进入立体角 }d\Omega(\theta,\varphi)
\text{ 的粒子数}
}{\text{入射强度}}.
$$

实验示意图中的标记：

- 入射粒子束（incident beam of particles），粒子数记为 $N_{\mathrm{inc}}$。
- 粒子束射向靶，入射方向的延长线用虚线表示。
- 探测器（detector）位于散射方向，接受立体角 $d\Omega$，接收到的粒子数标为 $dN$。
- $\theta$ 为散射方向与入射轴的夹角，$\varphi$ 表示绕入射轴的方位角。

## 解释

幺正性表达总概率守恒。截面将某方向的散射计数率除以入射粒子流强度，使测量结果能与束流强弱分开；其量纲为面积。

---

# 13. 入射强度与微分截面

对应图片：

- 13

## 板书整理

![[Picture/6.2/13.jpg]]

入射强度等于粒子数密度乘以速率：

$$
\text{Intensity}=(\text{number density})(\text{speed}).
$$

速率是相对于靶的速率（relative to target）。因此：

$$
I=\frac{N_{\mathrm{inc}}}{V}\,v_{\mathrm{inc}},
$$

其中 $V$ 是“实验”的体积（volume of the “experiment”）。

接着板书写出：

$$
d\sigma=\frac{1}{I}\frac{dN}{dt}\,d\Omega.
$$

进一步改写为：

$$
\frac{d\sigma}{d\Omega}
=\frac{1}{I/N_{\mathrm{inc}}}\,
\frac{d(N/N_{\mathrm{inc}})}{dt}.
$$

板书用箭头将 $N$ 标为散射粒子数（number of scattered particles）。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 12—13，探测器计数 $dN$ 与微分截面公式的衔接。
>
> 板书内容：图中将 $d\Omega$ 内的计数记为 $dN$，随后写 $d\sigma=I^{-1}(dN/dt)d\Omega$，并称 $N$ 为散射粒子数。
>
> 检查结果：$N$ 是角区间内的计数，还是每单位立体角的计数，记号不够明确；最后一步还隐含了 $N_{\mathrm{inc}}$ 不随所取时间变量变化的条件。
>
> 说明：若 $dN$ 已是落入 $d\Omega$ 的粒子数，则按上一张的定义应写 $d\sigma=I^{-1}dN/dt$，不应再乘一次 $d\Omega$。若用总计数分布 $N$ 表示，则通常写 $d\sigma/d\Omega=I^{-1}d^2N/(dt\,d\Omega)$。只有将板书中的 $dN/dt$ 理解为每单位立体角的计数率时，其第一式才成立。将 $N$ 改写为 $N/N_{\mathrm{inc}}$ 的导数时，还需把 $N_{\mathrm{inc}}$ 视为固定归一化量。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

$I$ 是单位面积、单位时间通过的入射粒子数。最后一式试图将散射计数率写成“每个入射粒子的散射概率变化率”除以“每个入射粒子的入射强度”；使用时需明确立体角计数约定。

---

# 14. 由大样本计数比定义散射概率

对应图片：

- 14

## 板书整理

![[Picture/6.2/14.jpg]]

当 $N_{\mathrm{inc}}$ 和 $N$ 很大时，预期比值 $N/N_{\mathrm{inc}}$ 定义散射概率：

$$
\boxed{P\equiv\frac{N}{N_{\mathrm{inc}}}}.
$$

## 解释

这里把大量重复入射中的相对频率与概率联系起来。$N$ 应按所研究的散射事件和探测范围计数，才能与前面选定末态或方向的概率对应。

---

# 本节知识结构

上节回顾：波函数、$N$ 粒子态、推迟传播子与格林函数
↓
空间 Fourier 变换，将推迟方程化为各动量模的方程
↓
连续性与导数跳跃条件确定 $B=0$、$A=-i/\omega_k$
↓
得到 $\widetilde D_R$，应用于脉冲源标量场
↓
讨论初值边界条件与洛伦兹不变性，引入费曼 $i\epsilon$ 处方
↓
确定能量极点及围道，用留数得到正、负时间分支
↓
将两项识别为真空二点函数，定义时间排序 $T$
↓
得到 $D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle$
↓
转向散射实验：自由初末态、渐近态、Born 规则与 $\hat S$
↓
散射矩阵的幺正性，衰变示意与截面定义
↓
入射强度、微分截面与计数比 $P=N/N_{\mathrm{inc}}$

---

# 核心公式清单

下表按课堂顺序列出重要公式；带有检查提示的原式仍按板书保留，使用时应同时参照对应正文注释。

| 公式 | 含义 |
| ----- | ---- |
| $D_R(x-y)=\Theta(x^0-y^0)\langle0\vert[\phi(x),\phi(y)]\vert0\rangle$ | 推迟传播子的定义 |
| $(\Box-m^2)D_R(x)=i\delta^4(x)$，$D_R(t,\vec x)=0\ (t<0)$ | 格林函数方程与推迟边界条件 |
| $D_R(t,\vec x)=\int\frac{d^3k}{(2\pi)^3}\widetilde D_R(t,\vec k)e^{i\vec k\cdot\vec x}$ | 空间 Fourier 表示 |
| $\delta(\vec x)=\int\frac{d^3k}{(2\pi)^3}e^{i\vec k\cdot\vec x}$ | 空间 delta 函数的 Fourier 表示 |
| $[-\partial_t^2-\omega_k^2]\widetilde D_R=i\delta(t)$ | 各动量模的方程 |
| $\widetilde D_R=A\sin\omega_k t+B\cos\omega_k t\ (t>0)$ | 正时间区域的通解 |
| $\widetilde D_R(0^+,\vec k)=\widetilde D_R(0^-,\vec k)=0$ | 连续性条件，确定 $B=0$ |
| $\partial_t\widetilde D_R(0^+,\vec k)-\partial_t\widetilde D_R(0^-,\vec k)=-i$ | 导数跳跃条件，确定 $A=-i/\omega_k$ |
| $\widetilde D_R(t,\vec k)=-i\Theta(t)\sin(\omega_k t)/\omega_k$，$\omega_k=\sqrt{\vec k^{\,2}+m^2}$ | 推迟传播子的动量模解 |
| $J(x)=j(\vec x)\delta(t)$ | 脉冲源 |
| $\mathcal L=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2+\phi J$，$(\Box-m^2)\phi=-J$ | 带源标量场的拉格朗日量密度与运动方程 |
| $\phi_{\vec k}(t)=\Theta(t)j_{\vec k}\sin(\omega_k t)/\omega_k$，$j_{\vec k}=\int d^3x\,j(\vec x)e^{-i\vec k\cdot\vec x}$ | 脉冲源的响应及源的 Fourier 变换 |
| $D_R(x-y)=i\int\frac{d^4p}{(2\pi)^4}\frac{e^{ip\cdot(x-y)}}{(p^0+i\epsilon)^2-(\vec p^{\,2}+m^2)}$ | 推迟极点处方 |
| $D_F(x-y)=i\int\frac{d^4p}{(2\pi)^4}\frac{e^{ip\cdot(x-y)}}{-p^2-m^2+i\epsilon}$ | 费曼传播子的四动量表示 |
| $p^2=-(p^0)^2+\vec p^{\,2}$ | 本课采用的度规约定 |
| $\langle0\vert\phi(x)\phi(y)\vert0\rangle=\int\frac{d^3p}{(2\pi)^3}\frac{e^{ip\cdot(x-y)}}{2\omega_p}$ | 真空二点函数，$p^0=\omega_p$ |
| $p^0=\pm\sqrt{\omega_p^2-i\epsilon}=\pm(\omega_p-i\epsilon')$ | 费曼极点；最后一式按无穷小处方理解 |
| $D_F(x-y)=\Theta(x^0-y^0)\langle0\vert\phi(x)\phi(y)\vert0\rangle+\Theta(y^0-x^0)\langle0\vert\phi(y)\phi(x)\vert0\rangle$ | 费曼传播子的两个时间分支 |
| $T\{O(t_{\sigma(1)})\cdots O(t_{\sigma(N)})\}=O(t_N)\cdots O(t_1)$，$t_1<\cdots<t_N$ | 多算符的时间排序 |
| $T\{O(t_1)O(t_2)\}=\Theta(t_2-t_1)O(t_2)O(t_1)+\Theta(t_1-t_2)O(t_1)O(t_2)$ | 两算符时间排序的阶跃函数表达式 |
| $D_F(x-y)=\langle0\vert T\{\phi(x)\phi(y)\}\vert0\rangle$ | 费曼传播子的时间排序表示 |
| $t_i=-\infty$，$t_f=+\infty$ | 散射初、末时刻的理想化 |
| $P_{i\to f}\propto\left\lvert\langle i;-\infty\vert f;+\infty\rangle\right\rvert^2$ | 板书的 Born 规则写法；绘景及演化约定见第 11 节 |
| $\langle i;-\infty\vert f;+\infty\rangle\equiv\langle i\vert\hat S\vert f\rangle$ | 板书的散射矩阵定义；指标次序见第 11 节 |
| $\hat S^{-1}=\hat S^\dagger$ | 散射矩阵的幺正性 |
| $\vert\psi;t\rangle=e^{iHt}\vert\psi\rangle$ | 板书的态关系原式；指数符号检查见第 12 节 |
| $d\sigma(\vec\Omega)=\frac{\text{单位时间散入 }d\Omega\text{ 的粒子数}}{\text{入射强度}}$ | 截面的实验定义 |
| $I=(N_{\mathrm{inc}}/V)v_{\mathrm{inc}}$ | 入射强度：数密度乘以相对靶的速率 |
| $d\sigma=I^{-1}(dN/dt)d\Omega$ | 板书的截面原式；角分布记号检查见第 13 节 |
| $\frac{d\sigma}{d\Omega}=\frac{1}{I/N_{\mathrm{inc}}}\frac{d(N/N_{\mathrm{inc}})}{dt}$ | 用入射粒子数归一化；适用条件见第 13 节 |
| $P=N/N_{\mathrm{inc}}$ | 大样本计数比对应的散射概率 |
