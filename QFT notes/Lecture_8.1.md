---
title: "量子场论导论 Lecture 8.1"
date: 2026-10-28
tags:
  - 量子场论导论
  - lecture
  - LSZ约化公式
  - 渐近态
  - 接触项
  - 时间排序
source: "课堂板书"
---

# Lecture 8.1: LSZ 约化公式、接触项与渐近算符关系的证明

## 本节内容概览

本节从上次课的散射、粒子衰变及 LSZ 约化公式回顾出发，说明场的物理质量、真空期望值和单粒子矩阵元的归一化条件。随后用渐近产生与湮灭算符表示入射态、出射态和散射矩阵元，给出 LSZ 公式。接着通过二点函数的时间排序与等时对易关系，逐步说明接触项的来源，并联系自由场的费曼传播子。最后利用分部积分和渐近自由条件，证明渐近算符之差与场的四维积分之间的关系，并讨论这一推导对具体相互作用形式的独立性。

<!-- date 为整理日期；板书未标明授课日期。正文按 Picture/8.1/1.jpg 至 13.jpg 的编号顺序展开。原图使用带目录的 Obsidian 引用，以区分不同课次的同名图片。板书疑似问题保留原式并就地标注。手写的产生算符上标 + 以 LaTeX 的 \dagger 表示。 -->

---

# 1. 上节回顾与量子场的定义

对应图片：

- 1

## 板书整理

![[Picture/8.1/1.jpg]]

课堂提醒：作业、考试（HW, exam）。

上节内容：

- $2\to2$ 散射。
- 粒子衰变。
- LSZ 约化公式。

引入含时算符 $\widetilde a_{\vec p}(t)$、$\widetilde a^\dagger_{\vec p}(t)$，板书列出

$$
\widetilde a_{\vec p}(t)|\Omega\rangle=0,
\qquad \forall t,
$$

并说明：对易关系在任意时刻成立（Commutation relations, $\forall t$）。本图没有展开对易关系的具体形式。

定义量子场：

$$
\phi(x)=\int\frac{d^3p}{(2\pi)^3\sqrt{2\omega_p}}
\left[
\widetilde a_{\vec p}(t)e^{ip\cdot x}
+\widetilde a^\dagger_{\vec p}(t)e^{-ip\cdot x}
\right].
$$

约定

$$
p\cdot x\equiv-\omega_p t+\vec p\cdot\vec x,
\qquad
\omega_p\equiv\sqrt{\vec p^{\,2}+m^2}.
$$

## 解释

$|\Omega\rangle$ 表示相互作用理论的真空。这里把显式平面波因子与算符本身的时间依赖分开；不能因为展开式外形类似自由场，就直接把有限时刻的 $\widetilde a_{\vec p}(t)$ 当成时间不变的自由场算符。后续所有相位符号均沿用本图的 $p\cdot x$ 约定。

---

# 2. 物理质量与场的归一化条件

对应图片：

- 2

## 板书整理

![[Picture/8.1/2.jpg]]

按定义，$m$ 是与场 $\phi$ 对应的粒子的**物理质量**（physical mass）。

一般而言，这个 $m$ 不同于拉格朗日量中 $\phi^2$ 项所含的质量参数。板书写为

$$
\mathcal L=\cdots-\frac{m'^2}{2}\phi^2+\cdots,
$$

并指出在相互作用理论中

$$
m'\ne m.
$$

板书提出两个条件（Proposition）：

$$
\boxed{\langle\Omega|\phi(x)|\Omega\rangle=0}
\qquad\text{“tadpole cancellation”},
$$

即蝌蚪项消除条件；以及

$$
\boxed{\langle\vec p;t|\phi(x)|\Omega\rangle=e^{-ip\cdot x}}
\qquad\text{“wave-function normalization”},
$$

即波函数归一化条件。

## 解释

本图区分了粒子的物理质量 $m$ 与拉格朗日量参数 $m'$。两个矩阵元条件分别固定场的真空期望值和场与所定义单粒子态之间的归一化；这里按板书保留态标记中的时间 $t$。

---

# 3. 拉格朗日量系数与时间排序

对应图片：

- 3

## 板书整理

![[Picture/8.1/3.jpg]]

通常，上述两个条件会使拉格朗日量的系数偏离自由理论的数值。实际上，还会有更多条件，包括电子电荷等其他可观测量所对应的条件。

板书写出

$$
\mathcal L
=-\frac12 Z(\partial\phi)^2
-\frac{m'^2}{2}\phi^2
+Y\phi
+(\text{interactions}).
$$

在自由理论中，

$$
Y=0,\qquad Z=1,\qquad m'=m.
$$

右侧红字补充时间排序的例子：当 $t_2>t_1$ 时，

$$
T\{O(t_1)O(t_2)\}=O(t_2)O(t_1).
$$

## 解释

$Y$、$Z$ 和 $m'$ 分别出现在场的一次项、动能项和质量项中。时间排序 $T$ 将时间较晚的算符放到左边；本节讨论的是标量玻色场，板书此处没有涉及费米算符交换的符号。

---

# 4. 渐近态与散射矩阵元

对应图片：

- 4

## 板书整理

![[Picture/8.1/4.jpg]]

本节只考虑与 $\phi$ 对应的**一种粒子类型**（Only one particle type $\sim\phi$）。

入射渐近态：

$$
|i;-\infty\rangle
=\sqrt{2\omega_1}\sqrt{2\omega_2}\cdots
\widetilde a^\dagger_{\vec p_1}(-\infty)
\widetilde a^\dagger_{\vec p_2}(-\infty)\cdots
|\Omega\rangle.
$$

出射渐近态的左矢：

$$
\langle f;+\infty|
=\sqrt{2\omega'_1}\sqrt{2\omega'_2}\cdots
\langle\Omega|
\widetilde a_{\vec p'_1}(+\infty)
\widetilde a_{\vec p'_2}(+\infty)\cdots.
$$

散射矩阵元的定义及板书展开为

$$
\begin{aligned}
\langle f|\hat S|i\rangle
&\equiv\langle f;+\infty|i;-\infty\rangle\\
&=\sqrt{2\omega_1\cdots2\omega'_1\cdots}\,
\langle\Omega|
\widetilde a_{\vec p'_1}(+\infty)\cdots
\widetilde a_{\vec p_1}(-\infty)\cdots
|\Omega\rangle.
\end{aligned}
$$

板书标注：上述算符乘积已经按时间排序（already time-ordered）。因此继续写成

$$
\langle f|\hat S|i\rangle
=\sqrt{2\omega_1\cdots2\omega'_1\cdots}\,
\langle\Omega|T\{
\widetilde a_{\vec p'_1}(+\infty)\cdots
\widetilde a_{\vec p_1}(-\infty)\cdots
\}|\Omega\rangle.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 4 下半部的两行散射矩阵元。
>
> 板书内容：入射因子写为 $\widetilde a_{\vec p_1}(-\infty)$，未写产生算符的上标。
>
> 检查结果：疑似漏写 $\dagger$。
>
> 说明：由本图上方的入射态定义，这两行的入射因子应对应 $\widetilde a^\dagger_{\vec p_1}(-\infty)$。若按原式直接用湮灭算符作用于真空，矩阵元会消失。下一张板书在对应位置写出了产生算符。
>
> 注意：以上为检查提示，未修改原板书内容。

右侧回顾单粒子态定义：

$$
|\vec p;t\rangle\equiv
\sqrt{2\omega_p}\,\widetilde a^\dagger_{\vec p}(t)|\Omega\rangle.
$$

记号：$\{\vec p_1,\vec p_2,\ldots\}$ 是初态粒子的动量；$\{\vec p'_1,\vec p'_2,\ldots\}$ 是末态粒子的动量。能量满足

$$
\omega_p\equiv\sqrt{\vec p^{\,2}+m^2},
\qquad
\omega'_p\equiv\sqrt{\vec p'^{\,2}+m^2}.
$$

## 解释

初态在 $t\to-\infty$ 定义，末态在 $t\to+\infty$ 定义；它们的内积给出散射矩阵元。每个 $\sqrt{2\omega}$ 来自板书采用的单粒子态归一化。由于出射算符的时间晚于入射算符，原有的左右次序已经符合时间排序。

---

# 5. 渐近算符之差与待证命题

对应图片：

- 5

## 板书整理

![[Picture/8.1/5.jpg]]

承接上一图，板书将矩阵元改写为

$$
\begin{aligned}
\langle f|\hat S|i\rangle
={}&\sqrt{2\omega_1\cdots2\omega'_1\cdots}\,
\langle\Omega|T\Big\{
\left[
\widetilde a_{\vec p'_1}(+\infty)
-\widetilde a_{\vec p'_1}(-\infty)
\right]\cdots\\
&\hspace{2em}\times
\left[
\widetilde a^\dagger_{\vec p_1}(-\infty)
-\widetilde a^\dagger_{\vec p_1}(+\infty)
\right]\cdots
\Big\}|\Omega\rangle.
\end{aligned}
$$

板书用箭头解释加入的两项：

- $\widetilde a_{\vec p'_1}(-\infty)$ 移向右边，并湮灭 $|\Omega\rangle$。
- $\widetilde a^\dagger_{\vec p_1}(+\infty)$ 移向左边，并湮灭 $\langle\Omega|$。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 5 顶部，把算符乘积直接换成渐近算符差的乘积。
>
> 板书内容：移向真空后，所添加的项被视为零。
>
> 检查结果：此步省略了移动算符时可能出现的对易子项，需说明所讨论的散射部分或动量条件。
>
> 说明：把入射湮灭算符移过入射产生算符时，一般会产生正比于 $(2\pi)^3\delta^{(3)}(\vec p'_j-\vec p_k)$ 的项，对应粒子不发生散射而直接通过的贡献。若排除了这些动量重合项，或已单独处理相应的非散射贡献，板书的简写才可直接使用；不能仅凭“湮灭真空”便忽略它们。
>
> 注意：以上为检查提示，未修改原板书内容。

随后提出命题（Proposition）：

$$
\boxed{
\sqrt{2\omega_p}
\left[\widetilde a_{\vec p}(+\infty)
-\widetilde a_{\vec p}(-\infty)\right]
=i\int d^4x\,e^{-ip\cdot x}
(-\Box+m^2)\phi(x)
}.
$$

相应的产生算符关系为

$$
\boxed{
\sqrt{2\omega_p}
\left[\widetilde a^\dagger_{\vec p}(-\infty)
-\widetilde a^\dagger_{\vec p}(+\infty)\right]
=i\int d^4x\,e^{+ip\cdot x}
(-\Box+m^2)\phi(x)
}.
$$

## 解释

这两个命题把无穷远时刻的算符差换成对场的时空积分，是接下来写出 LSZ 公式的关键。板书先使用命题，稍后再证明；这里保持这一顺序。对实标量场，第二式也可由第一式取厄米共轭后将两边乘以 $-1$ 得到。

---

# 6. LSZ 约化公式与接触项的出现

对应图片：

- 6

## 板书整理

![[Picture/8.1/6.jpg]]

把上一图的两个命题代入散射矩阵元：

$$
\begin{aligned}
\langle f|\hat S|i\rangle
=\langle\Omega|T\Big\{
&\left[i\int d^4x_1\,e^{ip_1\cdot x_1}
(-\Box_{x_1}+m^2)\phi(x_1)\right]\cdots\\
&\times\left[i\int d^4x'_1\,e^{-ip'_1\cdot x'_1}
(-\Box_{x'_1}+m^2)\phi(x'_1)\right]\cdots
\Big\}|\Omega\rangle.
\end{aligned}
$$

板书框出 **LSZ formula**：

$$
\boxed{
\begin{aligned}
\langle f|\hat S|i\rangle
={}&\left[i\int d^4x_1\,e^{ip_1\cdot x_1}
(-\Box_{x_1}+m^2)\right]\cdots\\
&\times\left[i\int d^4x'_1\,e^{-ip'_1\cdot x'_1}
(-\Box_{x'_1}+m^2)\right]\cdots\\
&\times\langle\Omega|T\{
\phi(x_1)\cdots\phi(x'_1)\cdots
\}|\Omega\rangle\\
&+(\text{contact terms}).
\end{aligned}
}
$$

其中每个初态粒子对应一个不带撇的积分，每个末态粒子对应一个带撇的积分。

## 解释

公式将散射矩阵元与真空中的时间排序场关联函数联系起来。入射因子是 $e^{+ip\cdot x}$，出射因子是 $e^{-ip'\cdot x'}$，都由前一图的算符关系确定。把微分算符从时间排序内部移到外部会产生接触项，不能把这一步视为普通代数换序；板书保留了这些项，并在后面解释其来源。上一节关于非散射贡献的检查提示同样适用于此处的矩阵元记号。

---

# 7. 接触项：二点函数的例子与时间排序展开

对应图片：

- 7

## 板书整理

![[Picture/8.1/7.jpg]]

接触项（Contact terms）具有

$$
\text{contact terms}\propto\delta^{(4)}(x_i-x_j)
$$

的形式。当把 $(-\Box_x+m^2)$ 从 $T\{\cdots\}$ 中移出时，会出现这类项。

例子：

$$
\begin{aligned}
&(-\Box_x+m^2)
\langle\Omega|T\{\phi(x)\phi(y)\}|\Omega\rangle\\
&\quad=\langle\Omega|T\{
[(-\Box_x+m^2)\phi(x)]\phi(y)
\}|\Omega\rangle
-i\delta^{(4)}(x-y).
\end{aligned}
$$

板书把微分算符分解为

$$
-\Box_x+m^2
=\partial_t^2-\vec\nabla_x^{\,2}+m^2,
$$

并指出 $-\vec\nabla_x^{\,2}+m^2$ 可以自由移入时间排序内部。

证明从时间排序的定义开始。取 $x=(t,\vec x)$、$y=(t',\vec x')$，则

$$
\begin{aligned}
&\langle\Omega|T\{\phi(t,\vec x)\phi(t',\vec x')\}|\Omega\rangle\\
&\quad\equiv\Theta(t-t')
\langle\Omega|\phi(t,\vec x)\phi(t',\vec x')|\Omega\rangle\\
&\qquad+\Theta(t'-t)
\langle\Omega|\phi(t',\vec x')\phi(t,\vec x)|\Omega\rangle.
\end{aligned}
$$

旁注为

$$
\partial_t\Theta(t-t')=\delta(t-t').
$$

## 解释

时间排序由阶跃函数决定，时间微分会作用在这些阶跃函数上，因而产生 $\delta$ 分布。空间微分和质量项不对时间阶跃函数求导，所以额外项只需从 $\partial_t^2$ 中寻找。上式中接触项的系数使用了课堂随后写出的等时对易关系，其归一化条件在第 9 节一并检查。

---

# 8. 一次时间求导：等时场对易子为零

对应图片：

- 8

## 板书整理

![[Picture/8.1/8.jpg]]

板书说明：只需考虑 $\partial_t^2$。先对上一图的二点函数求一次导数；以 $(\cdots)$ 保留板书对该函数的简写：

$$
\begin{aligned}
\partial_t(\cdots)
={}&\Theta(t-t')
\langle\Omega|\partial_t\phi(t,\vec x)\,
\phi(t',\vec x')|\Omega\rangle\\
&+\Theta(t'-t)
\langle\Omega|\phi(t',\vec x')\,
\partial_t\phi(t,\vec x)|\Omega\rangle\\
&+\delta(t-t')
\langle\Omega|
[\phi(t,\vec x),\phi(t',\vec x')]
|\Omega\rangle.
\end{aligned}
$$

在 $\delta(t-t')$ 的作用下，对易子取等时值：

$$
[\phi(t,\vec x),\phi(t',\vec x')]
\ \longrightarrow\
[\phi(t,\vec x),\phi(t,\vec x')]=0.
$$

板书说明：这个零来自 $\widetilde a_{\vec p}(t)$、$\widetilde a^\dagger_{\vec p}(t)$ 的对易关系。

因此

$$
\partial_t(\cdots)
=\langle\Omega|T\{
\partial_t\phi(t,\vec x)\,\phi(t',\vec x')
\}|\Omega\rangle.
$$

> 此处使用了 $\delta(t-t')$ 将对易子限制到等时，以及等时场对易子为零的性质。

## 解释

第一次求导虽然形式上产生一个 $\delta(t-t')$ 项，但它乘着零的等时场对易子，因此没有留下接触项。这个结论只说明一次时间导数的情况；还需继续计算第二次导数。

---

# 9. 二次时间求导：得到四维接触项

对应图片：

- 9

## 板书整理

![[Picture/8.1/9.jpg]]

对上一图的结果再求一次时间导数：

$$
\begin{aligned}
\partial_t^2(\cdots)
={}&\langle\Omega|T\{
\partial_t^2\phi(t,\vec x)\,\phi(t',\vec x')
\}|\Omega\rangle\\
&+\delta(t-t')\langle\Omega|
[\partial_t\phi(t,\vec x),\phi(t,\vec x')]
|\Omega\rangle.
\end{aligned}
$$

板书标出等时对易关系

$$
[\partial_t\phi(t,\vec x),\phi(t,\vec x')]
=-i\delta^{(3)}(\vec x-\vec x').
$$

所以第二项为

$$
\begin{aligned}
&\delta(t-t')\langle\Omega|
[\partial_t\phi(t,\vec x),\phi(t,\vec x')]
|\Omega\rangle\\
&\qquad=-i\delta^{(4)}(x-x')\langle\Omega|\Omega\rangle.
\end{aligned}
$$

板书采用真空归一化

$$
\langle\Omega|\Omega\rangle\equiv1.
$$

于是接触项为 $-i\delta^{(4)}(x-x')$，与图片 7 的例子相符。

> [!warning]
> **板书检查提醒**
>
> 位置：图片 9 的等时对易关系，以及图片 7 的接触项系数。
>
> 板书内容：$[\partial_t\phi(t,\vec x),\phi(t,\vec x')]=-i\delta^{(3)}(\vec x-\vec x')$。
>
> 检查结果：该式使用了场的特定正则归一化，与图片 3 中一般的动能系数 $Z$ 之间需要说明约定。
>
> 说明：若图片 3 的拉格朗日量没有额外的导数相互作用，则共轭动量为 $\pi=Z\partial_t\phi$。由正则关系 $[\phi(t,\vec x),\pi(t,\vec x')]=i\delta^{(3)}(\vec x-\vec x')$，可得 $[\partial_t\phi(t,\vec x),\phi(t,\vec x')]=-i\delta^{(3)}(\vec x-\vec x')/Z$。因此，直接使用板书的单位系数需要 $Z=1$，或另行说明场和共轭动量所采用的归一化；单粒子矩阵元的归一化本身不能代替这一说明。
>
> 注意：以上为检查提示，未修改原板书内容。

## 解释

第二次求导出现的是 $\partial_t\phi$ 与 $\phi$ 的等时对易子，它不再为零。时间的 $\delta(t-t')$ 与空间的 $\delta^{(3)}(\vec x-\vec x')$ 合成四维 $\delta$ 分布，说明这一贡献只支撑在两个时空点重合的位置。

---

# 10. 自由场传播子的格林函数方程与命题证明的起点

对应图片：

- 10

## 板书整理

![[Picture/8.1/10.jpg]]

在自由理论中，

$$
|\Omega\rangle=|0\rangle,
$$

并有

$$
\langle0|T\{\phi(x)\phi(x')\}|0\rangle
=D_F(x-x'),
$$

以及自由场方程

$$
(-\Box_x+m^2)\phi(x)=0.
$$

因此，利用前面的接触项关系，板书得到

$$
\boxed{
(\Box_x-m^2)D_F(x-x')
=i\delta^{(4)}(x-x')
}.
$$

板书标注：格林函数（Green function）。

接着开始证明图片 5 的命题（Proof of the proposition）。考虑某个函数 $f(x)$，满足

$$
\lim_{|\vec x|\to\infty}f(x)=0.
$$

## 解释

自由场本身满足齐次场方程，但时间排序二点函数因接触项而满足带点源的方程，因此是相应微分算符的格林函数。随后引入的 $f(x)$ 用于先建立分部积分恒等式，再将该恒等式用于量子场；这里的极限是空间无穷远的极限。

---
