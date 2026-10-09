---
title: "量子场论导论 Lecture 5.1"
date: 2026-10-09
tags:
  - 量子场论导论
  - lecture
  - Lorentz不变测度
  - 正则量子化
  - Klein-Gordon场
  - 真空能
  - 多粒子态
source: "课堂板书"
---

# Lecture 5.1: 实标量场的正则量子化、Hamiltonian 与多粒子态

## 本节内容概览

本节从实标量场的平面波展开出发，证明正能量质量壳上的积分测度具有 Lorentz 不变性。随后将展开系数提升为产生、湮灭算符，定义真空，并计算位置空间及场与共轭动量的对易关系。接着将场展开代入 Hamiltonian，逐项整理得到粒子激发的能量项和真空零点能。最后通过平移能量零点去掉真空能常数，构造多粒子态并证明它们是 Hamiltonian 的本征态。

<!-- date 为整理日期；原板书未标明授课日期。正文按 Picture/5.1/1.jpg 至 14.jpg 顺序整理。 -->

---

# 1. 上节回顾与实标量场展开

对应图片：

- 1

## 板书整理

![[Picture/5.1/1.jpg]]

上节课内容（Last time）：

- Noether theorem（Noether 定理）；
- Energy-momentum tensor（能量动量张量）；
- External sources（外部源）；
- Field quantization（场量子化）：实标量场。

实标量场满足

$$
\Box\phi-m^2\phi=0,
$$

并定义

$$
\omega_p\equiv\sqrt{\vec p^{\,2}+m^2}.
$$

场的平面波展开为

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}
\left[
a_{\vec p}e^{i(-\omega_pt+\vec p\cdot\vec x)}
+a_{\vec p}^{*}e^{-i(-\omega_pt+\vec p\cdot\vec x)}
\right].
$$

板书在这一展开旁标注：

- real：实场；
- Lorentz invariant：Lorentz 不变。

接着提出命题（Proposition）：

$$
\frac{d^3p}{2\omega_p}
\quad\text{是 Lorentz 不变测度。}
$$

## 解释

两个平面波项互为复共轭，保证经典场 $\phi(x)$ 为实数。这里的 $a_{\vec p}$ 仍是经典展开系数，尚未提升为算符。板书对场展开的 Lorentz 不变性及测度的说明将在后两张图片中展开。

---

# 2. Lorentz 不变测度的证明

对应图片：

- 2
- 3

## 板书整理

### 2.1 改写场展开与四维积分（图片 2）

![[Picture/5.1/2.jpg]]

板书先规定 $\sqrt{2\omega_p}\,a_{\vec p}$ 是 Lorentz 不变量，将场改写为

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3\,2\omega_p}
\left[
\sqrt{2\omega_p}\,a_{\vec p}e^{ip\cdot x}
+\sqrt{2\omega_p}\,a_{\vec p}^{*}e^{-ip\cdot x}
\right].
$$

其中

$$
p\cdot x\equiv-p^0t+\vec p\cdot\vec x
\equiv-\omega_pt+\vec p\cdot\vec x,
\qquad
p^\mu\equiv(\omega_p,\vec p),
$$

$$
p^2\equiv p\cdot p.
$$

在三维动量积分中，$p^0\equiv\omega_p$，已经取在质量壳上。

板书随后指出

$$
\int\frac{d^3p}{2\omega_p}[\cdots]
=\int d^4p\,\delta(p^2+m^2)\,\Theta(p^0)[\cdots].
$$

阶跃函数定义为

$$
\Theta(x)=
\begin{cases}
1,&x>0,\\
0,&x<0.
\end{cases}
$$

在右侧四维积分中，$p^0$ 是独立积分变量。因此右侧可展开成

$$
\int d^3p\int_{-\infty}^{\infty}dp^0\,
\delta\!\left(-(p^0)^2+\vec p^{\,2}+m^2\right)
\Theta(p^0)[\cdots].
$$

$\delta$ 函数的自变量具有两个零点：

$$
p^0=\pm\sqrt{\vec p^{\,2}+m^2},
$$

其对 $p^0$ 的导数为

$$
\frac{d}{dp^0}\left[-(p^0)^2+\vec p^{\,2}+m^2\right]=-2p^0.
$$

### 2.2 展开 $\delta$ 函数并完成积分（图片 3）

![[Picture/5.1/3.jpg]]

板书回顾公式：若 $g(x_i)=0$，则

$$
\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}.
$$

> 此处使用了 $\delta$ 函数在简单零点处的变量替换性质；分母中的导数取绝对值。

接上图的积分，得到

$$
\begin{aligned}
&\int d^3p\int_{-\infty}^{\infty}dp^0
\left[
\frac{\delta\!\left(p^0-\sqrt{\vec p^{\,2}+m^2}\right)}
{2\sqrt{\vec p^{\,2}+m^2}}
+\frac{\delta\!\left(p^0+\sqrt{\vec p^{\,2}+m^2}\right)}
{2\sqrt{\vec p^{\,2}+m^2}}
\right]\Theta(p^0)[\cdots]\\
&=\int d^3p\,
\frac{\Theta\!\left(\sqrt{\vec p^{\,2}+m^2}\right)}
{2\sqrt{\vec p^{\,2}+m^2}}[\cdots]\\
&=\int d^3p\,\frac{1}{2\omega_p}[\cdots].
\end{aligned}
$$

第二个 $\delta$ 项位于负能量根，因 $\Theta(p^0)$ 而不贡献；正能量根处 $\Theta(\omega_p)=1$。最后两行的 $[\cdots]$ 均取 $p^0=\omega_p$。

由于

$$
d^4p,\qquad p^2+m^2,\qquad\Theta(p^0)
$$

在保时向（orthochronous）Lorentz 变换下保持不变，故

$$
\boxed{\frac{d^3p}{2\omega_p}\ \text{是 Lorentz 不变测度。}}
$$

板书特别注明：保时向变换保持 $p^0$ 的符号。

## 解释

$\delta(p^2+m^2)$ 把四维动量限制在质量壳上，$\Theta(p^0)$ 再选出正能量分支。对 $p^0$ 积分产生因子 $1/(2\omega_p)$，从而得到三维测度。这里保持能量符号的说法针对质量壳上的类时或非零类光动量；板书结论的范围是保时向 Lorentz 变换。

本讲采用 $p\cdot x=-p^0t+\vec p\cdot\vec x$ 的符号约定，因此 $p^2=-m^2$ 与开头的 $\Box\phi-m^2\phi=0$ 相容。$\sqrt{2\omega_p}\,a_{\vec p}$ 的不变性是展开系数的变换规定，并不意味着 $a_{\vec p}$ 本身在变换前后保持同一数值。

---

# 3. 正则量子化与真空

对应图片：

- 4

## 板书整理

![[Picture/5.1/4.jpg]]

正则量子化（Canonical quantization），板书也称为“第二”量子化（“second” quantization）：

$$
a_{\vec p},\ a_{\vec p}^{*}
\quad\longrightarrow\quad
a_{\vec p},\ a_{\vec p}^{\dagger}
\qquad\text{（算符）}.
$$

规定对易关系

$$
\boxed{
[a_{\vec p},a_{\vec k}]=0
=[a_{\vec p}^{\dagger},a_{\vec k}^{\dagger}],
\qquad
[a_{\vec p},a_{\vec k}^{\dagger}]
=(2\pi)^3\delta^3(\vec p-\vec k).
}
$$

真空或基态（Vacuum or ground state）$|0\rangle$ 满足

$$
a_{\vec p}|0\rangle=0
\quad\Longleftrightarrow\quad
\langle0|a_{\vec p}^{\dagger}=0.
$$

其中 $a_{\vec p}$ 称为湮灭算符（annihilation operator），$a_{\vec p}^{\dagger}$ 称为产生算符（creation operator）。

## 解释

量子化后，复共轭系数对应为厄米共轭算符。真空条件对所有 $\vec p$ 成立，右侧等式是左侧取厄米共轭的结果；它并不表示 $a_{\vec p}^{\dagger}|0\rangle=0$。

---

# 4. 位置空间中的产生、湮灭算符

对应图片：

- 5

## 板书整理

![[Picture/5.1/5.jpg]]

板书注明位置空间的写法较少使用（seldom used），并定义

$$
a(\vec x)\equiv\int\frac{d^3p}{(2\pi)^3}
a_{\vec p}e^{i\vec p\cdot\vec x}.
$$

计算对易子：

$$
\begin{aligned}
[a(\vec x),a^{\dagger}(\vec y)]
&=\left[
\int\frac{d^3p}{(2\pi)^3}a_{\vec p}e^{i\vec p\cdot\vec x},
\int\frac{d^3k}{(2\pi)^3}a_{\vec k}^{\dagger}e^{-i\vec k\cdot\vec y}
\right]\\
&=\int\frac{d^3p}{(2\pi)^3}\int\frac{d^3k}{(2\pi)^3}
e^{i\vec p\cdot\vec x-i\vec k\cdot\vec y}
[a_{\vec p},a_{\vec k}^{\dagger}].
\end{aligned}
$$

代入

$$
[a_{\vec p},a_{\vec k}^{\dagger}]
=(2\pi)^3\delta^3(\vec p-\vec k),
$$

对 $\vec k$ 积分令 $\vec k\to\vec p$，于是

$$
\begin{aligned}
[a(\vec x),a^{\dagger}(\vec y)]
&=\int\frac{d^3p}{(2\pi)^3}e^{i\vec p\cdot(\vec x-\vec y)}\\
&=\boxed{\delta^3(\vec x-\vec y)}.
\end{aligned}
$$

> 此处使用了三维 $\delta$ 函数的 Fourier 积分表示。

## 解释

动量空间中的 $\delta^3(\vec p-\vec k)$ 消去一个动量积分，余下的平面波积分给出位置空间的 $\delta$ 函数。这也检验了 Fourier 变换与对易关系中的 $(2\pi)^3$ 因子彼此一致。

---

# 5. 场算符、共轭动量与谐振子类比

对应图片：

- 6
- 7

## 板书整理

### 5.1 场算符及共轭动量（图片 6）

![[Picture/5.1/6.jpg]]

场算符（Field operator）为

$$
\boxed{
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}
\left[
a_{\vec p}e^{i(-\omega_pt+\vec p\cdot\vec x)}
+a_{\vec p}^{\dagger}e^{-i(-\omega_pt+\vec p\cdot\vec x)}
\right].
}
$$

Klein–Gordon 场的正则共轭动量满足

$$
\pi=\dot\phi.
$$

因此

$$
\boxed{
\pi(x)=-i\int\frac{d^3p}{(2\pi)^3}\sqrt{\frac{\omega_p}{2}}
\left[
a_{\vec p}e^{i(-\omega_pt+\vec p\cdot\vec x)}
-a_{\vec p}^{\dagger}e^{-i(-\omega_pt+\vec p\cdot\vec x)}
\right].
}
$$

### 5.2 取 $t=0$ 并改写积分（图片 7）

![[Picture/5.1/7.jpg]]

考虑 $\phi(0,\vec x)$ 和 $\pi(0,\vec x)$。先有

$$
\phi(0,\vec x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}
\left[a_{\vec p}e^{i\vec p\cdot\vec x}
+a_{\vec p}^{\dagger}e^{-i\vec p\cdot\vec x}\right].
$$

在第二项中作 $\vec p\to-\vec p$，得到

$$
\phi(0,\vec x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}
\left[a_{\vec p}+a_{-\vec p}^{\dagger}\right]
e^{i\vec p\cdot\vec x}.
$$

同样地，

$$
\pi(0,\vec x)=-i\int\frac{d^3p}{(2\pi)^3}
\sqrt{\frac{\omega_p}{2}}
\left[a_{\vec p}-a_{-\vec p}^{\dagger}\right]
e^{i\vec p\cdot\vec x}.
$$

> 此处使用了积分变量替换与 $\omega_{-p}=\omega_p$；$a_{-\vec p}^{\dagger}$ 的下标来自变量替换。

板书将上述两式与量子力学谐振子作类比：

$$
\hat x=\frac{\hat a+\hat a^{\dagger}}{\sqrt{2\omega}},
\qquad
\hat p=-i\sqrt{\frac{\omega}{2}}\left(\hat a-\hat a^{\dagger}\right).
$$

## 解释

对场展开求时间导数时，正、负频项分别产生 $-i\omega_p$ 与 $+i\omega_p$，因此共轭动量的两项之间出现减号。$t=0$ 时的改写让两项具有相同空间指数，便于下一步计算等时对易子。板书的谐振子类比采用了相应的单位约定，场论公式中取 $\hbar=1$。

---

# 6. 等时正则对易关系及其检验

对应图片：

- 8
- 9（顶部，承接图片 8）

## 板书整理

### 6.1 对易关系与代入检验（图片 8）

![[Picture/5.1/8.jpg]]

板书先列出等时对易关系：

$$
\boxed{
[\phi(0,\vec x),\pi(0,\vec y)]
=i\delta^3(\vec x-\vec y),
}
$$

$$
\boxed{
[\phi(0,\vec x),\phi(0,\vec y)]=0
=[\pi(0,\vec x),\pi(0,\vec y)].
}
$$

它们对应量子力学中的

$$
[\hat x,\hat p]=i\hbar,
\qquad
[\hat x,\hat x]=0=[\hat p,\hat p].
$$

板书将同类场算符对易子为零的检验标为练习（exercise），随后实际计算混合对易子：

$$
\begin{aligned}
[\phi(0,\vec x),\pi(0,\vec y)]
={}&-\frac{i}{2}\int\frac{d^3p}{(2\pi)^3}\frac{d^3k}{(2\pi)^3}
\sqrt{\frac{\omega_k}{\omega_p}}\\
&\times\left[a_{\vec p}+a_{-\vec p}^{\dagger},
a_{\vec k}-a_{-\vec k}^{\dagger}\right]
e^{i\vec p\cdot\vec x}e^{i\vec k\cdot\vec y}.
\end{aligned}
$$

其中板书括号下标注

$$
\begin{aligned}
\left[a_{\vec p}+a_{-\vec p}^{\dagger},
a_{\vec k}-a_{-\vec k}^{\dagger}\right]
={}&-(2\pi)^3\delta^3(\vec p+\vec k)\\
&-(2\pi)^3\delta^3(\vec p+\vec k).
\end{aligned}
$$

### 6.2 完成积分（图片 9 顶部）

![[Picture/5.1/9.jpg]]

接上图，得到

$$
\begin{aligned}
[\phi(0,\vec x),\pi(0,\vec y)]
&=i\int\frac{d^3p}{(2\pi)^3}
e^{i\vec p\cdot\vec x}e^{-i\vec p\cdot\vec y}\\
&=i\delta^3(\vec x-\vec y).
\end{aligned}
$$

> 此处利用 $\delta^3(\vec p+\vec k)$ 令 $\vec k=-\vec p$，故 $\omega_k=\omega_p$，再使用 Fourier 积分表示。

## 解释

两个非零的交叉对易子都带负号，与式外的 $-i/2$ 合起来给出 $i$。这里检验的是同一时刻的对易关系；板书没有在此计算不同时刻的对易子。练习部分保留为练习，不补写课堂未展开的证明。

---

# 7. 将场展开代入 Hamiltonian

对应图片：

- 9（Hamiltonian 部分）
- 10

## 板书整理

### 7.1 Hamiltonian 与 $t=0$ 的计算技巧（图片 9）

图片 9 原图见上一部分；此处继续其下方的 Hamiltonian 内容。

自由实标量场的 Hamiltonian 为

$$
H=\int d^3x\left[
\frac12\pi^2+\frac12(\vec\nabla\phi)^2+\frac{m^2}{2}\phi^2
\right].
$$

板书给出的技巧（Trick）：在 $t=0$ 计算。根据 Noether 定理，

$$
\frac{dH}{dt}=0
\quad\Longrightarrow\quad H=H(t=0).
$$

旁边补充了场的空间梯度：

$$
\vec\nabla\phi(0,\vec x)
=i\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}
\vec p\left[a_{\vec p}+a_{-\vec p}^{\dagger}\right]
e^{i\vec p\cdot\vec x}.
$$

将 $\pi$、$\vec\nabla\phi$ 和 $\phi$ 的展开分别代入 $H$。下式的前两项写于图片 9，质量项和共同的指数因子续写于图片 10：

$$
\begin{aligned}
H={}&\int d^3x\int\frac{d^3p}{(2\pi)^3}\frac{d^3k}{(2\pi)^3}
\Bigg\{
-\frac{\sqrt{\omega_p\omega_k}}{4}
\left(a_{\vec p}-a_{-\vec p}^{\dagger}\right)
\left(a_{\vec k}-a_{-\vec k}^{\dagger}\right)\\
&\qquad-\frac{\vec p\cdot\vec k}{4\sqrt{\omega_p\omega_k}}
\left(a_{\vec p}+a_{-\vec p}^{\dagger}\right)
\left(a_{\vec k}+a_{-\vec k}^{\dagger}\right)\\
&\qquad+\frac{m^2}{4\sqrt{\omega_p\omega_k}}
\left(a_{\vec p}+a_{-\vec p}^{\dagger}\right)
\left(a_{\vec k}+a_{-\vec k}^{\dagger}\right)
\Bigg\}
e^{i\vec p\cdot\vec x}e^{i\vec k\cdot\vec x}.
\end{aligned}
$$

### 7.2 空间积分与各算符项的抵消（图片 10）

![[Picture/5.1/10.jpg]]

两个指数合并为

$$
e^{i\vec p\cdot\vec x}e^{i\vec k\cdot\vec x}
=e^{i(\vec p+\vec k)\cdot\vec x}.
$$

先对 $\vec x$ 积分，再对 $\vec k$ 积分：

$$
\int d^3x\,e^{i(\vec p+\vec k)\cdot\vec x}
=(2\pi)^3\delta^3(\vec p+\vec k)
\quad\Longrightarrow\quad\vec k=-\vec p.
$$

因此

$$
\begin{aligned}
H=\int\frac{d^3p}{(2\pi)^3}\Bigg\{
&-\frac{\omega_p}{4}
\left(a_{\vec p}-a_{-\vec p}^{\dagger}\right)
\left(a_{-\vec p}-a_{\vec p}^{\dagger}\right)\\
&+\frac{\vec p^{\,2}+m^2}{4\omega_p}
\left(a_{\vec p}+a_{-\vec p}^{\dagger}\right)
\left(a_{-\vec p}+a_{\vec p}^{\dagger}\right)
\Bigg\}.
\end{aligned}
$$

利用板书标出的

$$
\vec p^{\,2}+m^2=\omega_p^2,
$$

完整展开括号：

$$
\begin{aligned}
H=\frac14\int\frac{d^3p}{(2\pi)^3}\omega_p\Big\{
&-a_{\vec p}a_{-\vec p}
+a_{\vec p}a_{\vec p}^{\dagger}
+a_{-\vec p}^{\dagger}a_{-\vec p}
-a_{-\vec p}^{\dagger}a_{\vec p}^{\dagger}\\
&+a_{\vec p}a_{-\vec p}
+a_{\vec p}a_{\vec p}^{\dagger}
+a_{-\vec p}^{\dagger}a_{-\vec p}
+a_{-\vec p}^{\dagger}a_{\vec p}^{\dagger}
\Big\}.
\end{aligned}
$$

板书划去了相消的两组项：

$$
-a_{\vec p}a_{-\vec p}+a_{\vec p}a_{-\vec p}=0,
$$

$$
-a_{-\vec p}^{\dagger}a_{\vec p}^{\dagger}
+a_{-\vec p}^{\dagger}a_{\vec p}^{\dagger}=0.
$$

并在 $a_{-\vec p}^{\dagger}a_{-\vec p}$ 项下标明作 $\vec p\to-\vec p$ 的积分变量替换；化简结果接下一张图片。

## 解释

空间积分使两组 Fourier 动量互为相反数，梯度项因此贡献 $+\vec p^{\,2}$。它与质量项合成 $\omega_p^2$，使 $aa$ 和 $a^{\dagger}a^{\dagger}$ 两类项恰好抵消。整个过程中保留算符乘积的顺序，尚未将 $aa^{\dagger}$ 直接当成 $a^{\dagger}a$。

---

# 8. Hamiltonian 的零点能项

对应图片：

- 11

## 板书整理

![[Picture/5.1/11.jpg]]

接上图的化简结果：

$$
H=\frac12\int\frac{d^3p}{(2\pi)^3}\omega_p
\left\{a_{\vec p}a_{\vec p}^{\dagger}
+a_{\vec p}^{\dagger}a_{\vec p}\right\}.
$$

利用

$$
a_{\vec p}a_{\vec p}^{\dagger}
=a_{\vec p}^{\dagger}a_{\vec p}
+[a_{\vec p},a_{\vec p}^{\dagger}],
$$

得到

$$
H=\int\frac{d^3p}{(2\pi)^3}\omega_p
a_{\vec p}^{\dagger}a_{\vec p}
+\frac12\int\frac{d^3p}{(2\pi)^3}\omega_p\,
(2\pi)^3\delta^3(\vec0).
$$

板书将后项中的两个因子分别记为

$$
\rho_0\equiv\frac12\int\frac{d^3p}{(2\pi)^3}\omega_p,
\qquad
V=(2\pi)^3\delta^3(\vec0).
$$

其中系统体积（Volume of the system）的形式表示为

$$
\begin{aligned}
V&\equiv\int d^3x\cdot1\\
&=\int d^3x\,e^{i\vec0\cdot\vec x}\\
&=(2\pi)^3\delta^3(\vec0).
\end{aligned}
$$

板书在 $\rho_0$ 旁标注“zero-point energy”或“vacuum energy”，并与量子力学中的

$$
E_0=\frac{\omega}{2}
$$

作类比。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 11 的体积表示与零点能标注。
>
> 板书内容：$V=(2\pi)^3\delta^3(\vec0)$；将 $\rho_0=\frac12\int\frac{d^3p}{(2\pi)^3}\omega_p$ 标为“zero-point energy”或“vacuum energy”。
>
> 检查结果：这里的 $\delta^3(\vec0)$ 是形式记号，不是 $\delta$ 分布在一点的普通函数值；严格区分量纲时，$\rho_0$ 是能量密度。
>
> 说明：体积等式需在体积正则化的意义下理解。与 Hamiltonian 对应的真空总能量是 $\rho_0V$。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

交换 $a$ 与 $a^{\dagger}$ 的顺序会产生非零对易子，因此 Hamiltonian 除激发项外还有一个与态无关的常数项。每个动量模式贡献类似谐振子的 $\omega_p/2$，积分后形成零点能密度 $\rho_0$。

---

# 9. 平移能量零点

对应图片：

- 12

## 板书整理

![[Picture/5.1/12.jpg]]

先将 Hamiltonian 写成

$$
\boxed{
H=\int\frac{d^3p}{(2\pi)^3}\omega_p
a_{\vec p}^{\dagger}a_{\vec p}+\rho_0V.
}
$$

板书说明：虽然 $\rho_0$ 和 $V$ 在形式上都是无穷的，但它们只是常数；可以给 Hamiltonian 密度加一个常数来去掉这一项。

定义

$$
\mathcal H'\equiv\mathcal H+C.
$$

板书在 $C$ 旁注明：不影响 Euler–Lagrange 方程（does not affect E–L equations）。于是

$$
\begin{aligned}
H'&=H+\int d^3x\,C\\
&=H+CV\\
&=\int\frac{d^3p}{(2\pi)^3}\omega_p
a_{\vec p}^{\dagger}a_{\vec p}+(\rho_0+C)V.
\end{aligned}
$$

选择

$$
C=-\rho_0.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 12 用 $C=-\rho_0$ 消去形式上无穷的常数项。
>
> 板书内容：$H'=\int\frac{d^3p}{(2\pi)^3}\omega_p a_{\vec p}^{\dagger}a_{\vec p}+(\rho_0+C)V$，取 $C=-\rho_0$。
>
> 检查结果：这是形式上的减除，不能按普通实数运算直接解释为“无穷减无穷”。
>
> 说明：严谨处理需先引入正则化，在同一正则化下选择常数抵消真空能项，再讨论极限。课堂在这里没有展开这一过程。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

给能量密度加一个与场无关的常数，只会改变能量零点。在本讲的自由场设置中，这不改变场的运动方程；对应到 Lagrangian 密度就是减去同一个常数。板书的减除针对 $\rho_0V$ 这一能量项，并非把系统体积 $V$ 本身消去。

---

# 10. 真空能的减除与多粒子态的构造

对应图片：

- 13

## 板书整理

![[Picture/5.1/13.jpg]]

板书说明：利用 $\mathcal H$ 中一个不可观测的参数，抵消无穷项 $\rho_0V$，并将这一操作称为“renormalization”（重整化）。

随后讨论基态能量，并注明：从现在起取 $\rho_0=0$（set $\rho_0=0$ from now on）。

$$
H|0\rangle
=\int\frac{d^3p}{(2\pi)^3}\omega_p
a_{\vec p}^{\dagger}a_{\vec p}|0\rangle
=0.
$$

$N$ 粒子态（$N$-particle state）写为

$$
a_{\vec p_1}^{\dagger}a_{\vec p_2}^{\dagger}
\cdots a_{\vec p_N}^{\dagger}|0\rangle.
$$

## 解释

这里“取 $\rho_0=0$”表示已完成上图的能量零点减除，并把减除后的 $H'$ 重新记作 $H$，不是说原先的动量积分本身等于零。由于最右侧的湮灭算符作用在真空上为零，减除后的基态能量为零。连续施加 $N$ 个产生算符给出板书中的 $N$ 粒子态；此处尚未讨论态的归一化。

---

# 11. 多粒子态的能量本征值

对应图片：

- 14

## 板书整理

![[Picture/5.1/14.jpg]]

将减去真空能的 Hamiltonian 作用到 $N$ 粒子态上：

$$
\begin{aligned}
H a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle
=\int\frac{d^3p}{(2\pi)^3}\omega_p
a_{\vec p}^{\dagger}a_{\vec p}
a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle.
\end{aligned}
$$

板书在右侧重复列出需要使用的对易关系：

$$
[a_{\vec p},a_{\vec p_j}^{\dagger}]
=(2\pi)^3\delta^3(\vec p-\vec p_j).
$$

将 $a_{\vec p}$ 依次移过各产生算符，板书在括号下给出

$$
\begin{aligned}
&a_{\vec p}a_{\vec p_1}^{\dagger}\cdots
a_{\vec p_N}^{\dagger}|0\rangle\\
&\quad=(2\pi)^3\sum_{j=1}^{N}\delta^3(\vec p-\vec p_j)
\,a_{\vec p_1}^{\dagger}\cdots
a_{\vec p_{j-1}}^{\dagger}
a_{\vec p_{j+1}}^{\dagger}\cdots
a_{\vec p_N}^{\dagger}|0\rangle.
\end{aligned}
$$

> 此处使用了对易子的乘积展开性质，以及 $a_{\vec p}|0\rangle=0$。每一项只去掉被对易子选中的第 $j$ 个产生算符，最右侧仍含湮灭算符的项作用于真空后为零。

再对 $\vec p$ 积分，$\delta^3(\vec p-\vec p_j)$ 令 $\vec p\to\vec p_j$。原先外面的 $a_{\vec p}^{\dagger}$ 补回第 $j$ 个产生算符；图中用箭头标出了这一过程。

最终

$$
\begin{aligned}
H a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle
&=\sum_{j=1}^{N}\omega_{p_j}
a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle\\
&=\left(\sum_{j=1}^{N}\omega_{p_j}\right)
a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}|0\rangle.
\end{aligned}
$$

> 此处还使用了产生算符彼此对易，因此补回的 $a_{\vec p_j}^{\dagger}$ 可以移回原来的位置。

板书结论：$N$ 粒子态是 $H$ 的本征态，本征值为

$$
\boxed{E=\sum_{j=1}^{N}\omega_{p_j}.}
$$

## 解释

每次用对易子选中一个产生算符，就从 Hamiltonian 中取出对应模式的能量 $\omega_{p_j}$。所有贡献相加，得到自由场多粒子态的总能量；这一结果使用的是已经减去真空能常数的 Hamiltonian。

---

# 本节知识结构

上节回顾：Noether 定理、能量动量张量、外部源与实标量场展开（图片 1）  
↓  
利用质量壳 $\delta$ 函数与正能量条件证明 $d^3p/(2\omega_p)$ 的 Lorentz 不变性（图片 2–3）  
↓  
将经典系数提升为产生、湮灭算符，规定对易关系与真空（图片 4）  
↓  
Fourier 变换得到位置空间算符的对易关系（图片 5）  
↓  
写出场与共轭动量算符，在 $t=0$ 改写并与谐振子类比（图片 6–7）  
↓  
检验等时正则对易关系（图片 8–9 顶部）  
↓  
展开 Hamiltonian，完成空间积分并抵消 $aa$、$a^{\dagger}a^{\dagger}$ 项（图片 9–10）  
↓  
利用对易关系分离激发能与真空零点能（图片 11）  
↓  
给 Hamiltonian 密度加常数，减除真空能（图片 12）  
↓  
令减除后的真空能为零，构造 $N$ 粒子态（图片 13）  
↓  
证明 $N$ 粒子态的能量为 $\sum_{j=1}^{N}\omega_{p_j}$（图片 14）。

---

# 核心公式清单

以下按课堂出现顺序列出；使用 $p\cdot x=-\omega_pt+\vec p\cdot\vec x$，Hamiltonian 的减除前后含义与正文一致。

| 公式 | 含义 |
| ----- | ---- |
| $\Box\phi-m^2\phi=0$ | 本讲符号约定下的自由实标量场方程 |
| $\omega_p=\sqrt{\vec p^{\,2}+m^2}$ | 正能量色散关系 |
| $\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}[a_{\vec p}e^{ip\cdot x}+a_{\vec p}^{*}e^{-ip\cdot x}]$ | 经典实标量场展开 |
| $p\cdot x=-p^0t+\vec p\cdot\vec x,\quad p^\mu=(\omega_p,\vec p),\quad p^2=p\cdot p$ | 四动量及内积约定 |
| $\int d^4p\,\delta(p^2+m^2)\Theta(p^0)[\cdots]=\int\frac{d^3p}{2\omega_p}[\cdots]_{p^0=\omega_p}$ | 正能量质量壳上的不变积分测度 |
| $\delta(g(x))=\sum_i\frac{\delta(x-x_i)}{\lvert g'(x_i)\rvert},\quad g(x_i)=0$ | 简单零点处的 $\delta$ 函数变换 |
| $[a_{\vec p},a_{\vec k}]=[a_{\vec p}^{\dagger},a_{\vec k}^{\dagger}]=0$ | 同类算符彼此对易 |
| $[a_{\vec p},a_{\vec k}^{\dagger}]=(2\pi)^3\delta^3(\vec p-\vec k)$ | 产生、湮灭算符的非零对易关系 |
| $a_{\vec p}\lvert0\rangle=0\ \Longleftrightarrow\ \langle0\rvert a_{\vec p}^{\dagger}=0$ | 真空条件及其共轭 |
| $a(\vec x)=\int\frac{d^3p}{(2\pi)^3}a_{\vec p}e^{i\vec p\cdot\vec x}$ | 位置空间湮灭算符 |
| $[a(\vec x),a^{\dagger}(\vec y)]=\delta^3(\vec x-\vec y)$ | 位置空间算符对易关系 |
| $\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}[a_{\vec p}e^{ip\cdot x}+a_{\vec p}^{\dagger}e^{-ip\cdot x}]$ | 量子化后的实场算符 |
| $\pi(x)=\dot\phi(x)=-i\int\frac{d^3p}{(2\pi)^3}\sqrt{\frac{\omega_p}{2}}[a_{\vec p}e^{ip\cdot x}-a_{\vec p}^{\dagger}e^{-ip\cdot x}]$ | 正则共轭动量 |
| $\phi(0,\vec x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}[a_{\vec p}+a_{-\vec p}^{\dagger}]e^{i\vec p\cdot\vec x}$ | $t=0$ 的场展开 |
| $\pi(0,\vec x)=-i\int\frac{d^3p}{(2\pi)^3}\sqrt{\frac{\omega_p}{2}}[a_{\vec p}-a_{-\vec p}^{\dagger}]e^{i\vec p\cdot\vec x}$ | $t=0$ 的共轭动量展开 |
| $\hat x=(\hat a+\hat a^{\dagger})/\sqrt{2\omega},\quad\hat p=-i\sqrt{\omega/2}(\hat a-\hat a^{\dagger})$ | 板书中的谐振子类比 |
| $[\phi(0,\vec x),\pi(0,\vec y)]=i\delta^3(\vec x-\vec y)$ | 场与共轭动量的等时对易关系 |
| $[\phi(0,\vec x),\phi(0,\vec y)]=[\pi(0,\vec x),\pi(0,\vec y)]=0$ | 同类场算符的等时对易关系 |
| $H=\int d^3x[\frac12\pi^2+\frac12(\vec\nabla\phi)^2+\frac{m^2}{2}\phi^2]$ | 自由实标量场 Hamiltonian |
| $dH/dt=0\ \Longrightarrow\ H=H(t=0)$ | 在 $t=0$ 计算守恒能量 |
| $\vec\nabla\phi(0,\vec x)=i\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}\vec p[a_{\vec p}+a_{-\vec p}^{\dagger}]e^{i\vec p\cdot\vec x}$ | 场的空间梯度 |
| $\int d^3x\,e^{i(\vec p+\vec k)\cdot\vec x}=(2\pi)^3\delta^3(\vec p+\vec k)$ | Hamiltonian 推导中的空间积分 |
| $H=\frac12\int\frac{d^3p}{(2\pi)^3}\omega_p(a_{\vec p}a_{\vec p}^{\dagger}+a_{\vec p}^{\dagger}a_{\vec p})$ | 抵消同类算符乘积后的 Hamiltonian |
| $\rho_0=\frac12\int\frac{d^3p}{(2\pi)^3}\omega_p,\quad V=\int d^3x=(2\pi)^3\delta^3(\vec0)$ | 零点能密度与体积的形式表示，见检查提醒 |
| $H=\int\frac{d^3p}{(2\pi)^3}\omega_p a_{\vec p}^{\dagger}a_{\vec p}+\rho_0V$ | 减除前的 Hamiltonian |
| $\mathcal H'=\mathcal H+C,\quad H'=H+CV,\quad C=-\rho_0$ | 平移能量零点，见检查提醒 |
| $H\lvert0\rangle=0$ | 减除真空能后的基态能量 |
| $a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}\lvert0\rangle$ | $N$ 粒子态 |
| $H a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}\lvert0\rangle=(\sum_{j=1}^{N}\omega_{p_j})a_{\vec p_1}^{\dagger}\cdots a_{\vec p_N}^{\dagger}\lvert0\rangle$ | 多粒子态是能量本征态，能量为各粒子能量之和 |
