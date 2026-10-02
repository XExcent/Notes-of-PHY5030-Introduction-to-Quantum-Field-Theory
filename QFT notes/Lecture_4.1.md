---
title: "量子场论导论 Lecture 4.1"
date: 2026-10-02
tags:
  - 量子场论导论
  - lecture
  - Noether定理
  - 能动张量
  - Yukawa势
  - Klein-Gordon场
  - 场量子化
source: "课堂板书"
---

# Lecture 4.1：能动张量、外源与 Klein–Gordon 场

## 本节内容概览

本节从 Hamiltonian 与 Noether 定理出发，整理时空平移对应的能动张量，并说明其 $00$ 分量和 $0i$ 分量分别给出能量密度与动量密度。随后引入外部源，以电动力学为例说明源项的作用，再计算带静态点源的标量场解，得到 Yukawa 势及其无质量极限的 Coulomb 势。最后回顾 Klein–Gordon 方程的平面波展开，并说明实标量场的系数约束。

本笔记保留板书的符号约定。板书把平移 Noether 流的相反数记作 $T^\mu{}_{\nu}$，因此

$$
J_{a,\nu}^{\mu}=-T^\mu{}_{\nu}.
$$

## 1. 连续对称性与时空平移

### 1.1 Noether 定理回顾（图 1）

![[4.1/1.jpg]]

场的无穷小变换写作

$$
\phi(x)\longrightarrow \phi'(x)
=\phi(x)+\epsilon\,\Delta_\epsilon[\phi].
$$

若拉格朗日量只改变一个全导数，

$$
\mathcal L\longrightarrow \mathcal L'
=\mathcal L+\epsilon\,\partial_\mu K_\epsilon^\mu,
$$

则 Noether 流为

$$
J_\epsilon^\mu
=\frac{\partial\mathcal L}
 {\partial(\partial_\mu\phi)}\,\Delta_\epsilon[\phi]
-K_\epsilon^\mu.
$$

作用量为

$$
S=\int d^4x\,\mathcal L.
$$

时空平移为

$$
 x^\mu\longrightarrow x'^\mu=x^\mu+a^\mu,
 \qquad \mu\in\{0,1,2,3\},
$$

因此有四个平移参数。对标量场，固定同一个时空点的场变换为

$$
\phi'(x)=\phi(x+a)
=\phi(x)+a^\mu\partial_\mu\phi(x),
$$

所以

$$
\Delta_{a,\mu}=\partial_\mu\phi.
$$

要区分同一点比较和坐标随之变换的写法：前者是 $\phi'(x)=\phi(x+a)$，后者满足标量场关系 $\phi'(x')=\phi(x)$。板书还假定

$$
 d^4x'=d^4x.
$$

### 1.2 能动张量（图 2–3）

![[4.1/2.jpg]]
![[4.1/3.jpg]]

Noether 定理给出四个平移守恒流：

$$
\partial_\mu J_{a,\nu}^{\mu}=0
\quad\Longrightarrow\quad
\partial_\mu T^\mu{}_{\nu}=0.
$$

这里 $a^\mu$ 上的指标是标记四个平移对称性的 label。由

$$
 a^\mu\partial_\mu\mathcal L
 =a^\nu\partial_\mu\bigl(\mathcal L\,\delta^\mu{}_{\nu}\bigr)
$$

可识别

$$
K_{a,\nu}^{\mu}=\mathcal L\,\delta^\mu{}_{\nu}.
$$

直接代入 Noether 流定义得到

$$
J_{a,\nu}^{\mu}
=\frac{\partial\mathcal L}
 {\partial(\partial_\mu\phi)}\,\partial_\nu\phi
-\mathcal L\,\delta^\mu{}_{\nu}.
$$

本节板书将其相反数定义为能动张量：

$$
\boxed{
T^\mu{}_{\nu}
=\mathcal L\,\delta^\mu{}_{\nu}
-\frac{\partial\mathcal L}
 {\partial(\partial_\mu\phi)}\,\partial_\nu\phi
}.
$$

因而 $J_{a,\nu}^{\mu}=-T^\mu{}_{\nu}$，但守恒方程不变。

### 1.3 Noether 荷、能量与动量（图 2、4–5）

![[4.1/4.jpg]]
![[4.1/5.jpg]]

Noether 荷定义为

$$
Q_\epsilon=\int d^3x\,J_\epsilon^0.
$$

时间平移（$\nu=0$）给出

$$
\begin{aligned}
\int d^3x\,J_{a,0}^0
&=-\int d^3x\,T^0{}_0\\
&=\int d^3x\,T^{00}
\equiv E.
\end{aligned}
$$

空间平移（$\nu=i$，$i=1,2,3$）给出

$$
\int d^3x\,J_{a,i}^0
=-\int d^3x\,T^0{}_i
\equiv-P_i,
$$

等价地

$$
\boxed{P^i=\int d^3x\,T^{0i}}.
$$

能动张量的分量解释为

$$
T^{00}\longrightarrow \text{energy density},
\qquad
T^{0i}\longrightarrow \text{momentum density in direction }i.
$$

对标量场，正则动量为

$$
\pi=\frac{\partial\mathcal L}{\partial\dot\phi}.
$$

由本节的能动张量约定，

$$
\begin{aligned}
T^{00}
&=-T^0{}_0\\
&=\frac{\partial\mathcal L}{\partial(\partial_0\phi)}\,\partial_0\phi-\mathcal L\\
&=\pi\dot\phi-\mathcal L\\
&\equiv\mathcal H.
\end{aligned}
$$

所以

$$
E=\int d^3x\,T^{00}
=\int d^3x\,\mathcal H
\equiv H.
$$

板书还给出动量的空间表达式（exercise）：

$$
\boxed{\vec P=-\int d^3x\,\pi\,\vec\nabla\phi}.
$$

其中 $E=H$ 是在将场取为满足运动方程的物理构型（on-shell）后使用的等式。

## 2. 外部源与电动力学

### 2.1 外部源耦合（图 4）

![[4.1/4.jpg]]

外部源（external source）代表独立于所研究场的物理作用。板书写作

$$
\mathcal L_{\mathrm{tot}}
=\mathcal L[\phi]+\phi J(x),
$$

其中 $J(x)$ 是外部给定的源。

### 2.2 电动力学例子（图 6）

![[4.1/6.jpg]]
![[4.1/10.jpg]]

带外部电流的电动力学拉格朗日量为

$$
\mathcal L_{\mathrm{tot}}
=-\frac14F^{\mu\nu}F_{\mu\nu}+A_\mu J^\mu.
$$

Euler–Lagrange 方程为

$$
\boxed{\partial_\mu F^{\mu\nu}+J^\nu=0}.
$$

板书使用

$$
F^{0i}=E^i,
\qquad
F^{ij}=\epsilon^{ij}{}_{k}B^k,
$$

以及

$$
J^0=\rho,
\qquad
\vec J=\text{electric 3-current}.
$$

对 $\nu=0$，由于 $F^{i0}=-E^i$，

$$
\partial_iF^{i0}+J^0=0
\quad\Longrightarrow\quad
-\vec\nabla\cdot\vec E+\rho=0,
$$

即

$$
\boxed{\vec\nabla\cdot\vec E=\rho}.
$$

对 $\nu=j$，

$$
\partial_0F^{0j}+\partial_iF^{ij}+J^j=0.
$$

其中

$$
\partial_0F^{0j}=\frac{\partial E^j}{\partial t},
\qquad
\partial_iF^{ij}
=\epsilon^{ij}{}_{k}\partial_iB^k
=-\bigl(\vec\nabla\times\vec B\bigr)^j.
$$

因此

$$
\boxed{
\frac{\partial\vec E}{\partial t}
-\vec\nabla\times\vec B
+\vec J=0
}.
$$

## 3. 静态点源与 Yukawa 势

### 3.1 方程与 Fourier 变换（图 7–8）

![[4.1/7.jpg]]

考虑

$$
\mathcal L_{\mathrm{tot}}
=-\frac12(\partial\phi)^2
-\frac{m^2}{2}\phi^2
+\phi J,
$$

其中静态点源为

$$
J(x)=\alpha\,\delta^{(3)}(\vec x),
$$

$\alpha$ 为常数。Euler–Lagrange 方程为

$$
\boxed{\Box\phi-m^2\phi=-\alpha\,\delta^{(3)}(\vec x)}.
$$

寻找在 $|\vec x|\to\infty$ 足够快衰减的静态解。采用

$$
\phi(\vec x)
=\int\frac{d^3k}{(2\pi)^3}\,
\phi_{\vec k}e^{i\vec k\cdot\vec x},
\qquad
\phi_{\vec k}
=\int d^3x\,\phi(\vec x)e^{-i\vec k\cdot\vec x}.
$$

板书回顾

$$
\delta^{(3)}(\vec x)
=\int\frac{d^3k}{(2\pi)^3}e^{i\vec k\cdot\vec x},
\qquad
\delta^{(4)}(x)
=\int\frac{d^4k}{(2\pi)^4}e^{ik\cdot x}.
$$

静态时

$$
\Box=-\partial_t^2+\vec\nabla^{\,2}
\longrightarrow\vec\nabla^{\,2}.
$$

对每个 Fourier 模，

$$
-|\vec k|^2\phi_{\vec k}-m^2\phi_{\vec k}=-\alpha,
$$

所以

$$
\boxed{\phi_{\vec k}=\frac{\alpha}{|\vec k|^2+m^2}}.
$$

### 3.2 球对称积分（图 8–9）

![[4.1/8.jpg]]

取 $\vec x=(0,0,r)$，并令

$$
\vec k=k(\sin\theta\cos\varphi,
\sin\theta\sin\varphi,\cos\theta),
\qquad
\vec k\cdot\vec x=kr\cos\theta.
$$

于是

$$
\begin{aligned}
\phi(r)
&=\alpha\frac{2\pi}{(2\pi)^3}
\int_0^\infty k^2dk
\int_0^\pi\sin\theta d\theta\,
\frac{e^{ikr\cos\theta}}{k^2+m^2}\\
&=\frac{\alpha}{4\pi^2}
\int_0^\infty dk\,\frac{k^2}{k^2+m^2}
\int_{-1}^{1}d(\cos\theta)e^{ikr\cos\theta}.
\end{aligned}
$$

角积分为

$$
\int_{-1}^{1}du\,e^{ikru}
=\frac{e^{ikr}-e^{-ikr}}{ikr}.
$$

因此

$$
\phi(r)
=-\frac{i\alpha}{4\pi^2r}
\int_0^\infty dk\,
\frac{k}{k^2+m^2}(e^{ikr}-e^{-ikr}).
$$

对第二项作 $k\to-k$，得到

$$
\phi(r)
=-\frac{i\alpha}{4\pi^2r}
\int_{-\infty}^{\infty}dk\,
\frac{k e^{ikr}}{k^2+m^2}.
$$

### 3.3 留数计算（图 9、14）

![[4.1/9.jpg]]
![[4.1/14.jpg]]

当 $r>0$ 时在上半平面闭合路径，因为 $e^{ikr}$ 在上半平面无穷远处衰减。极点为

$$
 k=\pm im,
$$

上半平面内只有 $k=im$。留数为

$$
\begin{aligned}
\mathop{\mathrm{Res}}_{k=im}
\frac{k e^{ikr}}{k^2+m^2}
&=\left.\frac{k e^{ikr}}{k+im}\right|_{k=im}\\
&=\frac{im e^{-mr}}{2im}\\
&=\frac12e^{-mr}.
\end{aligned}
$$

由留数定理

$$
\int_{-\infty}^{\infty}dk\,
\frac{k e^{ikr}}{k^2+m^2}
=2\pi i\left(\frac12e^{-mr}\right)
=\pi i e^{-mr}.
$$

代回即得 Yukawa 势：

$$
\boxed{\phi(r)=\frac{\alpha}{4\pi}\frac{e^{-mr}}{r}}.
$$

当 $m=0$ 时，得到 Coulomb 势：

$$
\boxed{\left.\phi(r)\right|_{m=0}
=\frac{\alpha}{4\pi}\frac1r}.
$$

## 4. Klein–Gordon 场的平面波展开

### 4.1 模方程与色散关系（图 12–13）

![[4.1/12.jpg]]
![[4.1/13.jpg]]

实标量场满足

$$
\Box\phi-m^2\phi=0,
\qquad
\Box=-\partial_t^2+\vec\nabla^{\,2}.
$$

做三维 Fourier 展开：

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3}
\phi_{\vec p}(t)e^{i\vec p\cdot\vec x}.
$$

代入得到

$$
-\ddot\phi_{\vec p}
-|\vec p|^2\phi_{\vec p}
-m^2\phi_{\vec p}=0.
$$

定义

$$
\omega_{\vec p}=\sqrt{|\vec p|^2+m^2},
$$

则

$$
\phi_{\vec p}(t)
=A_{\vec p}e^{-i\omega_{\vec p}t}
+B_{\vec p}e^{+i\omega_{\vec p}t},
$$

其中 $A_{\vec p}$、$B_{\vec p}$ 是积分常数。于是一般解为

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3}
\left[
A_{\vec p}e^{-i\omega_{\vec p}t+i\vec p\cdot\vec x}
+B_{\vec p}e^{+i\omega_{\vec p}t+i\vec p\cdot\vec x}
\right].
$$

### 4.2 标准模归一化（图 11–13）

![[4.1/11.jpg]]

板书将归一化因子抽出，定义

$$
A_{\vec p}
\equiv\frac{a_{\vec p}}{\sqrt{2\omega_{\vec p}}},
\qquad
B_{\vec p}
\equiv\frac{b_{\vec p}}{\sqrt{2\omega_{\vec p}}}.
$$

于是

$$
\boxed{
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_{\vec p}}}
\left[
 a_{\vec p}e^{-i\omega_{\vec p}t+i\vec p\cdot\vec x}
+b_{\vec p}e^{+i\omega_{\vec p}t+i\vec p\cdot\vec x}
\right].
}
$$

在这一步 $a_{\vec p}$、$b_{\vec p}$ 仍是经典解的模系数。

### 4.3 实标量场条件（图 15–17）

![[4.1/15.jpg]]
![[4.1/16.jpg]]
![[4.1/17.jpg]]

要求实标量场满足

$$
\phi^*(x)=\phi(x).
$$

对展开式取复共轭，并作 $\vec p\to-\vec p$。积分测度不变，例如

$$
\int_{-\infty}^{\infty}dp_x
=\int_{\infty}^{-\infty}(-dp_x)
=\int_{-\infty}^{\infty}dp_x.
$$

比较正、负频率项后得到

$$
\boxed{
 b^*_{-\vec p}=a_{\vec p},
 \qquad
 a^*_{-\vec p}=b_{\vec p}
}.
$$

两式彼此等价。因此实标量场可写成

$$
\boxed{
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_{\vec p}}}
\left[
 a_{\vec p}e^{-i\omega_{\vec p}t+i\vec p\cdot\vec x}
+a^*_{-\vec p}e^{+i\omega_{\vec p}t+i\vec p\cdot\vec x}
\right].
}
$$

这里仍是经典场的 Fourier 模展开；板书在这组图片中尚未继续写出量子化后的算符对易关系。

## 本节知识结构

时空平移
→ Noether 流与能动张量
→ 能量、动量及其密度
→ 外部源耦合
→ 电动力学中的源项与 Maxwell 方程
→ 静态点源的 Klein–Gordon 方程
→ Fourier 积分与留数定理
→ Yukawa 势及 Coulomb 极限
→ Klein–Gordon 平面波展开
→ 实标量场的系数约束

## 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $J_\epsilon^\mu=\dfrac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\Delta_\epsilon-K_\epsilon^\mu$ | Noether 流 |
| $T^\mu{}_{\nu}=\mathcal L\delta^\mu{}_{\nu}-\dfrac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\partial_\nu\phi$ | 本节板书采用的能动张量约定 |
| $\partial_\mu T^\mu{}_{\nu}=0$ | 能动张量守恒 |
| $E=\int d^3x\,T^{00}=\int d^3x\,\mathcal H$ | 总能量 |
| $P^i=\int d^3x\,T^{0i}$ | 总动量 |
| $\mathcal L_{\mathrm{tot}}=\mathcal L[\phi]+\phi J(x)$ | 外部源耦合 |
| $\partial_\mu F^{\mu\nu}+J^\nu=0$ | 带源电动力学方程 |
| $\phi_{\vec k}=\alpha/(|\vec k|^2+m^2)$ | 静态点源的 Fourier 模 |
| $\phi(r)=\dfrac{\alpha}{4\pi}\dfrac{e^{-mr}}{r}$ | Yukawa 势 |
| $\phi(r)\big|_{m=0}=\dfrac{\alpha}{4\pi r}$ | Coulomb 极限 |
| $\omega_{\vec p}=\sqrt{|\vec p|^2+m^2}$ | Klein–Gordon 色散关系 |
| $b^*_{-\vec p}=a_{\vec p}$ | 实标量场的 Fourier 系数约束 |

## 板书核对说明

- 本节的 $T^\mu{}_{\nu}$ 与一些教材常用的 canonical energy-momentum tensor 相差一个负号；本文显式保留板书约定，并写出 $J=-T$。
- Yukawa 势的留数计算取 $r>0$ 并在上半平面闭合；$m=0$ 的 Coulomb 结果由最终表达式取极限得到。
- 图 11–17 中 $a_{\vec p}$、$b_{\vec p}$ 先作为经典模系数出现；实场条件才要求 $b_{\vec p}=a^*_{-\vec p}$。板书没有在本组图片中继续给出量子算符化和对易关系。






