---
title: "量子场论导论 Lecture 7.1"
date: 2026-10-20
tags:
  - 量子场论导论
  - lecture
  - 散射截面
  - 散射振幅
  - 相空间
  - 二体散射
source: "课堂板书"
---

# Lecture 7.1: 散射概率、洛伦兹不变相空间与二体散射截面

## 本节内容概览

本节从上次课的渐近态、散射矩阵与散射截面出发，将微分截面和散射概率联系起来，并引入避免全同末态重复计数的对称因子。随后用离散态的概率归一化说明末态求和，再通过相空间态密度得到连续末态的积分测度。结合多粒子态归一化、散射振幅以及能量动量守恒，板书推导出含洛伦兹不变相空间测度的跃迁概率和总截面。最后将公式用于质心系中的 $2\to2$ 散射，写出对两个出射动量积分的截面表达式。

<!-- date 为整理日期；原板书未标明授课日期。正文严格依照 Picture/7.1/1.jpg 至 16.jpg 的顺序展开。原式与检查注释分开保留；图片使用含目录的 Obsidian 引用，以区分其他课次的同名图片。 -->

---

# 1. 上节回顾：渐近态、散射矩阵与截面

对应图片：

- 1

## 板书整理

![[Picture/7.1/1.jpg]]

上节内容（Last time）：

- 费曼传播子（Feynman propagator）。
- 渐近态与散射矩阵（Asymptotic states and S-matrix）：

$$
\langle f;+\infty|i;-\infty\rangle
\equiv\langle f|\hat S|i\rangle.
$$

- 散射（Scattering）：入射粒子数为 $N_{\mathrm{inc}}$，入射速度为 $v_{\mathrm{inc}}$；粒子碰到靶（target）后，沿与入射方向夹角为 $\theta$ 的方向散射，探测器对应立体角元 $d\Omega$，散射计数标为 $dN$。

板书定义：

$$
d\sigma\equiv\frac{1}{I}\frac{dN}{dt}\,d\Omega.
$$

因此：

$$
\frac{d\sigma}{d\Omega}
=\frac{1}{I/N_{\mathrm{inc}}}
\frac{dN/N_{\mathrm{inc}}}{dt}.
$$

入射强度：

$$
I\equiv\frac{N_{\mathrm{inc}}}{V}v_{\mathrm{inc}},
$$

其中 $V$ 为实验体积（volume of experiment）。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 1 的散射计数与截面定义。
>
> 板书内容：图中将进入 $d\Omega$ 的计数标为 $dN$，公式又写成 $d\sigma=I^{-1}(dN/dt)d\Omega$。
>
> 检查结果：$dN$ 的记号可能混用了角区间内的计数和单位立体角的计数密度。
>
> 说明：若 $dN$ 已是角元内的计数，则应有 $d\sigma=I^{-1}dN/dt$；若保留原式中的额外 $d\Omega$，则 $dN/dt$ 须理解为单位立体角的计数率。此处保留原板书，后续仍沿用其记号。

## 解释

散射矩阵元给出渐近初态到渐近末态的跃迁振幅。截面把散射计数率除以入射强度，用于描述给定入射条件下的散射强弱。

---

# 2. 微分概率、微分截面与对称因子

对应图片：

- 2

## 板书整理

![[Picture/7.1/2.jpg]]

将微分概率（differential probability）识别为：

$$
dP\equiv\frac{dN}{N_{\mathrm{inc}}}.
$$

由上一张板书的入射强度得到微分截面（differential cross section）：

$$
\boxed{
\frac{d\sigma}{d\Omega}
=\frac{V}{v_{\mathrm{inc}}}\frac{dP}{dt}
}.
$$

总截面（total cross section）：

$$
\sigma\equiv\frac{1}{S}\int d\Omega\,
\frac{d\sigma}{d\Omega}.
$$

$S$ 称为“对称因子”（symmetry factor），用于避免对含有全同粒子的末态事件重复计数。

## 解释

因子 $V/v_{\mathrm{inc}}$ 来自入射强度与入射粒子数之比。这里的 $S$ 是计数因子，与散射算符 $\hat S$ 不同。上述 $dP$ 的角密度含义承接上一节的记号问题，暂按原式保留。

---

# 3. 方位角积分与连续末态

对应图片：

- 3

## 板书整理

![[Picture/7.1/3.jpg]]

通常 $d\sigma/d\Omega$ 不依赖方位角 $\varphi$，板书写出：

$$
d\Omega=d\varphi\,d\cos\theta.
$$

于是：

$$
\boxed{
\sigma=\frac{2\pi}{S}\int_{-1}^{1}d\cos\theta\,
\frac{d\sigma}{d\Omega}
}.
$$

接着讨论微分概率。考虑末态 $|f;+\infty\rangle$，其中包含 $N$ 个粒子，第 $n$ 个粒子的三动量位于：

$$
\vec p_n\ \text{与}\ \vec p_n+d\vec p_n\ \text{之间},
\qquad n=1,\ldots,N.
$$

> 此处使用了方位角对称性：对 $\varphi$ 积分产生 $2\pi$。

## 解释

$d\Omega$ 的写法将 $\cos\theta$ 作为积分变量，积分区间取 $[-1,1]$。方位角无关是这一简化的条件。接下来的末态包含连续动量区间，因此需要计算相应区间内的态数。

---

# 4. 跃迁概率与相空间测度

对应图片：

- 4

## 板书整理

![[Picture/7.1/4.jpg]]

过程 $i\to f$ 的概率为：

$$
\boxed{
dP_{i\to f}
=\frac{|\langle f|\hat S|i\rangle|^2}
{\langle f|f\rangle\langle i|i\rangle}\,d\Pi
}.
$$

其中：

$$
d\Pi\equiv\prod_{n=1}^{N}
\left[\frac{V}{(2\pi)^3}\,d^3p_n\right],
$$

称为“相空间测度”（phase space measure）。

板书提出：先在 $|f\rangle$ 构成离散态集合的情形下检验这一概率表达式。

## 解释

分母消除初、末态范数带来的归一化因子，$d\Pi$ 则计数所选动量区间中的末态。此处先给出测度，后面的板书再说明它的来源。

---

# 5. 离散末态的概率归一化检查

对应图片：

- 5

## 板书整理

![[Picture/7.1/5.jpg]]

定义归一化的态：

$$
|\hat i\rangle\equiv\frac{|i\rangle}{\sqrt{\langle i|i\rangle}},
\qquad
|\hat f\rangle\equiv\frac{|f\rangle}{\sqrt{\langle f|f\rangle}}.
$$

对离散末态求和：

$$
\begin{aligned}
\sum_f\frac{|\langle f|\hat S|i\rangle|^2}
{\langle f|f\rangle\langle i|i\rangle}
&=\sum_f|\langle\hat f|\hat S|\hat i\rangle|^2\\
&=\sum_f\langle\hat i|\hat S^\dagger|\hat f\rangle
\langle\hat f|\hat S|\hat i\rangle\\
&=\langle\hat i|\hat S^\dagger
\left(\sum_f|\hat f\rangle\langle\hat f|\right)
\hat S|\hat i\rangle\\
&=1.
\end{aligned}
$$

板书标注了完备性：

$$
\sum_f|\hat f\rangle\langle\hat f|=\mathbf 1,
$$

以及散射矩阵的幺正性：

$$
\hat S^\dagger=\hat S^{-1}.
$$

> 此处使用了归一化末态基的正交完备性与 $\hat S$ 的幺正性。

## 解释

对所有可能的末态求和后，总概率应为 $1$。该检验说明，带范数分母的表达式与通常的归一化态概率公式一致。

---

# 6. 从态求和到相空间体积与态密度

对应图片：

- 6

## 板书整理

![[Picture/7.1/6.jpg]]

板书说明，这里的 $|f\rangle$ 由连续取值的变量集合描述：

$$
\left\{(\vec x_n,\vec p_n)\right\}_{n=1}^{N}.
$$

对某个量 $[\cdots]$ 求和，可写成：

$$
\begin{aligned}
\sum_{\text{states}}[\cdots]
&=\sum_{\{(\vec x_n,\vec p_n)\}}[\cdots]\\
&=\left[\prod_{n=1}^{N}\int d^3x_n\,d^3p_n\right]
[\cdots]\times
\left(\frac{\text{态数}}{\text{相空间体积}}\right).
\end{aligned}
$$

其中 $d^3x_n\,d^3p_n$ 是相空间体积元，态数除以相空间体积称为态密度（density of states）。

板书画出以 $x$ 为横轴、$p_x$ 为纵轴的相空间网格，单个格子的面积标为：

$$
\Delta x\,\Delta p_x=2\pi\hbar.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 6 的末态标签及相空间求和。
>
> 板书内容：$|f\rangle$ 由 $\{(\vec x_n,\vec p_n)\}$ 描述，并用相空间格子计算态数。
>
> 检查结果：这里应理解为相空间态计数的描述，不能视为精确量子态同时具有确定位置和动量。$\Delta x\Delta p_x=2\pi\hbar$ 是计数单元的面积，并非不确定性关系取等号。
>
> 说明：对于 $N$ 粒子，若“态密度”指整个 $6N$ 维相空间中的密度，应包含每个粒子的因子；下一张板书将其明确写入连乘积。以上为检查提示，未修改原板书。

## 解释

这一段说明如何把“对所有末态求和”转换为相空间积分。相空间体积还需乘以每单位体积中的态数，才能得到正确的计数。

---

# 7. 相空间测度的推导

对应图片：

- 7

## 板书整理

![[Picture/7.1/7.jpg]]

三维空间中，单粒子的相空间态密度为：

$$
\frac{\text{态数}}{\text{相空间体积}}
=\left(\frac{\text{相空间体积}}{\text{每个态}}\right)^{-1}
=\left((2\pi\hbar)^3\right)^{-1}
=\frac{1}{(2\pi)^3}.
$$

最后一步取 $\hbar=1$。

因此：

$$
\sum_{\text{states}}[\cdots]
=\left[\prod_{n=1}^{N}\int
\frac{d^3x_n\,d^3p_n}{(2\pi)^3}\right][\cdots].
$$

假定被积量 $[\cdots]$ 与 $\vec x_n$ 无关（suppose independent of $\vec x_n$），则：

$$
\begin{aligned}
\sum_{\text{states}}[\cdots]
&=\left[\prod_{n=1}^{N}\frac{V}{(2\pi)^3}
\int d^3p_n\right][\cdots]\\
&=\int d\Pi\,[\cdots].
\end{aligned}
$$

> 此处使用了空间均匀性假设，对每个粒子的位置积分给出 $\int_V d^3x_n=V$。

## 解释

每个粒子贡献一个 $V\,d^3p_n/(2\pi)^3$，从而得到图片 4 中预先写出的 $d\Pi$。这些体积因子将在后续与态的归一化因子相消。

---

# 8. 单粒子态归一化与末态的平凡部分

对应图片：

- 8

## 板书整理

![[Picture/7.1/8.jpg]]

回顾单粒子态的归一化：

$$
\langle\vec p|\vec q\rangle
=(2\pi)^3\,2\omega_p\,\delta^3(\vec p-\vec q).
$$

利用：

$$
\delta^3(\vec 0)=\frac{V}{(2\pi)^3},
$$

得到：

$$
\langle\vec p|\vec p\rangle=2\omega_pV.
$$

将末态写为：

$$
|f\rangle=|\vec p_1\rangle|\vec p_2\rangle\cdots
|\vec p_N\rangle\times(\text{trivial}).
$$

前面的乘积表示 $N$ 粒子态。这里的“trivial”表示未参与散射的粒子；板书注明，它们在 $\langle f|i\rangle$ 中给出 $1$，但需计入相应归一化（up to normalization）。

> 此处使用了有限体积归一化：$(2\pi)^3\delta^3(\vec 0)=V$。

## 解释

$\delta^3(\vec0)$ 的等式是有限体积正则化下的记号，并非把 Dirac 分布当作普通函数求值。“平凡部分”用于分离未发生散射的粒子所带来的因子。

---

# 9. 多粒子态范数与 T 矩阵

对应图片：

- 9

## 板书整理

![[Picture/7.1/9.jpg]]

由上一张板书的乘积态形式：

$$
\begin{aligned}
\langle f|f\rangle
&=(2\omega_{p_1})\cdots(2\omega_{p_N})\,V^N
\cdot(\text{trivial})\\
&=\left[\prod_{n=1}^{N}2\omega_nV\right]
\cdot(\text{trivial}).
\end{aligned}
$$

初态范数为：

$$
\langle i|i\rangle
=\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_mV.
$$

定义：

$$
\boxed{\hat S\equiv\mathbf 1+i\hat T}.
$$

板书将 $\hat T$ 标为“transfer matrix”。

## 解释

板书把 $\omega_{p_n}$ 简写为 $\omega_n$。此处 $N_{\mathrm{inc}}$ 表示一次散射过程初态中的粒子数，而图片 1 的同一符号用于入射束的粒子计数，阅读时需区分。$\mathbf 1$ 对应无散射的部分，$\hat T$ 承载其余跃迁；按这里的定义，它通常称为跃迁矩阵（transition matrix）。

---

# 10. 去掉平凡贡献与总四动量

对应图片：

- 10

## 板书整理

![[Picture/7.1/10.jpg]]

约定忽略 $|f\rangle$ 中的平凡部分，使得：

$$
\langle f|i\rangle=0.
$$

于是：

$$
\langle f|\hat S|i\rangle
=\underbrace{\langle f|i\rangle}_{0}
+i\langle f|\hat T|i\rangle.
$$

定义总初态四动量：

$$
p_i\equiv\sum_{m=1}^{N_{\mathrm{inc}}}p_m,
$$

以及总末态四动量：

$$
p_f\equiv\sum_{n=1}^{N}p_n.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 10 的“忽略平凡部分”与 $\langle f|i\rangle=0$。
>
> 板书内容：忽略末态的平凡部分后，令 $\langle f|i\rangle=0$。
>
> 检查结果：除去未参与散射的旁观粒子，本身不足以保证初末态正交；还需限定在与初态不同的末态通道，或明确提取非平凡散射贡献。
>
> 说明：当末态与初态重合时，恒等算符项不能直接设为零。此处按板书所选的非平凡跃迁继续记录，未修改原式。

## 解释

这一步把后续计算集中到 $\hat T$ 的矩阵元。$p_i$ 和 $p_f$ 是四动量总和，包含总能量与总三动量。

---

# 11. 能量动量守恒与散射振幅

对应图片：

- 11

## 板书整理

![[Picture/7.1/11.jpg]]

由于散射守恒能量和动量：

$$
\langle f|i\hat T|i\rangle
\propto\delta^4(p_f-p_i).
$$

提取守恒的 $\delta$ 函数后，写为：

$$
\boxed{
\langle f|i\hat T|i\rangle
=(2\pi)^4\delta^4(p_f-p_i)\,i\mathcal M
}.
$$

$\mathcal M$ 称为“散射振幅”（scattering amplitude）。

## 解释

$\delta^4(p_f-p_i)$ 约束初末态总四动量相等。提取这一因子之后，散射过程的其余信息由 $\mathcal M$ 表示。

---

# 12. 矩阵元模平方与跃迁概率

对应图片：

- 12

## 板书整理

![[Picture/7.1/12.jpg]]

对上一式取模平方：

$$
|\langle f|i\hat T|i\rangle|^2
=(2\pi)^4\delta^4(p_f-p_i)
(2\pi)^4\delta^4(p_f-p_i)|\mathcal M|^2.
$$

板书在两个 $\delta$ 函数因子的下方，用蓝字作如下化简（保留原写法）：

$$
\begin{aligned}
&(2\pi)^4\delta^4(p_f-p_i)
(2\pi)^4\delta^4(p_f-p_i)\\
&\qquad=\delta^4(0)(2\pi)^4\delta^4(p_f-p_i)\\
&\qquad=V(\Delta T)\delta^4(p_f-p_i).
\end{aligned}
$$

旁注使用的关系为：

$$
f(x)\delta(x)=f(0)\delta(x).
$$

$\Delta T$ 标为实验总时长（total time of the experiment）。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 12 的蓝字 $\delta$ 函数化简。
>
> 板书内容：上述乘积化为 $\delta^4(0)(2\pi)^4\delta^4(p_f-p_i)$，再化为 $V\Delta T\delta^4(p_f-p_i)$。
>
> 检查结果：蓝字两行相对原乘积少了一个 $(2\pi)^4$。
>
> 说明：使用与单粒子归一化一致的有限时空体积记号 $(2\pi)^4\delta^4(0)=V\Delta T$，相应结果通常应为：
>
> $$
> \big[(2\pi)^4\delta^4(p_f-p_i)\big]^2
> =V\Delta T\,(2\pi)^4\delta^4(p_f-p_i).
> $$
>
> 此外，$f\delta=f(0)\delta$ 对光滑 $f$ 成立，不能直接把另一份 $\delta$ 当作普通函数代入；这里须理解为有限实验时间和体积下的正则化及长时间极限。板书下一条概率公式保留了所需的 $(2\pi)^4$，与通常的归一化一致。以上为检查提示，未修改原蓝字推导。

回到跃迁概率，板书写出：

$$
dP_{i\to f}
=\frac{
V\Delta T\,(2\pi)^4\delta^4(p_f-p_i)|\mathcal M|^2
}{
\displaystyle
\left[\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}V\right]
\left[\prod_{n=1}^{N}2\omega_{p_n}V\right]
}
\prod_{n=1}^{N}\left[\frac{V}{(2\pi)^3}d^3p_n\right].
$$

板书在 $dP_{i\to f}$ 旁标注：已对空间积分（integrated in space）。

## 解释

矩阵元模平方中的时空体积因子，与初末态范数及末态计数测度共同组成概率。下一步将整理这些因子，尤其是相消的末态体积因子。

---

# 13. 洛伦兹不变相空间测度

对应图片：

- 13

## 板书整理

![[Picture/7.1/13.jpg]]

继续化简上一张板书的概率：

$$
dP_{i\to f}
=\frac{\Delta T}{V^{N_{\mathrm{inc}}-1}}
\frac{|\mathcal M|^2}
{\displaystyle\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}
\,d\Pi_{\mathrm{LIPS}}.
$$

其中定义：

$$
\boxed{
d\Pi_{\mathrm{LIPS}}
\equiv
\left[\prod_{n=1}^{N}
\frac{d^3p_n}{(2\pi)^3}\frac{1}{2\omega_{p_n}}\right]
(2\pi)^4\delta^4(p_f-p_i)
}.
$$

它称为“洛伦兹不变相空间测度”（Lorentz invariant phase space measure）。

> 此处将每个末态的 $V$ 与范数中的 $V$ 相消，并把末态能量因子和四动量守恒的 $\delta$ 函数归入 $d\Pi_{\mathrm{LIPS}}$。

## 解释

$d\Pi$ 只是前面用于计数的动量空间测度；$d\Pi_{\mathrm{LIPS}}$ 还包括 $1/(2\omega_{p_n})$ 及整体守恒约束。二者在本课中有不同定义，不能混用。

---

# 14. 从跃迁概率回到总截面

对应图片：

- 14

## 板书整理

![[Picture/7.1/14.jpg]]

回到总截面：

$$
\begin{aligned}
\sigma
&=\frac{1}{S}\int d\Omega\,\frac{d\sigma}{d\Omega}\\
&=\frac{1}{S}\int\frac{V}{v_{\mathrm{inc}}}
\frac{dP}{dt}\,d\Omega\\
&=\frac{1}{S}\int\frac{V}{v_{\mathrm{inc}}}
\frac{dP_{i\to f}}{dt}.
\end{aligned}
$$

板书注明积分是对末态积分（integral over final state），并写出：

$$
dP_{i\to f}=dP\,d\Omega.
$$

关于 $dP$，红字标注“特定 $d\Omega$ 内的 $dP$”，蓝字又说明原定义是“单位立体角的概率”（probability per unit solid angle）。

板书随后写道：

> $dP_{i\to f}$ 与时间无关（is independent of time）。

因此可以写成：

$$
\frac{dP_{i\to f}}{dt}
=\frac{dP_{i\to f}}{\Delta T}.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 14 的角概率记号。
>
> 板书内容：$dP_{i\to f}=dP\,d\Omega$，同时将 $dP$ 说明为单位立体角的概率。
>
> 检查结果：这一等式要求 $dP$ 是角概率密度，与图片 1—2 中将 $dN$、$dP$ 画在有限角元内的表述不完全一致。
>
> 说明：若定义角概率密度 $\rho_\Omega$，则角元内概率为 $\rho_\Omega d\Omega$，两种含义即可区分。对于一般多粒子末态，还需对其余末态变量积分后才能用单个 $d\Omega$ 描述角分布。以上只是记号检查，未替换原公式。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 14 的时间无关说明。
>
> 板书内容：“$dP_{i\to f}$ 与时间无关”，并写出 $dP_{i\to f}/dt=dP_{i\to f}/\Delta T$。
>
> 检查结果：若概率本身与时间无关，其时间导数应为零，不能据此得到原式。
>
> 说明：图片 13 的概率正比于实验时长 $\Delta T$；这里应理解为稳恒散射条件下的跃迁率不随时间变化，因此可以用总概率除以总时长得到速率。以上为检查提示，未修改原板书。

## 解释

这一步先把末态概率换成单位时间的跃迁率，再除以入射通量并积分，得到总截面。按稳恒跃迁率理解后，上一节概率中的 $\Delta T$ 被消去。

---

# 15. 总截面公式与质心系中的二体散射

对应图片：

- 15

## 板书整理

![[Picture/7.1/15.jpg]]

代入前面的概率表达式，得到：

$$
\boxed{
\sigma
=\frac{1}{S}
\frac{1}{V^{N_{\mathrm{inc}}-2}v_{\mathrm{inc}}}
\frac{1}{\displaystyle\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}
\int|\mathcal M|^2\,d\Pi_{\mathrm{LIPS}}
}.
$$

随后讨论“质心系”（center of mass frame）中的 $2\to2$ 散射。板书特意注明：更准确地说，是总动量为零的参考系（actually momentum）。

示意图中，$p_1$、$p_2$ 是相向的入射动量，$p'_1$、$p'_2$ 是背对背的出射动量；散射角 $\theta$ 位于入射粒子 $1$ 的前进方向与出射粒子 $1$ 的方向之间。

这一参考系满足：

$$
\vec p_2=-\vec p_1,
\qquad
\vec p'_2=-\vec p'_1.
$$

质心能量定义为：

$$
E_{\mathrm{CM}}\equiv\omega_1+\omega_2,
\qquad
\omega_m\equiv\sqrt{|\vec p_m|^2+m_m^2}.
$$

入射相对速度取为：

$$
v_{\mathrm{inc}}=|\vec v_1-\vec v_2|,
\qquad N=2=N_{\mathrm{inc}}.
$$

> 此处使用了 $\sigma$ 中的 $V$ 与跃迁率中的 $V^{-(N_{\mathrm{inc}}-1)}$ 合并，产生 $V^{-(N_{\mathrm{inc}}-2)}$。

## 解释

对于这里的两个入射粒子，$N_{\mathrm{inc}}=2$，截面中的归一化体积完全消去。$v_{\mathrm{inc}}$ 是本参考系中用于入射通量的速度差大小；初态与末态总三动量均为零，但单个粒子的三动量不为零。

---

# 16. 二体散射截面的末态动量积分

对应图片：

- 16

## 板书整理

![[Picture/7.1/16.jpg]]

将 $N=N_{\mathrm{inc}}=2$ 及上一张板书的相对速度代入，展开两体末态的相空间测度：

$$
\boxed{
\begin{aligned}
\sigma
={}&\frac{1}{S}
\frac{1}{|\vec v_1-\vec v_2|\,4\omega_1\omega_2}
\int\frac{d^3p'_1\,d^3p'_2}{(2\pi)^6}\\
&\quad\times\frac{|\mathcal M|^2}{4\omega'_1\omega'_2}
(2\pi)^4\delta^4(p'_1+p'_2-p_1-p_2).
\end{aligned}
}
$$

## 解释

积分外的 $4\omega_1\omega_2$ 来自两个入射粒子的归一化，积分内的 $4\omega'_1\omega'_2$ 来自两个出射粒子的相空间测度。四维 $\delta$ 函数同时实施能量守恒与三动量守恒。本组板书止于这一积分形式，尚未进一步完成末态动量积分。

---

# 本节知识结构

渐近态、散射矩阵与入射强度（图片 1）
↓
微分概率、微分截面与对称因子（图片 2）
↓
方位角积分与连续动量末态（图片 3）
↓
含态范数及相空间测度的跃迁概率（图片 4）
↓
离散末态的完备性与总概率归一化（图片 5）
↓
相空间体积、态密度及连续末态测度（图片 6—7）
↓
单粒子与多粒子态归一化、$\hat S=\mathbf1+i\hat T$（图片 8—9）
↓
非平凡跃迁、总四动量与散射振幅 $\mathcal M$（图片 10—11）
↓
矩阵元模平方、实验时空体积及跃迁概率（图片 12）
↓
洛伦兹不变相空间测度 $d\Pi_{\mathrm{LIPS}}$（图片 13）
↓
跃迁率与总截面（图片 14—15）
↓
质心系的 $2\to2$ 散射及两体末态动量积分（图片 15—16）

# 核心公式清单

下表依照课堂出现顺序列出核心公式。涉及角概率记号及时间依赖的原式，应结合正文检查注释阅读。

| 公式 | 含义 |
| ----- | ---- |
| $\langle f;+\infty\vert i;-\infty\rangle=\langle f\vert\hat S\vert i\rangle$ | 渐近态跃迁与散射矩阵 |
| $I=(N_{\mathrm{inc}}/V)v_{\mathrm{inc}}$ | 入射强度 |
| $dP=dN/N_{\mathrm{inc}}$ | 板书的微分概率记号 |
| $\dfrac{d\sigma}{d\Omega}=\dfrac{V}{v_{\mathrm{inc}}}\dfrac{dP}{dt}$ | 微分截面与角概率率的关系，见记号检查 |
| $\sigma=\dfrac1S\int d\Omega\,\dfrac{d\sigma}{d\Omega}$ | 总截面与全同末态对称因子 |
| $\sigma=\dfrac{2\pi}{S}\int_{-1}^{1}d\cos\theta\,\dfrac{d\sigma}{d\Omega}$ | 方位角无关时的总截面 |
| $dP_{i\to f}=\dfrac{\lvert\langle f\vert\hat S\vert i\rangle\rvert^2}{\langle f\vert f\rangle\langle i\vert i\rangle}\,d\Pi$ | 连续末态跃迁概率 |
| $d\Pi=\prod_{n=1}^{N}\left[\dfrac{V}{(2\pi)^3}d^3p_n\right]$ | 末态计数测度 |
| $\sum_f\lvert\hat f\rangle\langle\hat f\rvert=\mathbf1,\quad\hat S^\dagger=\hat S^{-1}$ | 概率归一化所用的完备性与幺正性 |
| $\Delta x\Delta p_x=2\pi\hbar,\quad\rho_{\mathrm{states}}=(2\pi\hbar)^{-3}$ | 单粒子相空间计数单元与三维态密度 |
| $\langle\vec p\vert\vec q\rangle=(2\pi)^3 2\omega_p\delta^3(\vec p-\vec q)$ | 单粒子态归一化 |
| $\delta^3(\vec0)=V/(2\pi)^3,\quad\langle\vec p\vert\vec p\rangle=2\omega_pV$ | 有限体积下的范数 |
| $\langle f\vert f\rangle=\left(\prod_{n=1}^{N}2\omega_nV\right)(\mathrm{trivial}),\quad\langle i\vert i\rangle=\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_mV$ | 多粒子态范数 |
| $\hat S=\mathbf1+i\hat T$ | 分离无散射部分与跃迁部分 |
| $p_i=\sum_{m=1}^{N_{\mathrm{inc}}}p_m,\quad p_f=\sum_{n=1}^{N}p_n$ | 初末态总四动量 |
| $\langle f\vert i\hat T\vert i\rangle=(2\pi)^4\delta^4(p_f-p_i)i\mathcal M$ | 散射振幅定义 |
| $\lvert\langle f\vert i\hat T\vert i\rangle\rvert^2=\big[(2\pi)^4\delta^4(p_f-p_i)\big]^2\lvert\mathcal M\rvert^2$ | 模平方的原始形式；正则化及蓝字缺因子问题见第 12 节 |
| $dP_{i\to f}=\dfrac{\Delta T}{V^{N_{\mathrm{inc}}-1}}\dfrac{\lvert\mathcal M\rvert^2}{\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}d\Pi_{\mathrm{LIPS}}$ | 整理后的跃迁概率 |
| $d\Pi_{\mathrm{LIPS}}=\left[\prod_{n=1}^{N}\dfrac{d^3p_n}{(2\pi)^3 2\omega_{p_n}}\right](2\pi)^4\delta^4(p_f-p_i)$ | 洛伦兹不变相空间测度 |
| $\dfrac{dP_{i\to f}}{dt}=\dfrac{dP_{i\to f}}{\Delta T}$ | 稳恒跃迁率的写法，见第 14 节检查 |
| $\sigma=\dfrac{1}{S V^{N_{\mathrm{inc}}-2}v_{\mathrm{inc}}\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}\int\lvert\mathcal M\rvert^2d\Pi_{\mathrm{LIPS}}$ | 板书给出的总截面表达式 |
| $\vec p_2=-\vec p_1,\quad\vec p'_2=-\vec p'_1$ | 质心系中初末态的背对背动量 |
| $E_{\mathrm{CM}}=\omega_1+\omega_2,\quad\omega_m=\sqrt{\lvert\vec p_m\rvert^2+m_m^2}$ | 质心能量与单粒子能量 |
| $v_{\mathrm{inc}}=\lvert\vec v_1-\vec v_2\rvert,\quad N=N_{\mathrm{inc}}=2$ | 本课二体散射的入射通量参数 |
| $\sigma=\dfrac{1}{S\lvert\vec v_1-\vec v_2\rvert\,4\omega_1\omega_2}\int\dfrac{d^3p'_1d^3p'_2}{(2\pi)^6}\dfrac{\lvert\mathcal M\rvert^2}{4\omega'_1\omega'_2}(2\pi)^4\delta^4(p'_1+p'_2-p_1-p_2)$ | 两体末态动量积分形式的散射截面 |
