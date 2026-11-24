---
title: "量子场论导论 Lecture 12.1"
date: 2026-11-24
tags:
  - 量子场论导论
  - lecture
  - 维数正则化
  - 自能
  - 重整化方案
  - 反常量纲
  - 重整化群
source: "课堂板书"
---

# Lecture 12.1: φ⁴ 理论的一圈自能、重整化方案与反常量纲

## 本节内容概览

本节先回顾精确传播子、自能和两点函数的反项，再给出维数正则化的规则以及把发散写成 $\varepsilon$ 的 Laurent 级数时要用的两个展开公式。随后在 $\phi^4$ 理论中用维数正则化算出一圈自能，把 $1/\varepsilon$ 发散分离出来，并用 $\delta_m$ 将其抵消。抵消后剩下的有限常数可以任意选取，这就是重整化方案的任意性；板书据此比较了 MS 与 $\overline{\rm MS}$ 两种方案。最后从物理质量与 $\mu$ 无关这一要求出发，推出质量参数随 $\mu$ 的跑动和质量的反常量纲，并开始讨论 $\mu$ 的物理含义。

# 1. 上节回顾

对应图片：1

## 板书整理

![[Picture/12.1/1.jpg]]

板书首先提醒：**周五没有课**（Reminder: no class on Friday）。

**上节内容（Last time）：**

**精确传播子**

$$
\Delta(x-y)\equiv\langle\Omega|T\{\phi(x)\phi(y)\}|\Omega\rangle ,
$$

$$
\widetilde\Delta(p^2)=\frac{-i}{p^2+m^2-i\epsilon-\Sigma(p^2)},
\qquad
i\Sigma(p^2)=\ \xrightarrow{\;p\;}\boxed{\text{1PI}}\xrightarrow{\;p\;}
$$

即 $i\Sigma(p^2)$ 是动量 $p$ 流入、流出的所有 1PI 两点图之和。

**两点函数的重整化。** 拉格朗日量写成（板书在 $Z_\phi$、$Z_m$ 下划线）

$$
\mathcal L=-\frac12 Z_\phi(\partial\phi)^2-\frac{m^2}{2}Z_m\phi^2+Y\phi-V_{\rm int}(\phi),
$$

由此得到双腿反项顶点：

$$
\longrightarrow\quad
\xrightarrow{\;p\;}\!\otimes\!\xrightarrow{\;p\;}
=-i\left(\delta_\phi p^2+\delta_m m^2\right).
$$

板书右侧给出重整化条件：

$$
\langle\vec p\,;t|\phi(x)|\Omega\rangle=e^{-ip\cdot x}.
$$

并写道：反项使关联函数（即期望值）“重整化”，等价于说发散被抵消（Counter-terms "renormalize" correlation functions (= expectation values) $\leftrightarrow$ divergences are canceled）。

## 解释

这里沿用 Lecture 11.2 的记号：$\delta_\phi=Z_\phi-1$，$\delta_m=Z_m-1$。反项顶点本身是 1PI，因此会和圈图一起出现在 $i\Sigma$ 中。本节的工作就是在一个具体的理论里算出圈图部分，再确定反项应取什么值。

# 2. 维数正则化与 Laurent 展开公式

对应图片：2

## 板书整理

![[Picture/12.1/2.jpg]]

**维数正则化（Dimensional regularization）：**

$$
d\equiv4-\varepsilon ,
$$

$$
\int\frac{d^4p}{(2\pi)^4}f(p)\ \longrightarrow\ \int\frac{d^dp}{(2\pi)^d}f(p),
$$

并且（and）

$$
g\ \longrightarrow\ g\,\mu^{\frac{n-2}{2}\varepsilon}.
$$

为了把发散写成 $\varepsilon$ 的 Laurent 级数，板书给出一些有用的公式（To see the divergences in a Laurent series in $\varepsilon$, some useful formulas）：

$$
A^{a\varepsilon}=1+a\varepsilon\log A+\mathcal O(\varepsilon^2),
$$

$$
\Gamma(-n+a\varepsilon)=\frac{(-1)^n}{n!}\left[\frac{1}{a\varepsilon}-\gamma+H_n\right]+\mathcal O(\varepsilon),
\qquad (n=0,1,2,\dots)
$$

其中（where）：

$$
\gamma\simeq0.577\quad\text{（Euler–Mascheroni 常数）},
\qquad
H_n=\sum_{j=1}^{n}\frac1j\quad\text{（调和数，Harmonic number）}.
$$

## 解释

维数正则化把四维积分换成 $d$ 维积分，同时给耦合常数配上 $\mu$ 的幂次，使 $d$ 维中的新耦合 $g$ 仍保持四维时的质量量纲（Lecture 11.2 中已推导）。$\Gamma$ 函数在非正整数处有单极点，第二个公式给出 $\Gamma(-n+a\varepsilon)$ 在极点附近的展开：$1/(a\varepsilon)$ 就是紫外发散在维数正则化中的表现，$-\gamma+H_n$ 是紧随其后的有限部分。第一个公式用来展开 $\mu^\varepsilon$、$m^{-\varepsilon}$ 这类因子。

# 3. φ⁴ 理论的一圈自能

对应图片：3、4、5

## 板书整理

![[Picture/12.1/3.jpg]]

**$\phi^4$ 理论中的自能（Self-energy in $\phi^4$ theory）：**

$$
V_{\rm int}=\frac{\lambda}{4!}\phi^4 ,\qquad n=4 .
$$

（$n=4$ 用蓝笔标出，对应上一节替换 $g\to g\mu^{\frac{n-2}{2}\varepsilon}$ 中的 $n$，此时 $\mu$ 的幂次为 $\varepsilon$。）

到 $\lambda$ 的一阶，自能由两张图组成：动量 $p$ 的直线上附着一个圈（圈内动量 $q$），以及带叉的反项顶点：

$$
i\Sigma(p^2)=
\underbrace{\xrightarrow{\;p\;}\!\overset{q}{\bigcirc}\!\xrightarrow{\;p\;}}_{\text{一圈}}
+\xrightarrow{\;p\;}\!\otimes\!\xrightarrow{\;p\;}
+\mathcal O(\lambda^2).
$$

按费曼规则写出：

$$
=\frac{-i\lambda}{2}\mu^{\varepsilon}\int\frac{d^dq}{(2\pi)^d}\frac{-i}{q^2+m^2-i\epsilon}
-i\left(\delta_\phi p^2+\delta_m m^2\right)+\mathcal O(\lambda^2).
$$

板书用蓝色箭头标注分母中的 $2$ 为**对称因子**（Symmetry factor）。合并两个 $-i$：

$$
=-\frac{\lambda}{2}\mu^{\varepsilon}
\underbrace{\int\frac{d^dq}{(2\pi)^d}\frac{1}{q^2+m^2-i\epsilon}}_{}
-i\left(\delta_\phi p^2+\delta_m m^2\right).
$$

对下括号中的积分作 Wick 转动（板书标注 “(Wick)”）：

$$
\int\frac{d^dq}{(2\pi)^d}\frac{1}{q^2+m^2-i\epsilon}
\overset{\rm (Wick)}{=}
\frac{i}{(4\pi)^{d/2}}\,\frac{1}{(m^2)^{1-d/2}}\,
\frac{\Gamma\!\left(\frac d2\right)\Gamma\!\left(1-\frac d2\right)}{\Gamma\!\left(\frac d2\right)} .
$$

板书用红笔划去分子、分母中的 $\Gamma(d/2)$。

> 此处使用了 Wick 转动 $q^0\to iq_E^0$（给出因子 $i$）以及 $d$ 维欧氏积分公式，板书未展开。

用蓝笔代入 $d=4-\varepsilon$：

$$
=\frac{m^2}{(4\pi)^2}\cdot\frac{(4\pi)^{\varepsilon/2}}{m^{\varepsilon}}\cdot\Gamma\!\left(-1+\frac\varepsilon2\right),
$$

红笔在中间因子上方注明

$$
\frac{(4\pi)^{\varepsilon/2}}{m^{\varepsilon}}=\left(\frac{4\pi}{m^2}\right)^{\varepsilon/2}.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图 3，最后一行代入 $d=4-\varepsilon$ 之后的蓝色表达式。
>
> 板书内容：$\dfrac{i}{(4\pi)^{d/2}}\dfrac{1}{(m^2)^{1-d/2}}\cdots=\dfrac{m^2}{(4\pi)^2}\cdot\dfrac{(4\pi)^{\varepsilon/2}}{m^\varepsilon}\cdot\Gamma\!\left(-1+\dfrac\varepsilon2\right)$
>
> 检查结果：等号右边疑似漏写了左边的因子 $i$。
>
> 说明：代入 $d=4-\varepsilon$ 只改变 $(4\pi)$、$m^2$ 的幂次和 $\Gamma$ 的宗量，不会消去 $i$。图 4 第一行的前置因子 $\dfrac{im^2}{(4\pi)^2}$ 又带上了 $i$，与左边一致。
>
> 注意：以上为检查提示，未修改原板书内容。

![[Picture/12.1/4.jpg]]

图 3 右侧的蓝线连到图 4 左侧，表示下面的展开接着上面的积分结果。利用图 2 的两个公式（$A=4\pi/m^2$、$a=\tfrac12$；$n=1$、$a=\tfrac12$）：

$$
=\frac{im^2}{(4\pi)^2}
\left(1+\frac\varepsilon2\log\!\left(\frac{4\pi}{m^2}\right)+\mathcal O(\varepsilon^2)\right)
\left(-\left(\frac2\varepsilon-\gamma+1\right)+\mathcal O(\varepsilon)\right)
$$

$$
=-\frac{im^2}{(4\pi)^2}\left[\frac2\varepsilon-\gamma+1+\log\frac{4\pi}{m^2}+\mathcal O(\varepsilon)\right].
$$

> 此处使用了 $\Gamma(-1+\tfrac\varepsilon2)=-\left[\tfrac2\varepsilon-\gamma+H_1\right]+\mathcal O(\varepsilon)$，$H_1=1$；两括号相乘时，$\tfrac\varepsilon2\log\tfrac{4\pi}{m^2}$ 与 $\tfrac2\varepsilon$ 相乘给出有限项 $\log\tfrac{4\pi}{m^2}$。

代回自能，并用 $\mu^\varepsilon=1+\varepsilon\log\mu+\mathcal O(\varepsilon^2)$：

$$
\Longrightarrow\quad
i\Sigma(p^2)=\frac{im^2}{(4\pi)^2}\left(1+\varepsilon\log\mu\right)
\left(\frac1\varepsilon-\frac{\gamma-1}{2}+\frac12\log\frac{4\pi}{m^2}\right)
-i\left(\delta_\phi p^2+\delta_m m^2\right)
$$

$$
=\frac{im^2}{(4\pi)^2}\left[\frac1\varepsilon-\frac{\gamma-1}{2}+\log\mu+\frac12\log\frac{4\pi}{m^2}\right]
-i\left(\delta_\phi p^2+\delta_m m^2\right).
$$

红笔把两项改写为对数：

$$
-\frac\gamma2=\log e^{-\gamma/2},
\qquad
\frac12\log\frac{4\pi}{m^2}=\log\frac{\sqrt{4\pi}}{m}.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图 4，第三、四行 $i\Sigma(p^2)$ 的前置因子。
>
> 板书内容：$i\Sigma(p^2)=\dfrac{im^2}{(4\pi)^2}(1+\varepsilon\log\mu)(\cdots)$，下一行同样为 $\dfrac{im^2}{(4\pi)^2}[\cdots]$。
>
> 检查结果：此处疑似漏写耦合常数 $\lambda$。
>
> 说明：图 3 中积分前的系数为 $-\dfrac\lambda2\mu^\varepsilon$，乘以积分结果 $-\dfrac{im^2}{(4\pi)^2}[\cdots]$ 后应得 $\dfrac{i\lambda m^2}{(4\pi)^2}\cdot\dfrac12[\cdots]$。图 5 的前置因子写作 $\dfrac{i\lambda m^2}{(4\pi)^2}$，含有 $\lambda$。
>
> 注意：以上为检查提示，未修改原板书内容。

![[Picture/12.1/5.jpg]]

合并对数项，$-\frac{\gamma-1}{2}=-\frac\gamma2+\frac12$：

$$
=\frac{i\lambda m^2}{(4\pi)^2}\left[\frac1\varepsilon+\log\left(\sqrt{4\pi}\,e^{-\gamma/2}\frac{\mu}{m}\right)+\frac12\right]
-i\left(\delta_\phi p^2+\delta_m m^2\right)
$$

$$
=\frac{i\lambda m^2}{(4\pi)^2}\left[\frac1\varepsilon+\log\left(\frac{\tilde\mu}{m}\right)+\frac12\right]
-i\left(\delta_\phi p^2+\delta_m m^2\right)+\mathcal O(\lambda^2),
$$

其中（框出）

$$
\boxed{\tilde\mu\equiv\sqrt{4\pi}\,e^{-\gamma/2}\mu .}
$$

## 解释

一圈图是“蝌蚪图”：一条内线从同一个 $\phi^4$ 顶点出发又回到该顶点，交换圈的两端不改变图，故对称因子为 $2$。圈积分不依赖外动量 $p$，所以圈图对 $\Sigma$ 的贡献是常数。$\varepsilon\to0$ 时 $\Gamma(-1+\varepsilon/2)$ 的极点给出 $1/\varepsilon$ 发散；$\mu^\varepsilon$ 和 $(4\pi/m^2)^{\varepsilon/2}$ 乘上这个极点后留下有限的对数项。$\log\mu$ 与 $\log(1/m)$ 合成无量纲的 $\log(\mu/m)$，$\tilde\mu$ 则把常数 $\sqrt{4\pi}e^{-\gamma/2}$ 吸收进对数的宗量里。

# 4. 抵消发散与重整化方案的任意性

对应图片：5、6

## 板书整理

图 5 末尾写道：现在可以通过适当选择 $\delta_\phi,\delta_m$ 来抵消发散 $\frac1\varepsilon$（We can now cancel the divergence $\frac1\varepsilon$ with a suitable choice of $\delta_\phi,\delta_m$）：

![[Picture/12.1/6.jpg]]

$$
\longrightarrow\quad
\boxed{
\begin{aligned}
\delta_\phi&=0+(\text{finite})+\mathcal O(\lambda^2)\\
\delta_m&=\frac{\lambda}{16\pi^2\varepsilon}+(\text{finite})+\mathcal O(\lambda^2)
\end{aligned}}
$$

橙色箭头指向 “(finite)”：**与 $\varepsilon$ 无关的任意常数**（arbitrary constants independent of $\varepsilon$）。

抵消发散后还留下一些任意常数，这一事实称为**“重整化方案”任意性**（"renormalization scheme" ambiguity）。这不构成问题，因为反项不是可观测量（not a problem because counter-terms are not observable）。

## 解释

$\delta_m$ 的发散部分由 $\dfrac{i\lambda m^2}{16\pi^2}\cdot\dfrac1\varepsilon-i\delta_m m^2=0$ 得到。圈图贡献与 $p^2$ 无关，所以在这一阶 $\delta_\phi$ 不需要发散部分。只要求消去 $1/\varepsilon$，并不能确定 $\delta_\phi,\delta_m$ 中的有限部分；不同的取法就是不同的重整化方案。

# 5. MS 与 $\overline{\rm MS}$ 方案

对应图片：7、8、9

## 板书整理

![[Picture/12.1/7.jpg]]

**最小减除（Minimal subtraction，MS）：** 选择有限项 $=0$（Choose finite terms $=0$）。

$$
\longrightarrow\quad
\boxed{
\begin{aligned}
\delta_\phi^{\rm (MS)}&=0+\mathcal O(\lambda^2)\\
\delta_m^{\rm (MS)}&=\frac{\lambda}{16\pi^2}\frac1\varepsilon+\mathcal O(\lambda^2)
\end{aligned}}
$$

**修正的最小减除（Modified minimal subtraction，$\overline{\rm MS}$）：** 选择有限项，使其抵消结果中任何正比于 $\log\sqrt{4\pi}\,e^{-\gamma/2}$ 的项（Choose finite terms to cancel any $\propto\log\sqrt{4\pi}\,e^{-\gamma/2}$ in the result）。

![[Picture/12.1/8.jpg]]

$$
\longrightarrow\quad
\boxed{
\begin{aligned}
\delta_\phi^{(\overline{\rm MS})}&=0+\mathcal O(\lambda^2)\\
\delta_m^{(\overline{\rm MS})}&=\frac{\lambda}{16\pi^2}\left[\frac1\varepsilon+\log\left(\sqrt{4\pi}\,e^{-\gamma/2}\right)\right]+\mathcal O(\lambda^2)
\end{aligned}}
$$

于是得到“重整化后的”自能（So we get the "renormalized" self-energy）：

$$
\Sigma^{\rm (MS)}(p^2)=\frac{\lambda m^2}{(4\pi)^2}\left[\log\frac{\tilde\mu}{m}+\frac12\right]+\mathcal O(\lambda^2),
$$

$$
\Sigma^{(\overline{\rm MS})}(p^2)=\frac{\lambda m^2}{(4\pi)^2}\left[\log\frac{\mu}{m}+\frac12\right]+\mathcal O(\lambda^2).
$$

![[Picture/12.1/9.jpg]]

即 MS 与 $\overline{\rm MS}$ 的结果等价，区别仅在于选用 $\mu$ 还是 $\tilde\mu$（i.e. the results in MS and $\overline{\rm MS}$ are equivalent, the difference being only in the choice of $\mu$ vs. $\tilde\mu$）。

## 解释

把 $\delta_m$ 代回图 5 的结果：MS 只减去 $1/\varepsilon$，$\log(\tilde\mu/m)$ 原样留下；$\overline{\rm MS}$ 额外减去 $\log(\sqrt{4\pi}e^{-\gamma/2})$，由 $\log(\tilde\mu/m)=\log(\sqrt{4\pi}e^{-\gamma/2})+\log(\mu/m)$，剩下 $\log(\mu/m)$。两个结果形式相同，把一个方案中的 $\tilde\mu$ 换成另一个方案中的 $\mu$ 即可互相转换。这里已取 $\varepsilon\to0$，丢掉了 $\mathcal O(\varepsilon)$ 项。

# 6. 重整化条件与物理质量

对应图片：9

## 板书整理

**重整化条件（Renormalization conditions）：**

$$
\Sigma'(-m_{\rm ph}^2)=0\ \longrightarrow\ \text{ok}
\qquad(\text{we found }\Sigma(p^2)=\text{const.})
$$

$$
\Sigma(-m_{\rm ph}^2)=m^2-m_{\rm ph}^2
\ \xrightarrow{\ \overline{\rm MS}\ }\
\boxed{m_{\rm ph}^2=m^2-\frac{\lambda m^2}{(4\pi)^2}\left[\log\frac{\mu}{m}+\frac12\right]+\mathcal O(\lambda^2)}
$$

## 解释

两个条件来自 Lecture 11.2：极点位置给出 $m^2=m_{\rm ph}^2+\Sigma(-m_{\rm ph}^2)$，留数条件给出 $\Sigma'(-m_{\rm ph}^2)=0$。一圈自能与 $p^2$ 无关，导数为零，留数条件自动满足。在 $\overline{\rm MS}$ 中反项已经由方案确定，极点条件就用来从拉格朗日量参数 $m$ 和 $\mu$ 算出物理质量 $m_{\rm ph}$。

# 7. 反常量纲与重整化群跑动

对应图片：9、10、11、12

## 板书整理

图 9 下方开始新的一部分：**反常量纲（Anomalous dimension）**。

重整化标度 $\mu$ 不是物理的，所以**可观测量**（板书加下划线）

![[Picture/12.1/10.jpg]]

不应依赖于 $\mu$。然而 $m$ 和 $\lambda$ 也不是物理的（更一般地，拉格朗日量中的任何参数都是如此）：它们并不直接定义可观测量。所以 $m_{\rm ph}^2$ 确实与 $\mu$ 无关，因为 **$m$ 和 $\lambda$ 依赖于 $\mu$**（板书加下划线）$\longrightarrow$ **“重整化群跑动”**（"renormalization group running"）。

一般地，可以把这种依赖写成（In general, we can express this dependence as）：

$$
\frac{dm}{d\log\mu}=m\left[c\lambda+\mathcal O(\lambda^2)\right],
\qquad
\frac{d\lambda}{d\log\mu}=\lambda\left[c'\lambda+\mathcal O(\lambda^2)\right],
$$

红笔注明 $c$、$c'$ 为某些常数（some constants），并在右侧写下两条说明：

- note 1：由量纲分析（by dimensional analysis），$\dfrac{dm}{d\log\mu}\propto m$。
- note 2：跑动只在相互作用理论中出现（running only happens in the interacting theory），$\dfrac{dm}{d\log\mu}\propto\lambda+\dots$

![[Picture/12.1/11.jpg]]

必须有（We must have）：

$$
\boxed{\frac{dm_{\rm ph}}{d\log\mu}=0 .}
$$

板书右上角写出 $\log(1+x)=x+\mathcal O(x^2)$。考虑（Consider）：

$$
\log m_{\rm ph}^2=2\log m_{\rm ph}
=\log\left[m^2\left(1-\frac{\lambda}{16\pi^2}\left(\log\frac\mu m+\frac12\right)\right)\right]
$$

$$
=2\log m-\frac{\lambda}{16\pi^2}\left(\log\frac\mu m+\frac12\right)+\mathcal O(\lambda^2).
$$

两边作用 $\dfrac{d(\ \ )}{d\log\mu}$：

$$
0=2\frac{d\log m}{d\log\mu}
-\frac{1}{16\pi^2}\underbrace{\frac{d\lambda}{d\log\mu}}_{\mathcal O(\lambda^2)}\left(\log\frac\mu m+\frac12\right)
-\frac{\lambda}{16\pi^2}+\mathcal O(\lambda^2).
$$

（$\mathcal O(\lambda^2)$ 用蓝笔标在 $d\lambda/d\log\mu$ 下方，来自上面的 $d\lambda/d\log\mu=\lambda[c'\lambda+\cdots]$。）

> 此处使用了 $\dfrac{d}{d\log\mu}\log\dfrac\mu m=1-\dfrac{d\log m}{d\log\mu}$。其中 $-\dfrac{d\log m}{d\log\mu}$ 一项乘以 $\lambda$ 后为 $\mathcal O(\lambda^2)$（因为 $d\log m/d\log\mu=\mathcal O(\lambda)$），并入 $\mathcal O(\lambda^2)$。

![[Picture/12.1/12.jpg]]

$$
\longrightarrow\quad
\boxed{\frac{d\log m}{d\log\mu}=\frac{\lambda}{32\pi^2}+\mathcal O(\lambda^2)\equiv\gamma_m(\lambda)}
$$

红笔箭头指向 $\gamma_m(\lambda)$：**“质量的反常量纲”**（"anomalous dimension of the mass"），向下的箭头注明它一般也可能依赖于 $\mu$（generally may also depend on $\mu$）。

在这种情况下，跑动可以显式求解（In this case the running can be solved explicitly）：

$$
\frac{m}{m_0}=\left(\frac{\mu}{\mu_0}\right)^{\gamma_m},
$$

红笔标注 $m_0$、$\mu_0$ 为**积分常数**（integration constants）。

> 此处将 $\gamma_m$ 视为常数后积分 $d\log m=\gamma_m\,d\log\mu$。由于 $d\lambda/d\log\mu=\mathcal O(\lambda^2)$，在 $\mathcal O(\lambda)$ 精度下 $\lambda$ 的跑动可以忽略。

## 解释

$m_{\rm ph}$ 是可观测量，必须与 $\mu$ 无关；而 $m_{\rm ph}^2$ 的表达式里显含 $\log\mu$，这一依赖只能由 $m$（以及 $\lambda$）随 $\mu$ 的变化来抵消。在一阶精度下，对 $\log\mu$ 求导得到 $2\gamma_m=\lambda/(16\pi^2)$，即 $\gamma_m=\lambda/(32\pi^2)$。$\gamma_m$ 通过 $\lambda(\mu)$ 间接依赖于 $\mu$，这就是红字“一般也可能依赖于 $\mu$”的含义。把 $\gamma_m$ 当作常数时，解是幂律；$m_0$ 是质量在参考标度 $\mu_0$ 处的值，两者合起来只相当于一个积分常数。

# 8. μ 的物理诠释

对应图片：13

## 板书整理

![[Picture/12.1/13.jpg]]

**把 $\mu$ 诠释为实验的典型能量**（Interpretation of $\mu$ as the typical energy of the experiment）。

当我们用微扰论计算散射振幅时（When we calculate scattering amplitudes in perturbation theory）……

（板书至此结束，这句话在本节没有写完。）

## 解释

本节只给出了这一部分的标题和开头。前面的结果已经显示，圈修正中出现 $\log(\mu/m)$ 这样的对数；这一部分接下来讨论 $\mu$ 应当如何选取。

# 本节知识结构

回顾：精确传播子、自能、两点函数的反项  
↓  
维数正则化 $d=4-\varepsilon$，$g\to g\mu^{\frac{n-2}{2}\varepsilon}$，$A^{a\varepsilon}$ 与 $\Gamma(-n+a\varepsilon)$ 的展开  
↓  
$\phi^4$ 理论一圈自能：对称因子、Wick 转动、$\Gamma(-1+\varepsilon/2)$ 给出 $1/\varepsilon$ 极点  
↓  
用 $\delta_m$ 抵消 $1/\varepsilon$，有限部分任意：重整化方案任意性  
↓  
MS 与 $\overline{\rm MS}$：两者只差 $\mu\leftrightarrow\tilde\mu$  
↓  
由极点条件得到 $\overline{\rm MS}$ 中的物理质量 $m_{\rm ph}^2$  
↓  
$m_{\rm ph}$ 与 $\mu$ 无关 $\Rightarrow$ $m,\lambda$ 随 $\mu$ 跑动，质量反常量纲 $\gamma_m=\lambda/(32\pi^2)$  
↓  
将 $\mu$ 诠释为实验的典型能量（未完）

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $\widetilde\Delta(p^2)=-i/[p^2+m^2-i\epsilon-\Sigma(p^2)]$ | 精确传播子（回顾） |
| $-i(\delta_\phi p^2+\delta_m m^2)$ | 双腿反项顶点（回顾） |
| $d=4-\varepsilon,\quad g\to g\mu^{\frac{n-2}{2}\varepsilon}$ | 维数正则化规则 |
| $A^{a\varepsilon}=1+a\varepsilon\log A+\mathcal O(\varepsilon^2)$ | 幂因子的 $\varepsilon$ 展开 |
| $\Gamma(-n+a\varepsilon)=\frac{(-1)^n}{n!}\left[\frac{1}{a\varepsilon}-\gamma+H_n\right]+\mathcal O(\varepsilon)$ | $\Gamma$ 函数在极点附近的展开 |
| $H_n=\sum_{j=1}^n 1/j,\quad\gamma\simeq0.577$ | 调和数与 Euler–Mascheroni 常数 |
| $\int\frac{d^dq}{(2\pi)^d}\frac{1}{q^2+m^2-i\epsilon}=\frac{i}{(4\pi)^{d/2}}(m^2)^{d/2-1}\Gamma(1-\frac d2)$ | Wick 转动后的一圈积分 |
| $i\Sigma=\frac{i\lambda m^2}{(4\pi)^2}\left[\frac1\varepsilon+\log\frac{\tilde\mu}{m}+\frac12\right]-i(\delta_\phi p^2+\delta_m m^2)+\mathcal O(\lambda^2)$ | $\phi^4$ 理论的一圈自能 |
| $\tilde\mu\equiv\sqrt{4\pi}\,e^{-\gamma/2}\mu$ | 吸收常数后的标度 |
| $\delta_\phi=0+(\text{finite}),\quad\delta_m=\frac{\lambda}{16\pi^2\varepsilon}+(\text{finite})$ | 抵消发散所需的反项 |
| $\delta_m^{\rm (MS)}=\frac{\lambda}{16\pi^2}\frac1\varepsilon$ | MS 方案 |
| $\delta_m^{(\overline{\rm MS})}=\frac{\lambda}{16\pi^2}\left[\frac1\varepsilon+\log(\sqrt{4\pi}e^{-\gamma/2})\right]$ | $\overline{\rm MS}$ 方案 |
| $\Sigma^{\rm (MS)}=\frac{\lambda m^2}{(4\pi)^2}\left[\log\frac{\tilde\mu}{m}+\frac12\right],\quad\Sigma^{(\overline{\rm MS})}=\frac{\lambda m^2}{(4\pi)^2}\left[\log\frac{\mu}{m}+\frac12\right]$ | 重整化后的自能 |
| $m_{\rm ph}^2=m^2-\frac{\lambda m^2}{(4\pi)^2}\left[\log\frac\mu m+\frac12\right]+\mathcal O(\lambda^2)$ | $\overline{\rm MS}$ 中的物理质量 |
| $\frac{dm}{d\log\mu}=m[c\lambda+\cdots],\quad\frac{d\lambda}{d\log\mu}=\lambda[c'\lambda+\cdots]$ | 参数跑动的一般形式 |
| $\frac{dm_{\rm ph}}{d\log\mu}=0$ | 可观测量与 $\mu$ 无关 |
| $\gamma_m(\lambda)\equiv\frac{d\log m}{d\log\mu}=\frac{\lambda}{32\pi^2}+\mathcal O(\lambda^2)$ | 质量的反常量纲 |
| $m/m_0=(\mu/\mu_0)^{\gamma_m}$ | $\gamma_m$ 视为常数时的跑动解 |

# 板书完整性与数学检查

图 1 至图 13 编号连续，均在对应段落附有原图；图 3 右侧蓝线与图 4 左侧蓝线的衔接已按同一推导连续整理。图 3 代入 $d=4-\varepsilon$ 后疑似漏写因子 $i$，图 4 第三、四行疑似漏写 $\lambda$，均已在原式旁标注。图 11 中被并入 $\mathcal O(\lambda^2)$ 的项和图 12 显式解所用的近似已用注释说明。图 13 的板书在句中结束，按原样保留。
