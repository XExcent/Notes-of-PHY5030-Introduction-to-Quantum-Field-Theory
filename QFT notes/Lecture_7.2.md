---
title: "量子场论导论 Lecture 7.2"
date: 2026-10-24
tags:
  - 量子场论导论
  - lecture
  - 二体散射
  - 散射阈值
  - 粒子衰变
  - LSZ约化公式
source: "课堂板书"
---

# Lecture 7.2: 二体散射截面、粒子衰变与 LSZ 约化公式引入

## 本节内容概览

本节先回顾散射概率、散射振幅与总截面的关系，再在质心系中逐步完成二体末态的相空间积分。随后讨论散射阈值、弹性散射以及入射和出射动量对质心能量的依赖，并给出重靶非相对论散射的近似。接着将跃迁概率公式用于单粒子衰变，定义微分衰变率和总衰变率。最后引入 LSZ 约化公式这一主题，说明相互作用真空、含时产生与湮灭算符，以及有限时刻“单粒子态”的局限。

<!-- date 为整理日期；原板书未标明授课日期。正文严格按照 Picture/7.2/1.png 至 13.png 排列。疑似错误保留原式，并在对应位置添加检查注释；原图使用含目录的 Obsidian 引用，以区分不同课次的同名图片。 -->

---

# 1. 上节回顾：散射截面与跃迁概率

对应图片：

- 1

## 板书整理

![[Picture/7.2/1.png]]

课堂提醒：作业（Reminder: HW）。

上节内容：散射（Scattering）。微分截面写为

$$
\frac{d\sigma}{d\Omega}
=\frac{V}{v_{\mathrm{inc}}}\frac{dP}{dt}.
$$

板书对 $dP/dt$ 的说明是：单位时间、单位立体角内的概率（probability per unit time per unit solid angle）。总截面为

$$
\sigma=\frac{1}{S}\int d\Omega\,\frac{d\sigma}{d\Omega}.
$$

总微分概率（Total differential probability）：

$$
dP_{i\to f}
=\frac{|\langle f|\hat S|i\rangle|^2}
{\langle f|f\rangle\langle i|i\rangle}\,d\Pi
=\frac{\Delta T}{V^{N_{\mathrm{inc}}-1}}
\frac{|\mathcal M|^2}
{\displaystyle\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}
\,d\Pi_{\mathrm{LIPS}}.
$$

## 解释

$V$ 是态归一化使用的体积，$\Delta T$ 是时间区间；$d\Pi_{\mathrm{LIPS}}$ 表示洛伦兹不变相空间测度。这里的 $dP/dt$ 按板书约定已是每单位立体角的概率率。$S$ 是避免全同末态重复计数的对称因子，与散射算符 $\hat S$ 区别使用；本讲将它放在总截面积分前。

---

# 2. 散射振幅与质心系中的二体散射

对应图片：

- 2

## 板书整理

![[Picture/7.2/2.png]]

散射振幅（scattering amplitude）$\mathcal M$ 定义为

$$
\langle f|i\hat T|i\rangle
\equiv(2\pi)^4\delta^4(p_f-p_i)\,i\mathcal M.
$$

由前述概率与截面的关系，得到

$$
\sigma
=\frac{1}{S}
\frac{1}{V^{N_{\mathrm{inc}}-2}v_{\mathrm{inc}}}
\frac{1}{\displaystyle\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}
\int |\mathcal M|^2\,d\Pi_{\mathrm{LIPS}}.
$$

板书记号：$\{p_n\}_{n=1}^{N}$ 表示散射后的粒子动量，$\{p_m\}_{m=1}^{N_{\mathrm{inc}}}$ 表示入射粒子动量。单粒子能量满足

$$
\omega_n\equiv\sqrt{|\vec p_n|^2+m_n^2}.
$$

考虑质心系（CM frame）中的 $2\to2$ 散射。入射粒子的四动量为

$$
p_1=(\omega_1,\vec p_1),\qquad
p_2=(\omega_2,\vec p_2),
$$

散射后／末态粒子的四动量为

$$
p_1'=(\omega_1',\vec p_1'),\qquad
p_2'=(\omega_2',\vec p_2').
$$

质心系条件与总能量为

$$
\vec p_2=-\vec p_1,\qquad
\vec p_2'=-\vec p_1',
$$

$$
E_{\mathrm{CM}}\equiv\omega_1+\omega_2
\;(=\omega_1'+\omega_2').
$$

## 解释

振幅定义中的四维 $\delta$ 函数实施总能量和总动量守恒。对两个入射粒子，$N_{\mathrm{inc}}=2$，总截面中的体积因子消失；质心系条件则使两个末态三动量互为相反数。

---

# 3. 展开二体相空间并完成三动量积分

对应图片：

- 3

## 板书整理

![[Picture/7.2/3.png]]

二体散射总截面为

$$
\sigma
=\frac{1}{S}
\frac{1}{4\omega_1\omega_2|\vec v_1-\vec v_2|}
\frac{(2\pi)^4}{4(2\pi)^6}
\int d^3p_1'\,d^3p_2'\,
\frac{|\mathcal M|^2}{\omega_1'\omega_2'}
\delta^4(p_1'+p_2'-p_1-p_2).
$$

图示中，两粒子沿相反方向入射；$\vec p_1'$ 与入射轴夹角为 $\theta$，其方向对应立体角元 $d\Omega$，另一末态动量为 $\vec p_2'$。

板书旁注的球坐标体积元为

$$
d^3p_1=|\vec p_1|^2\,d|\vec p_1|\,d\Omega.
$$

将这一关系用于带撇的末态动量，并拆开四维 $\delta$ 函数：

$$
\begin{aligned}
\sigma
={}&\frac{1}{S}
\frac{1}{64\pi^2\omega_1\omega_2|\vec v_1-\vec v_2|}
\int d\Omega\,d|\vec p_1'|\,|\vec p_1'|^2\,d^3p_2'
\frac{|\mathcal M|^2}{\omega_1'\omega_2'}\\
&\quad\times\delta^3(\vec p_1'+\vec p_2'-\vec p_1-\vec p_2)
\delta(\omega_1'+\omega_2'-\omega_1-\omega_2).
\end{aligned}
$$

三维 $\delta$ 函数给出

$$
\vec p_2'=\vec p_1+\vec p_2-\vec p_1'=-\vec p_1'.
$$

因此，完成 $d^3p_2'$ 积分后，

$$
\sigma
=\frac{1}{S}
\frac{1}{64\pi^2\omega_1\omega_2|\vec v_1-\vec v_2|}
\int d\Omega\,d|\vec p_1'|\,
\frac{|\vec p_1'|^2|\mathcal M|^2}{\omega_1'\omega_2'}
\delta(\omega_1'+\omega_2'-\omega_1-\omega_2).
$$

## 解释

此步先用动量守恒消去一个末态动量积分，留下末态方向和动量大小的积分。球坐标中的 $|\vec p_1'|^2$ 是积分测度的因子，后面需要与能量 $\delta$ 函数换元产生的雅可比一起处理。

---

# 4. 能量守恒的径向积分与换元

对应图片：

- 4

## 板书整理

![[Picture/7.2/4.png]]

按本讲 $\sigma=S^{-1}\int d\Omega\,(d\sigma/d\Omega)$ 的约定，读出质心系微分截面：

$$
\left.\frac{d\sigma}{d\Omega}\right|_{\mathrm{CM}}
=\frac{1}{64\pi^2\omega_1\omega_2|\vec v_1-\vec v_2|}
\int_0^\infty d|\vec p_1'|\,
\frac{|\vec p_1'|^2|\mathcal M|^2}
{\sqrt{|\vec p_1'|^2+m_1'^2}\sqrt{|\vec p_1'|^2+m_2'^2}}
\delta\!\left(
\sqrt{|\vec p_1'|^2+m_1'^2}
+\sqrt{|\vec p_1'|^2+m_2'^2}-E_{\mathrm{CM}}
\right).
$$

令

$$
x=\sqrt{|\vec p_1'|^2+m_1'^2}
+\sqrt{|\vec p_1'|^2+m_2'^2}-E_{\mathrm{CM}}.
$$

于是

$$
dx=\left[
\frac{|\vec p_1'|}{\sqrt{|\vec p_1'|^2+m_1'^2}}
+\frac{|\vec p_1'|}{\sqrt{|\vec p_1'|^2+m_2'^2}}
\right]d|\vec p_1'|.
$$

通分后，板书用空根号代指前面的两个根式；展开该简写为

$$
dx=
\frac{|\vec p_1'|}
{\sqrt{|\vec p_1'|^2+m_1'^2}\sqrt{|\vec p_1'|^2+m_2'^2}}
\underbrace{\left(
\sqrt{|\vec p_1'|^2+m_1'^2}
+\sqrt{|\vec p_1'|^2+m_2'^2}
\right)}_{\text{板书标注为 }E_{\mathrm{CM}}}
d|\vec p_1'|.
$$

换元后的板书原式为

$$
\left.\frac{d\sigma}{d\Omega}\right|_{\mathrm{CM}}
=\frac{1}{64\pi^2\omega_1\omega_2|\vec v_1-\vec v_2|}
\int_{m_1'+m_2'-E_{\mathrm{CM}}}^{\infty}
dx\,|\vec p_1'|\,|\mathcal M|^2\delta(x).
$$

其中，板书特别标明 $|\vec p_1'|$ 是 $x$ 的隐函数。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 4，$dx$ 的通分式与换元后的最后一行。
>
> 板书内容：将两根式之和标为 $E_{\mathrm{CM}}$，并将径向积分写成 $\int dx\,|\vec p_1'|\,|\mathcal M|^2\delta(x)$。
>
> 检查结果：最后一行疑似漏掉雅可比带来的 $1/E_{\mathrm{CM}}$ 因子。
>
> 说明：由 $x$ 的定义，两根式之和一般为 $x+E_{\mathrm{CM}}$，只在 $\delta(x)$ 的支撑点 $x=0$ 上等于 $E_{\mathrm{CM}}$。因此
> $$
> \frac{|\vec p_1'|^2}{\omega_1'\omega_2'}\,d|\vec p_1'|
> =\frac{|\vec p_1'|}{x+E_{\mathrm{CM}}}\,dx.
> $$
> 与 $\delta(x)$ 相乘并积分时，应保留 $1/E_{\mathrm{CM}}$。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

换元把能量守恒条件化成 $\delta(x)$，使剩余径向积分可以直接取能量守恒处的值。下限来自 $|\vec p_1'|=0$ 时的两粒子静质量之和减去总能量。

---

# 5. 阶跃函数与入射速度因子的化简

对应图片：

- 5

## 板书整理

![[Picture/7.2/5.png]]

完成 $x$ 积分后，板书写为

$$
\left.\frac{d\sigma}{d\Omega}\right|_{\mathrm{CM}}
=\frac{|\vec p_1'|\,|\mathcal M|^2}
{64\pi^2\omega_1\omega_2|\vec v_1-\vec v_2|}
\Theta(E_{\mathrm{CM}}-m_1'-m_2').
$$

此处 $|\vec p_1'|$ 要用 $E_{\mathrm{CM}}$ 表示（expressed in terms of $E_{\mathrm{CM}}$）。

右侧给出所用积分性质：

$$
\begin{aligned}
\int_a^\infty dx\,f(x)\delta(x)
&=\int_{-\infty}^{\infty}dx\,f(x)\Theta(x-a)\delta(x)\\
&=f(0)\Theta(-a).
\end{aligned}
$$

> 此处使用了 $\delta$ 函数的筛选性质，并以阶跃函数表示积分区间是否包含 $x=0$；端点值需依具体约定处理。

回顾速度与动量的关系：

$$
\vec v=\frac{\vec p}{\omega}.
$$

在质心系中，

$$
\begin{aligned}
|\vec v_1-\vec v_2|
&=\left|\frac{\vec p_1}{\omega_1}-\frac{\vec p_2}{\omega_2}\right|\\
&=\left|\frac{\vec p_1}{\omega_1}+\frac{\vec p_1}{\omega_2}\right|\\
&=|\vec p_1|\frac{\omega_1+\omega_2}{\omega_1\omega_2}.
\end{aligned}
$$

所以

$$
\omega_1\omega_2|\vec v_1-\vec v_2|
=|\vec p_1|E_{\mathrm{CM}}.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 5，第一行微分截面。
>
> 板书内容：分母为 $64\pi^2\omega_1\omega_2|\vec v_1-\vec v_2|$。
>
> 检查结果：此式延续图片 4 的遗漏；按前述雅可比，分母还应有一个 $E_{\mathrm{CM}}$。本页速度因子的化简本身成立。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

$\Theta$ 用来表达末态能量是否足够；它来自能量守恒方程是否在积分区间内有解。速度因子的化简使用了质心系中两入射动量反向的条件。

---

# 6. 微分截面的板书结果、阈值与弹性散射

对应图片：

- 6

## 板书整理

![[Picture/7.2/6.png]]

板书框出的结果为

$$
\boxed{
\left.\frac{d\sigma}{d\Omega}\right|_{\mathrm{CM}}
=\frac{|\vec p_1'|}{64\pi^2|\vec p_1|E_{\mathrm{CM}}}
|\mathcal M|^2\Theta(E_{\mathrm{CM}}-m_1'-m_2')
}.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 6，框中的二体微分截面。
>
> 板书内容：分母只含一次方的 $E_{\mathrm{CM}}$。
>
> 检查结果：该式沿用了图片 4—5 漏掉的换元因子。由正确雅可比和本讲速度关系，应得到
> $$
> \left.\frac{d\sigma}{d\Omega}\right|_{\mathrm{CM}}
> =\frac{1}{64\pi^2E_{\mathrm{CM}}^2}
> \frac{|\vec p_1'|}{|\vec p_1|}
> |\mathcal M|^2\Theta(E_{\mathrm{CM}}-m_1'-m_2').
> $$
> 在本讲二体振幅归一化下，这也使截面具有能量的负二次方量纲。
>
> 注意：以上为检查提示，未修改原板书内容。

备注 ①：除非

$$
E_{\mathrm{CM}}>m_1'+m_2',
$$

否则

$$
\frac{d\sigma}{d\Omega}=0.
$$

$m_1'+m_2'$ 被称为阈值能量（threshold energy），即产生出射粒子所需的最小能量。

许多情况下，我们关心弹性散射（elastic scattering）：

$$
1+2\longrightarrow1+2.
$$

例如

$$
e^-+e^+\longrightarrow e^-+e^+.
$$

## 解释

阈值要求总能量足以提供末态静质量。板书这里用严格不等号讨论有可用末态相空间的情况；弹性散射则保持散射前后的粒子种类不变，下一张图继续使用这一条件。

---

# 7. 弹性散射条件与质心系运动学

对应图片：

- 7

## 板书整理

![[Picture/7.2/7.png]]

接续弹性散射的讨论：

$$
m_1'=m_1,\qquad m_2'=m_2.
$$

所以

$$
E_{\mathrm{CM}}
=\sqrt{|\vec p_1|^2+m_1^2}
+\sqrt{|\vec p_1|^2+m_2^2}
>m_1+m_2,
$$

从而

$$
\Theta(E_{\mathrm{CM}}-m_1-m_2)=1.
$$

备注 ②：$|\vec p_1|$ 和 $|\vec p_1'|$ 实际上都是 $E_{\mathrm{CM}}$ 的函数，这是运动学（kinematics）关系。

首先，

$$
|\vec p_1|=\sqrt{\omega_1^2-m_1^2},\qquad
|\vec p_2|=\sqrt{\omega_2^2-m_2^2}
\overset{\mathrm{CM}}{=}|\vec p_1|.
$$

因此

$$
\omega_1^2-m_1^2=\omega_2^2-m_2^2
\quad\Longrightarrow\quad
\omega_1^2-\omega_2^2=m_1^2-m_2^2.
$$

再使用

$$
\omega_1+\omega_2=E_{\mathrm{CM}},
$$

两式相除（Divide）得

$$
\omega_1-\omega_2=\frac{m_1^2-m_2^2}{E_{\mathrm{CM}}}.
$$

## 解释

弹性散射的阈值判断是在有非零入射动量的散射情形下进行的；$|\vec p_1|=0$ 时，上面的能量不等式退化为等式。后半部分由两粒子动量大小相等，得到能量之和与能量之差，为下一步解出动量大小作准备。

---

# 8. 入射和出射动量的显式表达式

对应图片：

- 8

## 板书整理

![[Picture/7.2/8.png]]

将上一张图中的能量之和与能量之差相加（Sum），得到

$$
2\omega_1=E_{\mathrm{CM}}
+\frac{m_1^2-m_2^2}{E_{\mathrm{CM}}}.
$$

进而，板书框出

$$
\boxed{
|\vec p_1|
=\sqrt{
\frac{E_{\mathrm{CM}}^2}{4}
+\frac{(m_1^2-m_2^2)^2}{4E_{\mathrm{CM}}^2}
-\frac{m_1^2+m_2^2}{2}
}
}.
$$

> 此处使用了上一张图的 $|\vec p_1|^2=\omega_1^2-m_1^2$，并展开平方。

类似地（Similarly），

$$
\boxed{
|\vec p_1'|
=\sqrt{
\frac{E_{\mathrm{CM}}^2}{4}
+\frac{(m_1'^2-m_2'^2)^2}{4E_{\mathrm{CM}}^2}
-\frac{m_1'^2+m_2'^2}{2}
}
}.
$$

板书说明：弹性散射满足

$$
|\vec p_1'|=|\vec p_1|.
$$

另一个说明：在质心系中，$|\vec p_1|$ 与 $|\vec p_1'|$ 均不依赖散射角 $\theta$；这一性质在其他参考系中一般不成立。$|\mathcal M|^2$ 在任一参考系中一般都依赖 $\theta$。

## 解释

给定质心能量和粒子质量后，二体初态、末态的动量大小由运动学确定。弹性散射前后质量相同，所以动量大小相同；角分布仍可通过振幅中的角度依赖体现出来。关于其他参考系的旁注，主要指末态动量大小通常会随散射方向变化，固定入射束的动量本身仍是给定的。

---

# 9. 重靶上的非相对论弹性散射

对应图片：

- 9

## 板书整理

![[Picture/7.2/9.png]]

板书标为备注 ④：重靶上的非相对论散射，且为弹性散射（Non-relativistic scattering with heavy target, elastic）。

例一，库仑散射（Coulomb scattering）：

$$
e^-+p^+\longrightarrow e^-+p^+.
$$

例二，卢瑟福散射（Rutherford scattering）：

$$
\alpha+N\longrightarrow\alpha+N.
$$

板书标注 $\alpha$ particle $={}^4\mathrm{He}$，$N$ 为重原子核（heavy nucleus）。图示为质量 $m_1$ 的轻粒子入射质量 $m_2$ 的重靶，并发生偏转。

质心系近似等于固定靶参考系：

$$
\text{CM frame}\approx\text{fixed target frame},
$$

因此

$$
E_{\mathrm{CM}}\approx m_2.
$$

板书框出

$$
\boxed{
\left.\frac{d\sigma}{d\Omega}\right|_{\mathrm{CM}}
\approx\frac{|\mathcal M|^2}{64\pi^2m_2^2}
}.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 9，重靶散射截面，与图片 6 的一般公式对照。
>
> 板书内容：这里的分母为 $64\pi^2m_2^2$，而图片 6 分母只含一次方的 $E_{\mathrm{CM}}$。
>
> 检查结果：两页原式不能直接衔接。本页结果与图片 6 检查注释中含 $E_{\mathrm{CM}}^2$ 的表达式一致：使用弹性条件 $|\vec p_1'|=|\vec p_1|$，再令 $E_{\mathrm{CM}}\approx m_2$ 即可得到。
>
> 注意：以上为检查提示，未修改两处原板书内容。

## 解释

这里的近似要求靶质量远大于入射粒子质量，且动能相对靶静质量很小，因而质心运动很慢、总能量主要由 $m_2$ 决定。$\alpha$ 粒子是氦-4 的原子核，板书的 ${}^4\mathrm{He}$ 是对此的简写。所提供图片中的备注编号从 ② 跳到 ④，本讲义保留这一编号，不补写未出现的条目。

---

# 10. 粒子衰变与衰变率

对应图片：

- 10

## 板书整理

![[Picture/7.2/10.png]]

粒子衰变（Particle decay）：一个初态粒子衰变为 $N$ 个末态粒子。图中标注 $N_{\mathrm{inc}}=1$，初态动量为 $p_1$。

定义微分衰变率（Differential decay rate）：

$$
d\Gamma\equiv\frac{dP_{i\to f}}{\Delta T}.
$$

在跃迁概率公式中取 $N_{\mathrm{inc}}=1$：

$$
dP_{i\to f}
=\Delta T\,\frac{|\mathcal M|^2}{2\omega_1}
\,d\Pi_{\mathrm{LIPS}}.
$$

因此

$$
\boxed{
d\Gamma=\frac{|\mathcal M|^2}{2\omega_1}
\,d\Pi_{\mathrm{LIPS}}
}.
$$

总衰变率（Total decay rate）为

$$
\Gamma=\frac{1}{S}\int d\Gamma,
$$

其中 $S$ 是全同末态粒子的对称因子（symmetry factor for identical final particles）。

板书旁注：在质心系中，

$$
\omega_1=m_1.
$$

## 解释

衰变过程只含一个初态粒子，直接将跃迁概率除以时间区间就得到衰变率。对单个初态粒子，质心系就是其静止系；总衰变率还要对允许的末态相空间积分，并处理全同粒子的重复计数。

---

# 11. LSZ 约化公式的引入与相互作用真空

对应图片：

- 11

## 板书整理

![[Picture/7.2/11.png]]

新主题：LSZ 约化公式（LSZ reduction formula），全称为 Lehmann–Symanzik–Zimmermann。

计算散射可观测量的问题，已经归结为计算

$$
\langle f|\hat S|i\rangle
\equiv\langle f;+\infty|i;-\infty\rangle.
$$

相互作用量子场论的假设（Postulates of interacting QFT）：存在基态，即零粒子态（ground state / zero-particle state），记为

$$
|\Omega\rangle.
$$

一般而言，

$$
|\Omega\rangle\ne|0\rangle,
$$

其中 $|0\rangle$ 是自由理论的基态。

## 解释

这部分从可观测的截面、衰变率转向如何计算散射矩阵元，并先区分相互作用理论真空与自由真空。本组板书仅开始建立 LSZ 讨论所需的概念，还没有写出完整的约化公式。

---

# 12. 含时产生、湮灭算符及等时对易关系

对应图片：

- 12

## 板书整理

![[Picture/7.2/12.png]]

继续列出假设：在每个时刻 $t$，存在产生、湮灭算符

$$
\widetilde a_{\vec p}^{\dagger}(t),\qquad
\widetilde a_{\vec p}(t).
$$

它们满足

$$
\widetilde a_{\vec p}(t)|\Omega\rangle=0,
$$

$$
\left[\widetilde a_{\vec p}(t),\widetilde a_{\vec q}(t)\right]
=0
=\left[\widetilde a_{\vec p}^{\dagger}(t),
\widetilde a_{\vec q}^{\dagger}(t)\right],
$$

$$
\left[\widetilde a_{\vec p}(t),\widetilde a_{\vec q}^{\dagger}(t)\right]
=(2\pi)^3\delta^3(\vec p-\vec q).
$$

说明（Note）：一般有

$$
\widetilde a_{\vec p}(t_1)\ne\widetilde a_{\vec p}(t_2),
$$

即这些算符随时间变化。不过，板书强调它们不按海森堡方程演化（they do not evolve with the Heisenberg equation）。蓝色旁注为

$$
\widetilde a_{\vec p}(t)\ne a_{\vec p}(t),
$$

其中右侧 $a_{\vec p}(t)$ 标为海森堡算符（Heisenberg operator）。

## 解释

这里给出的是课堂对带波浪号算符的假设及记号区分；等时对易关系采用玻色算符形式。算符显含时间并不等于它就是由固定算符按海森堡演化定义的算符。由于本页尚未给出 $\widetilde a_{\vec p}(t)$ 的具体构造，应保留这一区分，不能自行将它替换成 $a_{\vec p}(t)$。

---

# 13. 自由理论极限与有限时刻的“单粒子态”

对应图片：

- 13

## 板书整理

![[Picture/7.2/13.png]]

说明 2（Note 2）：在自由理论中，

$$
\widetilde a_{\vec p}(t)\longrightarrow a_{\vec p},
$$

但可以带有一个相位因子

$$
e^{i\theta(t)}.
$$

板书指出，该相位因子不影响对易关系（irrelevant for the commutation relations）。

说明 3（Note 3）：仿照自由理论，可以定义一个“单粒子态”（one-particle state）：

$$
|\vec p;t\rangle
\equiv\sqrt{2\omega_p}\,
\widetilde a_{\vec p}^{\dagger}(t)|\Omega\rangle.
$$

但是，板书强调：这在相互作用理论中不是一个良好的粒子态概念，因为它不是 $H$ 的本征态（not an eigenstate of $H$）。

## 解释

产生算符与湮灭算符上的共轭相位在等时混合对易关系中抵消，所以不改变上一页的归一化关系。形式上对真空作用一次产生算符，可以定义一个态；但在相互作用理论中，这一有限时刻定义本身并不能保证得到确定能量的粒子态。这是本组板书的结束位置。

---

# 本节知识结构

散射微分截面与跃迁概率的回顾（图 1）  
↓  
散射振幅、总截面与质心系二体运动学设定（图 2）  
↓  
展开末态相空间，用三动量守恒消去一个积分（图 3）  
↓  
对能量守恒条件换元，完成径向积分（图 4）  
↓  
阶跃函数与入射速度因子的化简（图 5）  
↓  
二体微分截面、散射阈值与弹性散射（图 6）  
↓  
由能量和动量关系解出入射、出射动量大小（图 7—8）  
↓  
重靶非相对论弹性散射的近似（图 9）  
↓  
单粒子衰变的微分衰变率和总衰变率（图 10）  
↓  
引入 LSZ：散射矩阵元与相互作用真空（图 11）  
↓  
含时产生、湮灭算符及等时对易关系（图 12）  
↓  
自由理论极限与有限时刻“单粒子态”的局限（图 13）

---

# 核心公式清单

下表按课堂顺序列出重要公式。含疑似遗漏的截面表达式仍按原板书收录，检查结果见正文相应注释。

| 公式 | 含义 |
| ----- | ---- |
| $\dfrac{d\sigma}{d\Omega}=\dfrac{V}{v_{\mathrm{inc}}}\dfrac{dP}{dt}$ | 微分截面与单位立体角概率率的关系 |
| $\sigma=\dfrac1S\int d\Omega\,\dfrac{d\sigma}{d\Omega}$ | 含全同末态对称因子的总截面 |
| $dP_{i\to f}=\dfrac{\lvert\langle f\lvert\hat S\rvert i\rangle\rvert^2}{\langle f\vert f\rangle\langle i\vert i\rangle}\,d\Pi=\dfrac{\Delta T}{V^{N_{\mathrm{inc}}-1}}\dfrac{\lvert\mathcal M\rvert^2}{\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}\,d\Pi_{\mathrm{LIPS}}$ | 总微分跃迁概率 |
| $\langle f\lvert i\hat T\rvert i\rangle=(2\pi)^4\delta^4(p_f-p_i)\,i\mathcal M$ | 散射振幅定义 |
| $\sigma=\dfrac1S\dfrac{1}{V^{N_{\mathrm{inc}}-2}v_{\mathrm{inc}}}\dfrac{1}{\prod_{m=1}^{N_{\mathrm{inc}}}2\omega_{p_m}}\int\lvert\mathcal M\rvert^2d\Pi_{\mathrm{LIPS}}$ | 总截面的振幅表达式 |
| $\omega_n=\sqrt{\lvert\vec p_n\rvert^2+m_n^2}$ | 单粒子能量 |
| $\vec p_2=-\vec p_1,\ \vec p_2'=-\vec p_1',\ E_{\mathrm{CM}}=\omega_1+\omega_2=\omega_1'+\omega_2'$ | 二体质心系条件 |
| $d^3p_1'=\lvert\vec p_1'\rvert^2d\lvert\vec p_1'\rvert\,d\Omega$ | 球坐标相空间测度 |
| $x=\sqrt{\lvert\vec p_1'\rvert^2+m_1'^2}+\sqrt{\lvert\vec p_1'\rvert^2+m_2'^2}-E_{\mathrm{CM}}$ | 能量守恒积分的换元变量 |
| $dx=\left(\dfrac{\lvert\vec p_1'\rvert}{\omega_1'}+\dfrac{\lvert\vec p_1'\rvert}{\omega_2'}\right)d\lvert\vec p_1'\rvert$ | 换元微分关系；原板书后续疑似遗漏因子 |
| $\int_a^\infty dx\,f(x)\delta(x)=f(0)\Theta(-a)$ | 用阶跃函数表示积分区间限制，端点值依约定 |
| $\vec v=\vec p/\omega,\quad\omega_1\omega_2\lvert\vec v_1-\vec v_2\rvert=\lvert\vec p_1\rvert E_{\mathrm{CM}}$ | 质心系速度因子的化简 |
| $\left.\dfrac{d\sigma}{d\Omega}\right\rvert_{\mathrm{CM}}=\dfrac{\lvert\vec p_1'\rvert\lvert\mathcal M\rvert^2}{64\pi^2\lvert\vec p_1\rvert E_{\mathrm{CM}}}\Theta(E_{\mathrm{CM}}-m_1'-m_2')$ | **图片 6 原式，疑似漏掉一个 $1/E_{\mathrm{CM}}$；见第 6 节检查注释** |
| $E_{\mathrm{CM}}>m_1'+m_2'$ | 板书给出的非零末态相空间条件 |
| $\omega_1-\omega_2=(m_1^2-m_2^2)/E_{\mathrm{CM}}$ | 质心系两入射粒子的能量差 |
| $2\omega_1=E_{\mathrm{CM}}+(m_1^2-m_2^2)/E_{\mathrm{CM}}$ | 由能量和与差确定单粒子能量 |
| $\lvert\vec p_1\rvert=\sqrt{\dfrac{E_{\mathrm{CM}}^2}{4}+\dfrac{(m_1^2-m_2^2)^2}{4E_{\mathrm{CM}}^2}-\dfrac{m_1^2+m_2^2}{2}}$ | 入射动量大小 |
| $\lvert\vec p_1'\rvert=\sqrt{\dfrac{E_{\mathrm{CM}}^2}{4}+\dfrac{(m_1'^2-m_2'^2)^2}{4E_{\mathrm{CM}}^2}-\dfrac{m_1'^2+m_2'^2}{2}}$ | 出射动量大小 |
| $m_1'=m_1,\ m_2'=m_2\ \Rightarrow\ \lvert\vec p_1'\rvert=\lvert\vec p_1\rvert$ | 弹性散射的动量大小关系 |
| $E_{\mathrm{CM}}\approx m_2,\quad\left.\dfrac{d\sigma}{d\Omega}\right\rvert_{\mathrm{CM}}\approx\dfrac{\lvert\mathcal M\rvert^2}{64\pi^2m_2^2}$ | 重靶非相对论弹性散射；与图片 6 原式的差异见第 9 节 |
| $d\Gamma=\dfrac{dP_{i\to f}}{\Delta T}=\dfrac{\lvert\mathcal M\rvert^2}{2\omega_1}d\Pi_{\mathrm{LIPS}}$ | 微分衰变率；初态静止时 $\omega_1=m_1$ |
| $\Gamma=\dfrac1S\int d\Gamma$ | 总衰变率 |
| $\langle f\lvert\hat S\rvert i\rangle=\langle f;+\infty\vert i;-\infty\rangle$ | 散射矩阵元与渐近态重叠 |
| $\lvert\Omega\rangle\ne\lvert0\rangle$ | 相互作用真空一般不同于自由真空 |
| $\widetilde a_{\vec p}(t)\lvert\Omega\rangle=0$ | 湮灭算符作用于相互作用真空 |
| $[\widetilde a_{\vec p}(t),\widetilde a_{\vec q}(t)]=[\widetilde a_{\vec p}^{\dagger}(t),\widetilde a_{\vec q}^{\dagger}(t)]=0$ | 两类同种算符的等时对易关系 |
| $[\widetilde a_{\vec p}(t),\widetilde a_{\vec q}^{\dagger}(t)]=(2\pi)^3\delta^3(\vec p-\vec q)$ | 产生、湮灭算符的混合等时对易关系 |
| $\widetilde a_{\vec p}(t_1)\ne\widetilde a_{\vec p}(t_2),\quad\widetilde a_{\vec p}(t)\ne a_{\vec p}(t)$ | 时间依赖及与海森堡算符的区分 |
| $\widetilde a_{\vec p}(t)\to a_{\vec p}$，允许相位 $e^{i\theta(t)}$ | 自由理论极限的板书说明 |
| $\lvert\vec p;t\rangle\equiv\sqrt{2\omega_p}\,\widetilde a_{\vec p}^{\dagger}(t)\lvert\Omega\rangle$ | 有限时刻形式上的“单粒子态”；板书指出其不是 $H$ 的本征态 |
