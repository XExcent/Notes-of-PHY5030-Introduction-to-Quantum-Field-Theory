---
title: "量子场论导论 Lecture 6.1"
date: 2026-10-14
tags:
  - 量子场论导论
  - lecture
  - 多粒子态
  - 态归一化
  - 场对易子
  - 推迟传播子
  - Klein-Gordon方程
source: "课堂板书"
---

# Lecture 6.1: 粒子态的归一化、场对易子与推迟传播子

## 本节内容概览

本节先回顾自由实标量场的 Hamiltonian 与多粒子态，讨论粒子的能量、动量及玻色交换对称性。随后定义单粒子态和多粒子态的归一化，并由场算符的矩阵元得到自由粒子的平面波。接着计算不同时空点的场对易子，通过复能量平面上的围道积分引入推迟传播子。最后分别从动量空间积分和位置空间的等时对易关系出发，验证推迟传播子满足 Klein–Gordon 格林函数方程。

<!-- date 为整理日期；原板书未标明授课日期。正文严格按 Picture/6.1/1.jpg 至 14.jpg 排列。产生算符的板书上标 + 统一排为 \dagger。 -->

---

# 1. 作业提醒与上节课回顾

对应图片：

- 1

## 板书整理

![[Picture/6.1/1.jpg]]

作业提醒：HW。

上节课内容（Last time）：

- 场量子化（Field quantization）。
- 产生、湮灭算符（Creation / annihilation operators）。
- 在壳且经过重整化的 Hamiltonian（on-shell and renormalized）：

$$
H=\int\frac{d^3p}{(2\pi)^3}\,\omega_p\,
a_{\vec p}^{\dagger}a_{\vec p},
\qquad
\omega_p\equiv\sqrt{\vec p^{\,2}+m^2}.
$$

$N$ 粒子态

$$
a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle
$$

是 $H$ 的本征态，本征值为

$$
\sum_{n=1}^{N}\omega_{p_n}=E.
$$

这是 $N$ 个无相互作用粒子的总能量。

## 解释

这里的 Hamiltonian 已去掉真空能常数。每个产生算符增加一个具有确定动量的粒子，因此多粒子态的能量是各粒子能量之和。

---

# 2. 单粒子能量与自由场的粒子解释

对应图片：

- 2

## 板书整理

![[Picture/6.1/2.jpg]]

特别地，当 $N=1$ 时，板书写为

$$
H a_{\vec p}^{\dagger}|0\rangle=\omega_p|0\rangle
\quad\longrightarrow\quad \text{1-particle state}.
$$

这个单粒子态具有能量

$$
\omega_p=\sqrt{\vec p^{\,2}+m^2}.
$$

**Remark 1：** 这是动量为 $\vec p$、质量为 $m$ 的相对论性粒子。

**Remark 2：** 没有势能（No potential energy），板书表述为

$$
E=\text{Sum of kinetic energies}.
$$

即：场 $\phi$ 没有相互作用 $\Longleftrightarrow$ 粒子之间没有相互作用。

**Remark 3：** 没有负能量问题：

$$
\omega_p>0\quad\longrightarrow\quad E>0.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 2 顶部的单粒子本征方程。
>
> 板书内容：$H a_{\vec p}^{\dagger}|0\rangle=\omega_p|0\rangle$。
>
> 检查结果：右端疑似漏写产生算符。
>
> 说明：根据图片 1 的多粒子本征态结论，右端通常应为 $\omega_p a_{\vec p}^{\dagger}|0\rangle$；$H$ 作用后应仍为同一个单粒子态乘以能量本征值。
>
> 注意：以上为检查提示，未修改原板书内容。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 2 的 Remark 2、Remark 3。
>
> 板书内容：$E$ 是“kinetic energies”之和，且 $\omega_p>0\Rightarrow E>0$。
>
> 检查结果：能量的术语和严格不等号需要限定。
>
> 说明：$\omega_p=\sqrt{\vec p^{\,2}+m^2}$ 包含静止能量；若“动能”指扣除静止能量后的能量，则每个粒子的动能是 $\omega_p-m$。板书想强调的是没有粒子间相互作用能。$E>0$ 适用于具有正能量粒子激发的态；去掉真空能后真空的能量为零，整个能谱应表述为非负。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

本页把场量子化得到的激发解释为满足相对论性能量关系的粒子。“没有相互作用”意味着总能量直接相加；正频率 $\omega_p$ 则给出粒子激发的正能量。

---

# 3. 动量算符与玻色交换对称性

对应图片：

- 3

## 板书整理

![[Picture/6.1/3.jpg]]

动量算符：

$$
\vec P=-\int d^3x\,\pi\,\vec\nabla\phi
=\int\frac{d^3p}{(2\pi)^3}\,\vec p\,
a_{\vec p}^{\dagger}a_{\vec p}.
\qquad\text{(HW)}
$$

因此

$$
\vec P\,a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle
=\left(\sum_{n=1}^{N}\vec p_n\right)
a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle.
$$

即 $N$ 粒子态也是动量算符的本征态，其本征值等于 $N$ 个粒子的总动量。

> 此处使用了产生、湮灭算符的对易关系及真空被湮灭算符消去的性质；动量算符的展开计算在板书中标为作业，未展开证明。

**Remark 4：** Klein–Gordon 粒子是自旋为零的玻色子。

$$
a_{\vec p}^{\dagger}a_{\vec q}^{\dagger}|0\rangle
=a_{\vec q}^{\dagger}a_{\vec p}^{\dagger}|0\rangle.
$$

交换两个粒子后，二粒子态不变。

## 解释

动量算符的结构与 Hamiltonian 相似，但每个动量模的权重由 $\omega_p$ 换成 $\vec p$。产生算符彼此对易，使得交换粒子标签不改变状态；自旋零则对应本课讨论的标量场。

---

# 4. 同一动量模的占据与态归一化

对应图片：

- 4

## 板书整理

![[Picture/6.1/4.jpg]]

同一个动量 $\vec p$ 可以对应任意多个粒子：

$$
a_{\vec p}^{\dagger}\cdots a_{\vec p}^{\dagger}|0\rangle.
$$

态归一化（State normalization）：

单粒子态定义为

$$
\boxed{|\vec p\rangle\equiv\sqrt{2\omega_p}\,
a_{\vec p}^{\dagger}|0\rangle.}
$$

$N$ 粒子态定义为

$$
\boxed{
|\vec p_1,\ldots,\vec p_N\rangle
\equiv\sqrt{2\omega_{p_1}}\cdots\sqrt{2\omega_{p_N}}\,
a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle.
}
$$

## 解释

玻色子的同一动量模没有占据数上限。这里的“归一化”是对连续动量标签的态选定归一化约定，并不是把每个动量本征态的范数设为一；具体内积在下一张板书计算。

---

# 5. 单粒子态的内积

对应图片：

- 5

## 板书整理

![[Picture/6.1/5.jpg]]

考虑

$$
\langle\vec p|\vec q\rangle
=2\sqrt{\omega_p\omega_q}\,
\langle0|a_{\vec p}a_{\vec q}^{\dagger}|0\rangle.
$$

其中

$$
\begin{aligned}
\langle0|a_{\vec p}a_{\vec q}^{\dagger}|0\rangle
&=(2\pi)^3\delta^3(\vec p-\vec q)\langle0|0\rangle
+\langle0|a_{\vec q}^{\dagger}a_{\vec p}|0\rangle,\\
\langle0|0\rangle&\equiv1,\\
\langle0|a_{\vec q}^{\dagger}a_{\vec p}|0\rangle&=0.
\end{aligned}
$$

因此

$$
\boxed{
\langle\vec p|\vec q\rangle
=(2\pi)^3\,2\omega_p\,\delta^3(\vec p-\vec q).
}
$$

板书标注：Lorentz invariant（Lorentz 不变）。

> 此处使用了 $[a_{\vec p},a_{\vec q}^{\dagger}]=(2\pi)^3\delta^3(\vec p-\vec q)$、$a_{\vec p}|0\rangle=0$，并在 $\delta^3(\vec p-\vec q)$ 的支持上令 $\omega_q=\omega_p$。

左下角另有一个未继续展开的缩并表达式：

$$
g^{\mu\nu}p_\mu p_\nu.
$$

## 解释

$\sqrt{2\omega_p}$ 因子使单粒子态内积采用相对论性归一化。这里的 Lorentz 不变性针对整个组合 $2\omega_p\delta^3(\vec p-\vec q)$；三维 $\delta$ 函数本身不是 Lorentz 标量。

---

# 6. 场算符作用于真空

对应图片：

- 6

## 板书整理

![[Picture/6.1/6.jpg]]

进入波函数（Wave-function）的讨论。场展开为

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}
\left[
a_{\vec p}e^{i(-\omega_p t+\vec p\cdot\vec x)}
+a_{\vec p}^{\dagger}e^{-i(-\omega_p t+\vec p\cdot\vec x)}
\right].
$$

考虑

$$
\phi(x)|0\rangle
=\int\frac{d^3p}{(2\pi)^3\,2\omega_p}\,
\underbrace{\sqrt{2\omega_p}\,a_{\vec p}^{\dagger}|0\rangle}_{|\vec p\rangle}
e^{-i(-\omega_p t+\vec p\cdot\vec x)}.
$$

因此

$$
\phi(x)|0\rangle
=\int\frac{d^3p}{(2\pi)^3}\,
\frac{|\vec p\rangle}{2\omega_p}
e^{-i(-\omega_p t+\vec p\cdot\vec x)}.
$$

板书解释：把 $\phi(x)$ 理解为在位置 $\vec x$、时刻 $t\equiv x^0$ 产生粒子的算符；但是得到的态并不具有确定的动量。

> 此处使用了湮灭算符作用于真空为零的性质，故只剩产生算符项。

## 解释

上式明确展示了 $\phi(x)|0\rangle$ 是不同动量单粒子态的叠加。“产生粒子”的说法在这里针对场作用于真空；完整的 $\phi(x)$ 同时包含产生与湮灭两部分。该局域场激发的表述也不等于已经证明它是严格的位置本征态。

---

# 7. 场矩阵元与自由粒子的平面波

对应图片：

- 7

## 板书整理

![[Picture/6.1/7.jpg]]

考虑

$$
\langle\vec p|\phi(x)|0\rangle
=\int\frac{d^3q}{(2\pi)^3}\,
\frac{\langle\vec p|\vec q\rangle}{2\omega_q}
e^{-i(-\omega_qt+\vec q\cdot\vec x)}.
$$

代入板书上方标注的

$$
\langle\vec p|\vec q\rangle
=(2\pi)^3\,2\omega_p\,\delta^3(\vec p-\vec q),
$$

得到

$$
\langle\vec p|\phi(x)|0\rangle
=e^{i\omega_pt}e^{-i\vec p\cdot\vec x}.
$$

进而

$$
\boxed{
\langle0|\phi(x)|\vec p\rangle
=e^{-i\omega_pt}e^{i\vec p\cdot\vec x}.
}
$$

这是动量为 $\vec p$ 的自由粒子的波函数。

> 此处先使用 $\delta$ 函数完成动量积分，再利用实标量场的 Hermitian 性 $\phi(x)^{\dagger}=\phi(x)$ 对矩阵元取复共轭。

## 解释

场算符本身是算符，而真空与单粒子态之间的矩阵元是普通复函数。这里的矩阵元恰好具有确定能量、确定动量的平面波形式。

---

# 8. 传播子：展开不同时空点的场对易子

对应图片：

- 8

## 板书整理

![[Picture/6.1/8.jpg]]

传播子（Propagators）。板书在右上角给出约定

$$
p\cdot x\equiv-p^0t+\vec p\cdot\vec x.
$$

考虑场对易子，将场展开代入：

$$
\begin{aligned}
[\phi(x),\phi(y)]
={}&\int\frac{d^3p}{(2\pi)^3}\frac{d^3q}{(2\pi)^3}
\frac{1}{2\sqrt{\omega_p\omega_q}}\\
&\quad\times\left[
a_{\vec p}e^{ip\cdot x}+a_{\vec p}^{\dagger}e^{-ip\cdot x},\,
a_{\vec q}e^{iq\cdot y}+a_{\vec q}^{\dagger}e^{-iq\cdot y}
\right].
\end{aligned}
$$

计算算符对易子后：

$$
\begin{aligned}
[\phi(x),\phi(y)]
={}&\int\frac{d^3p}{(2\pi)^3}\frac{d^3q}{(2\pi)^3}
\frac{1}{2\sqrt{\omega_p\omega_q}}\\
&\quad\times\left[
(2\pi)^3\delta^3(\vec p-\vec q)e^{ip\cdot x-iq\cdot y}
-(2\pi)^3\delta^3(\vec p-\vec q)e^{-ip\cdot x+iq\cdot y}
\right].
\end{aligned}
$$

> 此处使用了 $[a,a]=[a^{\dagger},a^{\dagger}]=0$，以及 $[a_{\vec p}^{\dagger},a_{\vec q}]=-(2\pi)^3\delta^3(\vec p-\vec q)$；第二项的负号来自对易顺序。

## 解释

本页保留了两个独立动量积分，以展示对易关系如何产生 $\delta$ 函数。这里的场展开在正能量质量壳上取 $p^0=\omega_p$、$q^0=\omega_q$。

---

# 9. 场对易子的积分形式与复能量极点

对应图片：

- 9

## 板书整理

![[Picture/6.1/9.jpg]]

完成上一页的 $\vec q$ 积分，得到

$$
[\phi(x),\phi(y)]
=\int\frac{d^3p}{(2\pi)^3}\frac{1}{2\omega_p}
\left[e^{ip\cdot(x-y)}-e^{-ip\cdot(x-y)}\right].
$$

板书标注：这是 c-number，省略了与单位算符的乘积。

因此

$$
\boxed{
\langle0|[\phi(x),\phi(y)]|0\rangle
=\int\frac{d^3p}{(2\pi)^3}\frac{1}{2\omega_p}
\left[e^{ip\cdot(x-y)}-e^{-ip\cdot(x-y)}\right].
}
$$

接着考虑四维积分：

$$
\begin{aligned}
&\int\frac{d^4p}{(2\pi)^4}
\frac{e^{ip\cdot x}}{(p^0+i\epsilon)^2-(\vec p^{\,2}+m^2)}\\
&\qquad=\int\frac{d^3p}{(2\pi)^3}\,e^{i\vec p\cdot\vec x}
\int_{-\infty}^{\infty}\frac{dp^0}{2\pi}
\frac{e^{-ip^0x^0}}{(p^0+i\epsilon)^2-\omega_p^2},
\end{aligned}
$$

其中

$$
\vec p^{\,2}+m^2\equiv\omega_p^2.
$$

板书注明：隐含取极限 $\displaystyle\lim_{\epsilon\to0^+}$。

极点（Poles）满足

$$
p^0+i\epsilon=\pm\omega_p
\quad\longrightarrow\quad
p^0=\pm\omega_p-i\epsilon.
$$

## 解释

自由场对易子中的产生、湮灭算符全部消去，剩下一个乘以单位算符的函数。随后引入的四维积分中，$p^0$ 是独立积分变量；$i\epsilon$ 使两个极点都位于实轴下方，为下一页的围道积分指定极点位置。

---

# 10. 围道积分与阶跃函数

对应图片：

- 10

## 板书整理

![[Picture/6.1/10.jpg]]

本页继续计算图片 9 的四维积分。为指代该积分，下文记为 $I(x)$（此简记为整理时添加）。

复 $p^0$ 平面的围道图中，两极点为

$$
-\omega_p-i\epsilon,\qquad \omega_p-i\epsilon.
$$

围道选择如下：

- $x^0<0$：在上半平面闭合，内部没有极点。
- $x^0>0$：在下半平面闭合，包含两个极点；方向为顺时针（clockwise），因此留数定理带负号。

板书将结果写为

$$
\begin{aligned}
I(x)={}&-\Theta(x^0)\int\frac{d^3p}{(2\pi)^3}
e^{i\vec p\cdot\vec x}\frac{1}{2\pi}\\
&\times\left[
2\pi i\,\underset{p^0=\omega_p-i\epsilon}{\operatorname{Res}}
\frac{e^{-ip^0x^0}}{(p^0+i\epsilon)^2-\omega_p^2}
+2\pi i\,\underset{p^0=-\omega_p-i\epsilon}{\operatorname{Res}}
\frac{e^{-ip^0x^0}}{(p^0+i\epsilon)^2-\omega_p^2}
\right].
\end{aligned}
$$

计算两个简单极点的留数：

$$
I(x)=-i\Theta(x^0)\int\frac{d^3p}{(2\pi)^3}
e^{i\vec p\cdot\vec x}
\left[
\frac{e^{-i(\omega_p-i\epsilon)x^0}}{2\omega_p}
+\frac{e^{-i(-\omega_p-i\epsilon)x^0}}{-2\omega_p}
\right].
$$

板书注明在 $\epsilon=0$ 时留数表达式有限，取隐含的 $\epsilon\to0^+$ 极限：

$$
I(x)=-i\Theta(x^0)\int\frac{d^3p}{(2\pi)^3}
\frac{1}{2\omega_p}
\left[
e^{i\vec p\cdot\vec x-i\omega_px^0}
-e^{i\vec p\cdot\vec x+i\omega_px^0}
\right].
$$

在第二项中作 $\vec p\to-\vec p$ 的变量替换，最终

$$
I(x)=-i\Theta(x^0)\int\frac{d^3p}{(2\pi)^3}
\frac{1}{2\omega_p}
\left[e^{ip\cdot x}-e^{-ip\cdot x}\right].
$$

> 此处使用了留数定理，以及 $\omega_{-p}=\omega_p$ 和三维积分测度在 $\vec p\to-\vec p$ 下不变的性质。最后一式的 $p^0$ 已取极点极限中的正值 $\omega_p$。

## 解释

$e^{-ip^0x^0}$ 决定应在哪个半平面闭合围道。$x^0<0$ 时积分为零，$x^0>0$ 时由两个留数给出，因此结果带有阶跃函数 $\Theta(x^0)$。这里“$\epsilon=0$ 时有限”针对算出留数后的表达式，不是先把原积分实轴上的极点处方删去。

---

# 11. 推迟传播子的定义

对应图片：

- 11

## 板书整理

![[Picture/6.1/11.jpg]]

定义推迟传播子（Retarded propagator）：

$$
\boxed{
D_R(x-y)\equiv i\int\frac{d^4p}{(2\pi)^4}
\frac{e^{ip\cdot(x-y)}}{(p^0+i\epsilon)^2-\omega_p^2}.
}
$$

已经证明

$$
\boxed{
D_R(x-y)=\Theta(x^0-y^0)
\langle0|[\phi(x),\phi(y)]|0\rangle.
}
$$

## 解释

阶跃函数使 $D_R(x-y)$ 在 $x^0<y^0$ 时为零，这就是此处“推迟”的时间条件。定义中的整体因子 $i$ 与上一页围道积分产生的 $-i$ 相消；后面的格林函数方程也沿用这一归一化约定。

---

# 12. Klein–Gordon 格林函数：动量空间证明

对应图片：

- 12

## 板书整理

![[Picture/6.1/12.jpg]]

注意：$D_R(x)$ 是 Klein–Gordon 方程的格林函数，即

$$
\boxed{(\Box-m^2)D_R(x)=i\delta^4(x).}
$$

**Proof #1（easy）：**

$$
\begin{aligned}
(\Box-m^2)D_R(x)
&=i(\Box-m^2)\int\frac{d^4p}{(2\pi)^4}
\frac{e^{ip\cdot x}}{(p^0+i\epsilon)^2-\omega_p^2}\\
&=i\int\frac{d^4p}{(2\pi)^4}
\frac{(\Box-m^2)e^{ip\cdot x}}
{(p^0+i\epsilon)^2-\omega_p^2}.
\end{aligned}
$$

板书旁注给出作用于平面波后的因子（包含蓝字补注的 $-m^2$）：

$$
\begin{aligned}
-p\cdot p-m^2
&=-\left(-(p^0)^2+\vec p^{\,2}\right)-m^2\\
&=(p^0)^2-(\vec p^{\,2}+m^2)\\
&=(p^0)^2-\omega_p^2.
\end{aligned}
$$

因此

$$
(\Box-m^2)D_R(x)
=i\int\frac{d^4p}{(2\pi)^4}
\frac{\left[(p^0)^2-\omega_p^2\right]e^{ip\cdot x}}
{(p^0+i\epsilon)^2-\omega_p^2}.
$$

板书用箭头标记 $\epsilon\to0$，得到

$$
(\Box-m^2)D_R(x)
=i\int\frac{d^4p}{(2\pi)^4}e^{ip\cdot x}
=i\delta^4(x).
$$

> 此处使用了 $\delta$ 函数的 Fourier 表示。分子、分母的消去是在隐含的 $\epsilon\to0^+$ 分布极限下进行，有限 $\epsilon$ 时二者并不相等。

## 解释

本课采用 $p\cdot x=-p^0x^0+\vec p\cdot\vec x$，相应地 $\Box=-\partial_0^2+\nabla^2$。波动算符作用于 Fourier 指数后给出动量多项式，抵消传播子的分母，留下点源 $i\delta^4(x)$。

---

# 13. 第二种证明：对阶跃函数与场对易子求导

对应图片：

- 13

## 板书整理

![[Picture/6.1/13.jpg]]

**Proof #2：** 从

$$
D_R(x)=\Theta(x^0)\langle0|[\phi(x),\phi(0)]|0\rangle
$$

出发，其中 $\phi(0)$ 表示时空原点处的场。

板书所用的算符及乘积法则为

$$
\Box=\partial^\mu\partial_\mu,
$$

$$
\begin{aligned}
\Box(fg)
&=\partial^\mu\partial_\mu(fg)\\
&=(\Box f)g+2(\partial^\mu f)(\partial_\mu g)+f\Box g.
\end{aligned}
$$

阶跃函数的导数：

$$
\frac{d}{dx}\Theta(x)=\delta(x),
$$

$$
\partial_\mu\Theta(x^0)
=\frac{\partial}{\partial x^0}\Theta(x^0)\,\delta_\mu^{\,0}
=\delta(x^0)\,\delta_\mu^{\,0}.
$$

因此（包含板书在第一项下方补写的真空对易子因子）

$$
\begin{aligned}
\Box D_R(x)
={}&[\Box\Theta(x^0)]\langle0|[\phi(x),\phi(0)]|0\rangle\\
&+2[\partial^\mu\Theta(x^0)]\,
\partial_\mu\langle0|[\phi(x),\phi(0)]|0\rangle\\
&+\Theta(x^0)\langle0|[\Box\phi(x),\phi(0)]|0\rangle.
\end{aligned}
$$

板书标注：只有 $\mu=0$ 的导数有贡献；同时

$$
\Box\phi(x)=m^2\phi(x).
$$

于是

$$
\begin{aligned}
\Box D_R(x)
={}&-\delta'(x^0)
\langle0|[\phi(x^0,\vec x),\phi(0,\vec0)]|0\rangle\\
&-2\delta(x^0)\,\partial_0
\langle0|[\phi(x),\phi(0)]|0\rangle\\
&+m^2\Theta(x^0)
\langle0|[\phi(x),\phi(0)]|0\rangle.
\end{aligned}
$$

板书注明：两个负号来自对时间指标 $\mu=0$ 的升指标操作（from raising index）。第一行的 $x^0$ 旁有指向零的标记，其分布处理在下一张板书继续。

## 解释

此处 $\partial^0=-\partial_0$，所以 $\Box\Theta(x^0)=-\delta'(x^0)$。场方程处理了乘积法则中的最后一项；余下两项集中在 $x^0=0$，需要结合等时对易关系计算，不能把 $\delta'(x^0)$ 简单当成 $\delta(x^0)$。

---

# 14. 等时对易关系与分布导数：完成第二种证明

对应图片：

- 14

## 板书整理

![[Picture/6.1/14.jpg]]

回顾（Recall）：

$$
[\phi(0,\vec x),\phi(0,\vec y)]=0,
$$

$$
\partial_0\phi(x)=\pi(x),
$$

$$
[\pi(0,\vec y),\phi(0,\vec x)]
=-i\delta^3(\vec x-\vec y).
$$

接着处理 $\delta'$ 项。板书可见内容为

$$
\begin{aligned}
&\delta'(x^0)\langle0|[\phi(x^0,\vec x),\phi(0,\vec0)]|0\rangle\\
&\quad=\frac{\partial}{\partial x^0}
\left(\delta(x^0)\langle0|[\phi(x^0,0),\phi(0)]|0\rangle\right)
-\delta(x^0)\partial_0\langle0|[\phi(x),\phi(y)]|0\rangle.
\end{aligned}
$$

板书把括号中的 $\delta(x^0)$ 与等时场对易子之积标为零，并在这一整个导数项下标出“$=0$”。上式右端最后的 ket 在照片右缘被截断，末尾的 $|0\rangle$ 按可见结构补全；$\phi(x^0,0)$ 和 $\phi(y)$ 则按图中写法保留。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 14 中部的 $\delta'$ 项乘积求导公式。
>
> 板书内容：左端含 $\phi(x^0,\vec x)$、$\phi(0,\vec0)$，右端括号内写成 $\phi(x^0,0)$，最后一项又出现 $\phi(y)$。
>
> 检查结果：空间自变量与第二个场的位置记号疑似前后不一致。
>
> 说明：若对左端使用乘积法则，右端应保持同一个对易子 $\langle0|[\phi(x^0,\vec x),\phi(0,\vec0)]|0\rangle$。本证明已经取第二个点为原点，故 $\phi(y)$ 也应在 $y=0$ 下理解。求导恒等式的结构是 $\delta'f=(\delta f)'-\delta f'$；当 $f(0)=0$ 时，消失的是 $(\delta f)'$，并不能据此断言 $\delta'f=0$。
>
> 注意：以上为检查提示，未修改原板书内容；照片右缘截断处已另行注明。

最后一行承接图片 13 的 $\Box D_R(x)$，板书给出

$$
\Box D_R(x)
=+i\delta(x^0)\delta^3(\vec x)
+m^2\Theta(x^0)\langle0|[\phi(x),\phi(0)]|0\rangle.
$$

其中板书用下括号标出

$$
\delta(x^0)\delta^3(\vec x)=\delta^4(x).
$$

> 此处使用了分布的乘积求导法则和等时正则对易关系。令 $f(x)=\langle0|[\phi(x),\phi(0)]|0\rangle$，则 $f(0,\vec x)=0$，而 $\left.\partial_0f(x)\right|_{x^0=0}=-i\delta^3(\vec x)$。因此上一页的 $-\delta'f-2\delta\partial_0f$ 合并为 $-\delta\partial_0f=i\delta^4(x)$；这是板书末行所用的省略步骤。

## 解释

末行中的第二项就是 $m^2D_R(x)$。移到左边便得到图片 12 已提出的目标 $(\Box-m^2)D_R(x)=i\delta^4(x)$。这说明格林函数的点源来自阶跃函数在等时时刻的导数，以及场和共轭动量的等时对易关系。

---

# 本节知识结构

作业提醒与上节课的 Hamiltonian、多粒子能量回顾（图片 1）  
↓  
单粒子能量关系、自由粒子解释与非负能量（图片 2）  
↓  
动量算符、总动量与玻色交换对称性（图片 3）  
↓  
同一动量模的任意占据、单粒子和多粒子态归一化（图片 4）  
↓  
单粒子态内积及 Lorentz 不变归一化（图片 5）  
↓  
场作用于真空、场矩阵元与平面波（图片 6–7）  
↓  
不同时空点的场对易子与 c-number 结果（图片 8–9）  
↓  
复能量极点、围道积分与阶跃函数（图片 9–10）  
↓  
推迟传播子及其与场对易子的关系（图片 11）  
↓  
Klein–Gordon 格林函数方程的动量空间证明（图片 12）  
↓  
阶跃函数求导、等时对易关系与第二种证明（图片 13–14）

---

# 核心公式清单

以下按课堂顺序汇总；疑似笔误仍保留并指向正文检查提示。含 $\epsilon$ 的积分均隐含 $\epsilon\to0^+$。

| 公式 | 含义 |
| ----- | ---- |
| $\omega_p=\sqrt{\vec p^{\,2}+m^2}$ | 单个自由粒子的能量 |
| $H=\int\frac{d^3p}{(2\pi)^3}\omega_p a_{\vec p}^{\dagger}a_{\vec p}$ | 去掉真空能后的 Hamiltonian |
| $E=\sum_{n=1}^{N}\omega_{p_n}$ | $N$ 粒子态的总能量 |
| $Ha_{\vec p}^{\dagger}\lvert0\rangle=\omega_p\lvert0\rangle$ | 图片 2 原式；右端疑似漏写产生算符，见第 2 节 |
| $\vec P=-\int d^3x\,\pi\vec\nabla\phi=\int\frac{d^3p}{(2\pi)^3}\vec p\,a_{\vec p}^{\dagger}a_{\vec p}$ | 动量算符，其多粒子态本征值为 $\sum_n\vec p_n$ |
| $a_{\vec p}^{\dagger}a_{\vec q}^{\dagger}\lvert0\rangle=a_{\vec q}^{\dagger}a_{\vec p}^{\dagger}\lvert0\rangle$ | 玻色子的交换对称性 |
| $\lvert\vec p\rangle\equiv\sqrt{2\omega_p}\,a_{\vec p}^{\dagger}\lvert0\rangle$ | 单粒子态归一化约定 |
| $\lvert\vec p_1,\ldots,\vec p_N\rangle\equiv\bigl(\prod_{n=1}^{N}\sqrt{2\omega_{p_n}}\bigr)a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}\lvert0\rangle$ | 多粒子态归一化约定 |
| $\langle\vec p\vert\vec q\rangle=(2\pi)^3\,2\omega_p\delta^3(\vec p-\vec q)$ | Lorentz 不变的单粒子态内积 |
| $\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}[a_{\vec p}e^{ip\cdot x}+a_{\vec p}^{\dagger}e^{-ip\cdot x}]$ | 实标量场展开，$p^0=\omega_p$ |
| $\phi(x)\lvert0\rangle=\int\frac{d^3p}{(2\pi)^3\,2\omega_p}\lvert\vec p\rangle e^{-ip\cdot x}$ | 场作用于真空得到动量态叠加 |
| $\langle\vec p\vert\phi(x)\vert0\rangle=e^{i\omega_pt-i\vec p\cdot\vec x}$；$\langle0\vert\phi(x)\vert\vec p\rangle=e^{-i\omega_pt+i\vec p\cdot\vec x}$ | 场矩阵元与自由粒子平面波 |
| $p\cdot x=-p^0x^0+\vec p\cdot\vec x$ | 本课的四维内积约定 |
| $[\phi(x),\phi(y)]=\int\frac{d^3p}{(2\pi)^3\,2\omega_p}[e^{ip\cdot(x-y)}-e^{-ip\cdot(x-y)}]$ | 场对易子，右端隐含单位算符 |
| $p^0=\pm\omega_p-i\epsilon$ | 推迟处方的两个极点均在下半平面 |
| $\int\frac{d^4p}{(2\pi)^4}\frac{e^{ip\cdot x}}{(p^0+i\epsilon)^2-\omega_p^2}=-i\Theta(x^0)\int\frac{d^3p}{(2\pi)^3\,2\omega_p}[e^{ip\cdot x}-e^{-ip\cdot x}]$ | 围道积分结果；右端 $p^0=\omega_p$ |
| $D_R(x-y)=i\int\frac{d^4p}{(2\pi)^4}\frac{e^{ip\cdot(x-y)}}{(p^0+i\epsilon)^2-\omega_p^2}$ | 推迟传播子的定义 |
| $D_R(x-y)=\Theta(x^0-y^0)\langle0\vert[\phi(x),\phi(y)]\vert0\rangle$ | 推迟传播子与场对易子的关系 |
| $(\Box-m^2)D_R(x)=i\delta^4(x)$ | Klein–Gordon 格林函数方程 |
| $\Box=\partial^\mu\partial_\mu$；$\Box(fg)=(\Box f)g+2(\partial^\mu f)(\partial_\mu g)+f\Box g$ | 第二种证明使用的乘积法则 |
| $\Theta'(x)=\delta(x)$；$\partial_\mu\Theta(x^0)=\delta(x^0)\delta_\mu^{\,0}$ | 阶跃函数的分布导数 |
| $[\phi(0,\vec x),\phi(0,\vec y)]=0$；$\partial_0\phi=\pi$；$[\pi(0,\vec y),\phi(0,\vec x)]=-i\delta^3(\vec x-\vec y)$ | 第二种证明使用的等时关系 |
| $\delta'f=(\delta f)'-\delta f'$ | 处理 $\delta'$ 项的乘积求导恒等式；图片 14 的自变量问题见第 14 节 |
| $\delta(x^0)\delta^3(\vec x)=\delta^4(x)$ | 合并时间和空间点源 |
