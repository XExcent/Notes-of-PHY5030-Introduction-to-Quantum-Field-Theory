---
title: "量子场论导论 Lecture 8.2"
date: 2026-10-30
tags:
  - 量子场论导论
  - lecture
  - 拉格朗日微扰论
  - Schwinger-Dyson方程
  - Ward-Takahashi恒等式
  - Wick定理
source: "课堂板书"
---

# Lecture 8.2: 拉格朗日微扰论、Schwinger–Dyson 方程、Ward–Takahashi 恒等式与 Wick 定理

## 本节内容概览

本节由 LSZ 公式回顾引出量子场论的三种微扰方法，随后采用拉格朗日形式，列出标量场的等时对易关系和算符运动方程。由时间排序产生的接触项，课堂先得到 Schwinger–Dyson 方程，再从连续对称性的 Noether 流逐步推导 Ward–Takahashi 恒等式。接着引入传播子简记和 DeWitt 记号，通过分部积分与自由场 Schwinger–Dyson 方程建立多点函数的递推关系。最后把递推结果写成完全收缩之和，给出四点函数的例子、一般形式的 Wick 定理及正规序定义。

<!-- date 为整理日期；板书未标明授课日期。正文严格按 Picture/8.2/1.jpg 至 15.jpg 展开。原图引用带目录，以区分不同课次的同名图片。板书产生算符的手写上标 + 排版为 \dagger；收缩连线用配对标记和原图保留。 -->

---

# 1. LSZ 公式回顾与三种微扰方法

对应图片：

- 1

## 板书整理

![[Picture/8.2/1.jpg]]

课堂提醒：考试（Reminder: exam）。

上次课：LSZ 公式。板书用示意式联系散射矩阵元与时间排序关联函数：

$$
\langle f|\widehat S|i\rangle
\sim
\int\cdots\int
\langle\Omega|T\{\phi\cdots\phi\}|\Omega\rangle.
$$

量子场论中的三种微扰论方法（3 perturbation theory methods in QFT）：

1. 拉格朗日方法（Lagrangian），板书以箭头标出本节采用这一方法。
2. 哈密顿方法（Hamiltonian）。
3. 路径积分方法（Path integrals）。

右侧有两幅以 $t$ 为纵轴、$x$ 为横轴的时空示意图：第一幅标出两个同一时刻、空间位置不同的事件，注明“因果不相连”（causally disconnected）；第二幅画出一个事件附近的光线（light ray）和光锥边界，并标示光锥外的另一个事件与其因果不相连。

## 解释

LSZ 公式把散射问题转化为时间排序关联函数的计算问题，因此接下来要建立计算这些关联函数的方法。此处的 $\sim$ 表示回顾性的关系示意，板书没有在本图重写 LSZ 公式中的全部积分核和微分算符。

---

# 2. 拉格朗日微扰论的基本假设

对应图片：

- 2

## 板书整理

![[Picture/8.2/2.jpg]]

标题：拉格朗日微扰论（Lagrangian perturbation theory）。

假设量子场 $\phi(x)$ 是 Lorentz 标量，其等时对易关系为

$$
[\phi(t,\vec x),\phi(t,\vec y)]
=0
=[\dot\phi(t,\vec x),\dot\phi(t,\vec y)],
$$

$$
[\phi(t,\vec x),\dot\phi(t,\vec y)]
=i\delta^3(\vec x-\vec y).
$$

板书在场的等时对易关系旁标注“微观因果性”（micro-causality），并说明在 Klein–Gordon 情形中

$$
\dot\phi=\pi,
\qquad
\dot\phi\equiv\partial_t\phi.
$$

此外，要求

$$
\mathcal E[\phi(x)]=0,
$$

这是一个“算符陈述”（operator statement），其中

$$
\mathcal E[\phi]
\equiv
\frac{\partial\mathcal L}{\partial\phi}
-\partial_\mu
\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\right).
$$

## 解释

这里同时给出场的量子对易结构和运动方程。微观因果性要求类空间隔处的局域场对易；板书中的等时场对易关系体现了这一条件。$\mathcal E[\phi]=0$ 则把 Euler–Lagrange 方程作为量子场的算符关系使用。$\pi=\dot\phi$ 对应这里采用的标准标量场动能项。

---

# 3. 算符运动方程与相互作用势

对应图片：

- 3

## 板书整理

![[Picture/8.2/3.jpg]]

更准确地说，算符等式 $\mathcal E=0$ 意味着：对任意两个态 $|\psi_1\rangle$、$|\psi_2\rangle$ 以及任意算符 $O$，有

$$
\mathcal E=0
\quad\Longleftrightarrow\quad
\langle\psi_1|O\mathcal E|\psi_2\rangle=0.
$$

接下来讨论 **Schwinger–Dyson 方程**。

本节关注的拉格朗日密度为

$$
\mathcal L
=-\frac12(\partial\phi)^2
-\frac{m^2}{2}\phi^2
-V_{\mathrm{int}}(\phi).
$$

因此

$$
\mathcal E[\phi]
=(\Box-m^2)\phi-V'_{\mathrm{int}}(\phi).
$$

由算符运动方程得到

$$
(\Box-m^2)\phi=V'_{\mathrm{int}}(\phi).
$$

板书定义

$$
V'_{\mathrm{int}}\equiv\frac{dV_{\mathrm{int}}}{d\phi},
$$

并给出例子：

$$
V_{\mathrm{int}}=\alpha\phi^3
\quad\Longrightarrow\quad
V'_{\mathrm{int}}=3\alpha\phi^2.
$$

## 解释

运动方程中的相互作用由 $V'_{\mathrm{int}}$ 表示。后续将这个算符方程放入时间排序关联函数，但对整个时间排序乘积求导时，还必须保留时间排序带来的接触项。

这里沿用板书的度规符号：$\Box=-\partial_t^2+\nabla^2$，与 $-\tfrac12(\partial\phi)^2$ 和 $(\Box-m^2)\phi$ 的写法一致。

---

# 4. 从二点函数到一般 Schwinger–Dyson 方程

对应图片：

- 4

## 板书整理

![[Picture/8.2/4.jpg]]

先回顾上一节关于二点函数的关系：

$$
\begin{aligned}
&(-\Box_x+m^2)
\langle\Omega|T\{\phi(x)\phi(y)\}|\Omega\rangle
\\
&\quad=
\langle\Omega|
T\{[(-\Box_x+m^2)\phi(x)]\phi(y)\}
|\Omega\rangle
-i\delta^4(x-y).
\end{aligned}
$$

板书在时间排序内标出

$$
(-\Box_x+m^2)\phi(x)
=-V'_{\mathrm{int}}(\phi(x)).
$$

代入并将等式两边乘以 $-1$，得到

$$
\begin{aligned}
&(\Box_x-m^2)
\langle\Omega|T\{\phi(x)\phi(y)\}|\Omega\rangle
\\
&\quad=
\langle\Omega|
T\{V'_{\mathrm{int}}(\phi(x))\phi(y)\}
|\Omega\rangle
+i\delta^4(x-y).
\end{aligned}
$$

推广（Generalization，标注为 **HW**）：

$$
\boxed{
\begin{aligned}
&(\Box_x-m^2)
\langle\Omega|
T\{\phi(x)\phi(x_1)\cdots\phi(x_N)\}
|\Omega\rangle
\\
&=
\langle\Omega|
T\{V'_{\mathrm{int}}(\phi(x))\phi(x_1)\cdots\phi(x_N)\}
|\Omega\rangle
\\
&\quad+i\sum_{n=1}^{N}\delta^4(x-x_n)
\langle\Omega|
T\{\phi(x_1)\cdots\phi(x_{n-1})
\phi(x_{n+1})\cdots\phi(x_N)\}
|\Omega\rangle.
\end{aligned}
}
$$

这就是板书给出的 **Schwinger–Dyson 方程**。

> 此处使用了时间排序中阶跃函数的求导性质与等时对易关系；一般多点情形的证明留作作业，板书未展开。

## 解释

右侧第一项来自场的运动方程；求和中的每一项则来自 $x$ 与某个 $x_n$ 重合时的接触项。接触项中，$\phi(x)$ 和相应的 $\phi(x_n)$ 都不再出现在剩余的时间排序乘积中，所以它把原关联函数联系到少两个场的关联函数。

---

# 5. 连续对称性与 Noether 流

对应图片：

- 5

## 板书整理

![[Picture/8.2/5.jpg]]

新主题：**Ward–Takahashi 恒等式**。

假设 $\mathcal L$ 具有连续对称性

$$
\phi\longmapsto\phi'
=\phi+\epsilon\Delta_\epsilon.
$$

为简化讨论，假设

$$
K^\mu=0,
\qquad\text{即}\qquad
\mathcal L'=\mathcal L,
$$

并且 $\Delta_\epsilon$ 仅为 $\phi$ 的函数。板书举出的对称性例子为 $U(1)$ 对称性。

由 Noether 定理，

$$
j_\epsilon^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
\Delta_\epsilon.
$$

取 $\mu=0$，有

$$
j_\epsilon^0=\dot\phi\,\Delta_\epsilon.
$$

其散度满足

$$
\partial_\mu j_\epsilon^\mu
=-\mathcal E\Delta_\epsilon
=0.
$$

## 解释

这里用 $\mathcal E=0$ 得到流守恒。$K^\mu=0$ 排除了拉格朗日密度只在相差一个全导数意义下不变的情形；$\Delta_\epsilon$ 不含场的导数这一假设，将用于后面的等时对易子计算。

板书以单个 $\phi$ 简记；所举 $U(1)$ 相位对称性的例子需要复场或相应的多个实分量。此处只记录板书的一般变换形式，没有额外指定该例的场内容。

---

# 6. 对含流的时间排序三点函数求导

对应图片：

- 6

## 板书整理

![[Picture/8.2/6.jpg]]

由流守恒，先有

$$
\langle\Omega|
T\{\partial_\mu j_\epsilon^\mu(x)
\phi(x_1)\cdots\phi(x_N)\}
|\Omega\rangle=0.
$$

接着考虑

$$
\partial_\mu^{(x)}
\langle\Omega|
T\{j_\epsilon^\mu(x)\phi(x_1)\phi(x_2)\}
|\Omega\rangle,
$$

其中板书以箭头注明

$$
x=(t,\vec x),\qquad
x_1=(t_1,\vec x_1),\qquad
x_2=(t_2,\vec x_2).
$$

把时间排序展开为阶跃函数：

$$
\begin{aligned}
&\partial_\mu^{(x)}
\langle\Omega|T\{j_\epsilon^\mu(x)\phi(x_1)\phi(x_2)\}|\Omega\rangle
\\
&=\partial_\mu^{(x)}\Big[
\Theta(t-t_1)\Theta(t_1-t_2)
\langle\Omega|j_\epsilon^\mu(x)\phi(x_1)\phi(x_2)|\Omega\rangle
\\
&\qquad+
\Theta(t_1-t)\Theta(t-t_2)
\langle\Omega|\phi(x_1)j_\epsilon^\mu(x)\phi(x_2)|\Omega\rangle
\\
&\qquad+
\Theta(t_1-t_2)\Theta(t_2-t)
\langle\Omega|\phi(x_1)\phi(x_2)j_\epsilon^\mu(x)|\Omega\rangle
\\
&\qquad+\big(\text{同样三项，作 }x_1\leftrightarrow x_2\big)
\Big].
\end{aligned}
$$

板书标出：导数作用在阶跃函数上时，只有 $\mu=0$ 的部分有贡献；作用在流上时，得到流的散度。第二项阶跃函数下的彩色标记提示，在相应的 $\delta(t-t_1)$ 或 $\delta(t-t_2)$ 支撑上代入重合的时间。

右侧补充计算：

$$
\mathcal L=-\frac12\partial^\mu\phi\,\partial_\mu\phi-\cdots,
$$

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
=-\partial^\mu\phi.
$$

对于 $\mu=0$，

$$
-\partial^0\phi
=\partial_0\phi
=\dot\phi.
$$

## 解释

流守恒使“先求散度，再作时间排序”的关联函数为零，但“先作时间排序，再求散度”还会对阶跃函数求导。上面的六种时间排列，就是后续接触项的来源。右侧的计算说明为什么流的时间分量可以写成 $j_\epsilon^0=\dot\phi\Delta_\epsilon$。

---

# 7. 从阶跃函数导数整理出等时对易子

对应图片：

- 7

## 板书整理

![[Picture/8.2/7.jpg]]

承接上一图，对时间排序展开式求导得到

$$
\begin{aligned}
&\partial_\mu^{(x)}
\langle\Omega|T\{j_\epsilon^\mu(x)\phi(x_1)\phi(x_2)\}|\Omega\rangle
\\
&=
\langle\Omega|T\{\partial_\mu j_\epsilon^\mu(x)
\phi(x_1)\phi(x_2)\}|\Omega\rangle
\\
&\quad+
\delta(t-t_1)\Theta(t_1-t_2)
\Big(
\langle\Omega|j_\epsilon^0(x)\phi(x_1)\phi(x_2)|\Omega\rangle
\\
&\hspace{48mm}
-\langle\Omega|\phi(x_1)j_\epsilon^0(x)\phi(x_2)|\Omega\rangle
\Big)
\\
&\quad+
\delta(t-t_2)\Theta(t_1-t_2)
\Big(
\langle\Omega|\phi(x_1)j_\epsilon^0(x)\phi(x_2)|\Omega\rangle
\\
&\hspace{48mm}
-\langle\Omega|\phi(x_1)\phi(x_2)j_\epsilon^0(x)|\Omega\rangle
\Big)
\\
&\quad+(x_1\leftrightarrow x_2).
\end{aligned}
$$

第一项由流守恒等于零；这里的 $(x_1\leftrightarrow x_2)$ 指交换两个场后得到的接触项。

将括号中的算符差写成对易子，并利用 $\delta$ 函数令相应时间相等：

$$
\begin{aligned}
&\partial_\mu^{(x)}
\langle\Omega|T\{j_\epsilon^\mu(x)\phi(x_1)\phi(x_2)\}|\Omega\rangle
\\
&=
\delta(t-t_1)\Theta(t_1-t_2)
\langle\Omega|
[j_\epsilon^0(t_1,\vec x),\phi(t_1,\vec x_1)]
\phi(x_2)|\Omega\rangle
\\
&\quad+
\delta(t-t_2)\Theta(t_1-t_2)
\langle\Omega|
\phi(x_1)
[j_\epsilon^0(t_2,\vec x),\phi(t_2,\vec x_2)]
|\Omega\rangle
\\
&\quad+(x_1\leftrightarrow x_2).
\end{aligned}
$$

> 此处使用了 $\partial_t\Theta(t-t_i)=\delta(t-t_i)$、$\partial_t\Theta(t_i-t)=-\delta(t_i-t)$，以及 $\delta(t-t_i)$ 对时间变量的限制。

## 解释

每当流的时间跨过某个场的时间，时间排序中的算符顺序就会改变。跨越前后的差形成流与该场的等时对易子，因此可以用前面给出的正则对易关系继续计算。

---

# 8. 计算流与场的对易子并合并接触项

对应图片：

- 8

## 板书整理

![[Picture/8.2/8.jpg]]

先计算

$$
\begin{aligned}
&[j_\epsilon^0(t_1,\vec x),\phi(t_1,\vec x_1)]
\\
&\quad=
[\dot\phi(t_1,\vec x)\Delta_\epsilon(\phi),
\phi(t_1,\vec x_1)]
\\
&\quad=
\dot\phi\,[\Delta_\epsilon(\phi),\phi]
+\Delta_\epsilon(\phi)[\dot\phi,\phi].
\end{aligned}
$$

板书在第一项下标注

$$
[\Delta_\epsilon(\phi),\phi]=0,
\qquad\text{因为}\qquad
[\phi,\phi]=0,
$$

并在第二个对易子下标注

$$
[\dot\phi(t_1,\vec x),\phi(t_1,\vec x_1)]
=-i\delta^3(\vec x-\vec x_1).
$$

因此，代回上一图的结果：

$$
\begin{aligned}
&\partial_\mu^{(x)}
\langle\Omega|T\{j_\epsilon^\mu(x)\phi(x_1)\phi(x_2)\}|\Omega\rangle
\\
&=-i\delta^4(x-x_1)\Theta(t_1-t_2)
\langle\Omega|\Delta_\epsilon(\phi(x_1))\phi(x_2)|\Omega\rangle
\\
&\quad-i\delta^4(x-x_2)\Theta(t_1-t_2)
\langle\Omega|\phi(x_1)\Delta_\epsilon(\phi(x_2))|\Omega\rangle
\\
&\quad+(x_1\leftrightarrow x_2).
\end{aligned}
$$

将交换后的项一起合并回时间排序，最终得到

$$
\begin{aligned}
&\partial_\mu^{(x)}
\langle\Omega|T\{j_\epsilon^\mu(x)\phi(x_1)\phi(x_2)\}|\Omega\rangle
\\
&=-i\delta^4(x-x_1)
\langle\Omega|
T\{\Delta_\epsilon(\phi(x_1))\phi(x_2)\}
|\Omega\rangle
\\
&\quad-i\delta^4(x-x_2)
\langle\Omega|
T\{\phi(x_1)\Delta_\epsilon(\phi(x_2))\}
|\Omega\rangle.
\end{aligned}
$$

> 此处使用了 $\delta(t-t_i)\delta^3(\vec x-\vec x_i)=\delta^4(x-x_i)$。$\Delta_\epsilon$ 只依赖于场本身，所以它与等时的 $\phi$ 对易；$[\dot\phi,\phi]$ 又是与单位算符成比例的分布，因而板书中第二项的排列不改变结果。

## 解释

每个接触项都把与流重合的那个场替换为其对称变换 $\Delta_\epsilon(\phi)$，其余场保持原样。负号来自 $[\dot\phi,\phi]=-i\delta^3$，这与 Schwinger–Dyson 方程中的接触项符号来源不同。

---

# 9. 一般 Ward–Takahashi 恒等式

对应图片：

- 9

## 板书整理

![[Picture/8.2/9.jpg]]

推广（Generalization，标注为 **HW**）：

$$
\boxed{
\begin{aligned}
&\partial_\mu^{(x)}
\langle\Omega|
T\{j_\epsilon^\mu(x)\phi(x_1)\cdots\phi(x_N)\}
|\Omega\rangle
\\
&=-i\sum_{n=1}^{N}\delta^4(x-x_n)
\langle\Omega|
T\{\phi(x_1)\cdots\phi(x_{n-1})
\Delta_\epsilon(\phi(x_n))
\phi(x_{n+1})\cdots\phi(x_N)\}
|\Omega\rangle.
\end{aligned}
}
$$

板书将此命名为 **Ward–Takahashi 恒等式**。

> 此处沿用前面逐项求导和等时对易子的计算；一般多点推广留作作业，板书没有另写完整证明。

## 解释

这个恒等式把流守恒转化为对关联函数的约束。对时间排序的含流关联函数求散度，所得结果是在每个场插入点处出现的接触项之和；每一项都对应那个场的无穷小对称变换。

---

# 10. 费曼规则的准备：场、传播子与接触项的简记

对应图片：

- 10

## 板书整理

![[Picture/8.2/10.jpg]]

新主题：**费曼规则（Feynman rules）**。

先引入记号（Notations）：

$$
\delta_{xy}\equiv\delta^4(x-y),
\qquad\text{或}\qquad
\delta_{12}\equiv\delta^4(x_1-x_2),
$$

$$
\phi_x\equiv\phi(x),
\qquad\text{或}\qquad
\phi_1\equiv\phi(x_1),
$$

$$
D_{xy}\equiv D_F(x-y),
\qquad\text{或}\qquad
D_{12}\equiv D_F(x_1-x_2).
$$

回顾费曼传播子满足的方程：

$$
(\Box_x-m^2)D_F(x-y)=i\delta^4(x-y).
$$

使用新记号写为

$$
(\Box_x-m^2)D_{xy}=i\delta_{xy}.
$$

## 解释

下标 $x,y$ 或 $1,2$ 在这里代表时空点。把长的坐标依赖压缩成下标后，可以更清楚地表示传播子与多点函数之间的运算；这些简记不改变传播子的定义。

---

# 11. DeWitt 记号与关联函数的一个命题

对应图片：

- 11

## 板书整理

![[Picture/8.2/11.jpg]]

**DeWitt 记号**：重复出现的时空指标隐含对该变量的四维积分。

例：

$$
\begin{aligned}
D_{xy}\delta_{yz}
&\equiv\int d^4y\,D_F(x-y)\delta^4(y-z)
\\
&=D_F(x-z)
\\
&=D_{xz}.
\end{aligned}
$$

另外，定义时间排序真空期望值的简记：

$$
\langle O\rangle
\equiv
\langle\Omega|T\{O\}|\Omega\rangle.
$$

板书将 $D_{12}$ 画成连接两个端点 $x_1$ 和 $x_2$ 的一条线：

$$
D_{12}\equiv
\overset{x_1}{\circ}\!\text{────────}\!\overset{x_2}{\circ}.
$$

随后提出命题（Proposition）：

$$
\boxed{
\langle\phi_1\cdots\phi_N\rangle
=-iD_{x1}(\Box_x-m^2)
\langle\phi_x\phi_2\cdots\phi_N\rangle.
}
$$

## 解释

命题右侧隐含对 $x$ 的积分，$(\Box_x-m^2)$ 作用在其后的关联函数上。它表示：可以先对关联函数中的一个坐标施加运动方程算符，再通过传播子积分恢复原来的关联函数。下一张板书给出证明。

---

# 12. 命题的证明与自由场关联函数的递推关系

对应图片：

- 12

## 板书整理

![[Picture/8.2/12.jpg]]

**证明。** 首先用 $\delta$ 函数选出 $x=x_1$：

$$
\langle\phi_1\cdots\phi_N\rangle
=\delta_{x1}\langle\phi_x\phi_2\cdots\phi_N\rangle.
$$

由传播子方程，将 $\delta_{x1}$ 改写为

$$
\langle\phi_1\cdots\phi_N\rangle
=-i\big[(\Box_x-m^2)D_{x1}\big]
\langle\phi_x\phi_2\cdots\phi_N\rangle.
$$

再作分部积分（板书标注 **IBP**），得到

$$
\langle\phi_1\cdots\phi_N\rangle
=-iD_{x1}(\Box_x-m^2)
\langle\phi_x\phi_2\cdots\phi_N\rangle.
$$

> 此处使用了分部积分，将二阶微分算符从传播子移到关联函数上；这一步沿用可舍去边界项的处理。以上各式中的 $x$ 均按 DeWitt 记号积分。

接下来先考虑**自由理论**：

$$
V_{\mathrm{int}}=0,
\qquad
(\Box_x-m^2)\phi_x=0.
$$

Schwinger–Dyson 方程化为

$$
\begin{aligned}
&(\Box_x-m^2)
\langle\phi_x\phi_2\cdots\phi_N\rangle
\\
&\quad=i\sum_{n=2}^{N}\delta_{xn}
\langle\phi_2\cdots\phi_{n-1}\phi_{n+1}\cdots\phi_N\rangle.
\end{aligned}
$$

代入刚刚证明的命题：

$$
\begin{aligned}
\langle\phi_1\cdots\phi_N\rangle
&=D_{x1}\sum_{n=2}^{N}\delta_{xn}
\langle\phi_2\cdots\phi_{n-1}\phi_{n+1}\cdots\phi_N\rangle
\\
&=\sum_{n=2}^{N}D_{1n}
\langle\phi_2\cdots\phi_{n-1}\phi_{n+1}\cdots\phi_N\rangle.
\end{aligned}
$$

右侧另注明

$$
D_{xy}=D_{yx},
\qquad
\delta_{xy}=\delta_{yx}.
$$

> 此处使用了 $(-i)i=1$、$\delta$ 函数积分，以及传播子的对称性：$D_{x1}\delta_{xn}=D_{n1}=D_{1n}$。

## 解释

递推关系把 $\phi_1$ 依次与其他任意一个场 $\phi_n$ 配成一对，产生 $D_{1n}$，并留下少两个场的关联函数。虽然自由场满足齐次运动方程，其时间排序关联函数仍有接触项，因此上面的递推关系不会因自由场方程而变成零。

---

# 13. 继续递推：奇数点函数与完全收缩

对应图片：

- 13

## 板书整理

![[Picture/8.2/13.jpg]]

承接上一图，板书继续写出下一层递推：

$$
\begin{aligned}
\langle\phi_1\cdots\phi_N\rangle
&=\sum_{n=2}^{N}D_{1n}
\sum_{\substack{m=3\\m\ne n}}^{N}D_{2m}
\\
&\qquad\times
\langle\phi_3\cdots\phi_{n-1}\phi_{n+1}\cdots
\phi_{m-1}\phi_{m+1}\cdots\phi_N\rangle,
\end{aligned}
$$

并写明“etc.”：如此继续。每一步从期望值中移去两个 $\phi$。

**若 $N$ 为奇数**，递推最终留下一个场的期望值：

$$
\langle\phi_1\cdots\phi_N\rangle
=\sum\cdots\sum D\cdots D\,\langle\phi\rangle
=0,
$$

因为

$$
\langle\phi(x_n)\rangle=0.
$$

**若 $N$ 为偶数**，板书用连续求和示意：

$$
\begin{aligned}
\langle\phi_1\cdots\phi_N\rangle
&=\sum_{n=2}^{N}
\sum_{\substack{m=3\\n\ne m}}^{N}
\sum_{\substack{\ell=4\\\ell\ne n,m}}^{N}
\cdots
\\
&\qquad\times
D_{1n}D_{2m}D_{3\ell}\cdots\langle\Omega|\Omega\rangle.
\end{aligned}
$$

红字补充注明：

- $D_{2m}$：“except if $n=2$”（若 $n=2$ 则例外）。
- $D_{3\ell}$：“except if $m=3$”（若 $m=3$ 则例外）。
- $\langle\Omega|\Omega\rangle=1$。

最终写为

$$
\langle\phi_1\cdots\phi_N\rangle
=\text{所有完全收缩（full contractions）之和}.
$$

> [!warning]
> **板书检查提醒**
>
> 位置：图片 13，第一行的二重求和及下方偶数点函数的连续求和。
>
> 板书内容：每个分支都继续写成 $D_{1n}D_{2m}D_{3\ell}\cdots$；红字分别注明 $n=2$、$m=3$ 时的例外。
>
> 检查结果：这是递推的示意写法，若把所写求和限直接当作统一公式使用，会重复配对已经移去的场；第一行尚未区分 $n=2$ 的分支，下方红字也未列出全部例外。
>
> 说明：当 $n=2$ 时，第一次递推已经给出 $D_{12}\langle\phi_3\cdots\phi_N\rangle$，下一步应从剩余的场中选取配对，不能再引入 $D_{2m}$。同样，若 $n=3$，$\phi_3$ 也已移去，不能再出现 $D_{3\ell}$；因此它的例外不只限于板书所注的 $m=3$。各步应从尚未配对的指标中继续选择，最终“所有完全收缩之和”的结论与上一图的递推关系一致。
>
> 注意：以上为检查提示，未修改原板书公式及红字注释。

## 解释

自由理论中，每一次递推都形成一个传播子并减少两个场。奇数个场最终留下零的一点函数；偶数个场可以全部成对，最后只剩归一化的真空内积。这里的奇数点函数为零及完全收缩结论，承接上一图的自由理论条件。

---

# 14. 收缩的定义与自由场四点函数

对应图片：

- 14

## 板书整理

![[Picture/8.2/14.jpg]]

**收缩（Contraction）**：板书在两个场上方画连接线，定义为

$$
\overbrace{\phi_1\phi_2}^{\text{收缩}}
\equiv D_{12}.
$$

例：四点函数。原板书通过场上方的连线表示三种配对；以下在每项下方标出相同的配对关系，保留场的排列顺序：

$$
\begin{aligned}
\langle\phi_1\phi_2\phi_3\phi_4\rangle
&=
\underbrace{\langle\phi_1\phi_2\phi_3\phi_4\rangle}
_{\text{收缩 }(1,2),(3,4)}
\\
&\quad+
\underbrace{\langle\phi_1\phi_2\phi_3\phi_4\rangle}
_{\text{收缩 }(1,3),(2,4)}
\\
&\quad+
\underbrace{\langle\phi_1\phi_2\phi_3\phi_4\rangle}
_{\text{收缩 }(1,4),(2,3)}.
\end{aligned}
$$

这里下方的“收缩”标记是各项定义的一部分：每项均指按所标配对完成收缩后的表达式。

板书注明：

1. **完全收缩（Full contraction）**：所有场都必须被收缩。
2. **顺序不重要（Order does not matter）**。

因此

$$
\boxed{
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=D_{12}D_{34}+D_{13}D_{24}+D_{23}D_{14}.
}
$$

板书下方把三项分别画为两条传播子线：

- 第一幅：上方连 $x_1$ 与 $x_2$，下方连 $x_3$ 与 $x_4$，对应 $D_{12}D_{34}$。
- 第二幅：左侧连 $x_1$ 与 $x_3$，右侧连 $x_2$ 与 $x_4$，对应 $D_{13}D_{24}$。
- 第三幅：两条线交叉，分别连 $x_2$ 与 $x_3$、$x_1$ 与 $x_4$，对应 $D_{23}D_{14}$；交叉位置没有另画顶点。

## 解释

四个场的完全收缩有三种不同配对，每种配对给出两个传播子的乘积。本节讨论的是标量玻色场，所以调换配对内的两个端点或传播子因子的排列不改变该项；板书中的“顺序不重要”应在这一语境下理解。

---

# 15. 一般形式的 Wick 定理与正规序

对应图片：

- 15

## 板书整理

![[Picture/8.2/15.jpg]]

**Wick 定理的一般形式（General version of Wick theorem）**：

$$
\boxed{
T\{\phi_1\cdots\phi_N\}
=\mathcal N\left\{
\phi_1\cdots\phi_N
+\big(\text{所有收缩项}\big)
\right\}.
}
$$

$\mathcal N$ 是**正规序符号（normal ordering symbol）**：把所有产生算符 $a_{\vec p}^{\dagger}$ 移到所有湮灭算符 $a_{\vec p}$ 的左边。

板书例子：

$$
\mathcal N\left\{
a_{\vec p}a_{\vec q}^{\dagger}a_{\vec k}
\right\}
=a_{\vec q}^{\dagger}a_{\vec p}a_{\vec k}.
$$

## 解释

这里的“所有收缩项”包含部分收缩和完全收缩：每个收缩对替换为对应传播子，未收缩的场保留在正规序内；原式中的第一项则是不作收缩的项。承接前面的自由场条件，对此算符等式取真空期望值时，含未收缩场的正规序项为零，于是得到前面使用的完全收缩之和。

正规序是一种规定的排列操作，板书例子是在定义该操作；它并不是声称原来的非正规序乘积与重排后的乘积直接相等。

---

# 本节知识结构

LSZ 公式回顾与三种微扰方法（图 1）  
↓  
拉格朗日形式：Lorentz 标量场、等时对易关系与算符运动方程（图 2）  
↓  
相互作用势及 $(\Box-m^2)\phi=V'_{\mathrm{int}}(\phi)$（图 3）  
↓  
二点函数接触项与一般 Schwinger–Dyson 方程（图 4）  
↓  
连续对称性与 Noether 流（图 5）  
↓  
展开含流的时间排序三点函数（图 6）  
↓  
对阶跃函数求导，整理为等时对易子（图 7）  
↓  
计算对易子，合并为对称变换的接触项（图 8）  
↓  
一般 Ward–Takahashi 恒等式（图 9）  
↓  
费曼规则的准备：传播子与场的简记（图 10）  
↓  
DeWitt 记号、传播子线及关联函数命题（图 11）  
↓  
分部积分证明与自由场多点函数递推（图 12）  
↓  
奇数点函数为零，偶数点函数为完全收缩之和（图 13）  
↓  
收缩定义、四点函数及三种配对图（图 14）  
↓  
一般 Wick 定理与正规序（图 15）。

课堂标注的作业：图 4 的多点 Schwinger–Dyson 方程推广，以及图 9 的多点 Ward–Takahashi 恒等式推广。

---

# 核心公式清单

下表按课堂出现顺序汇总。表中 $\langle O\rangle\equiv\langle\Omega|T\{O\}|\Omega\rangle$，$\phi_n\equiv\phi(x_n)$；$\widehat{\phi_n}$ 表示省略该场，仅为表格中的紧凑记法。涉及 $D_{x1}$ 与重复坐标 $x$ 的式子沿用 DeWitt 积分约定。自由场递推、完全收缩和 Wick 定理均在本节自由理论的条件下使用。

| 公式 | 含义 |
| ----- | ---- |
| $\langle f\vert\widehat S\vert i\rangle\sim\int\cdots\int\langle\phi\cdots\phi\rangle$ | LSZ 公式的课堂回顾示意，不是完整公式 |
| $[\phi(t,\vec x),\phi(t,\vec y)]=[\dot\phi(t,\vec x),\dot\phi(t,\vec y)]=0$ | 等时场—场及时间导数—时间导数对易关系 |
| $[\phi(t,\vec x),\dot\phi(t,\vec y)]=i\delta^3(\vec x-\vec y)$ | 等时正则对易关系，标准动能下 $\pi=\dot\phi$ |
| $\mathcal E[\phi]=\dfrac{\partial\mathcal L}{\partial\phi}-\partial_\mu\dfrac{\partial\mathcal L}{\partial(\partial_\mu\phi)}=0$ | 算符 Euler–Lagrange 方程 |
| $\mathcal E=0\Longleftrightarrow\langle\psi_1\vert O\mathcal E\vert\psi_2\rangle=0$ | 算符等式对任意态与算符插入的含义 |
| $\mathcal L=-\tfrac12(\partial\phi)^2-\tfrac{m^2}{2}\phi^2-V_{\mathrm{int}}(\phi)$ | 本节采用的标量场拉格朗日密度 |
| $\mathcal E[\phi]=(\Box-m^2)\phi-V'_{\mathrm{int}}(\phi)$ | 代入拉格朗日密度得到的运动方程表达式 |
| $(\Box-m^2)\phi=V'_{\mathrm{int}}(\phi)$ | 相互作用场的算符运动方程 |
| $V'_{\mathrm{int}}=dV_{\mathrm{int}}/d\phi$；$V_{\mathrm{int}}=\alpha\phi^3\Rightarrow V'_{\mathrm{int}}=3\alpha\phi^2$ | 相互作用势的导数及板书例子 |
| $(\Box_x-m^2)\langle\phi(x)\phi(y)\rangle=\langle V'_{\mathrm{int}}(\phi(x))\phi(y)\rangle+i\delta^4(x-y)$ | 二点 Schwinger–Dyson 方程 |
| $(\Box_x-m^2)\langle\phi(x)\phi_1\cdots\phi_N\rangle=\langle V'_{\mathrm{int}}(\phi(x))\phi_1\cdots\phi_N\rangle+i\sum_{n=1}^N\delta^4(x-x_n)\langle\phi_1\cdots\widehat{\phi_n}\cdots\phi_N\rangle$ | 一般 Schwinger–Dyson 方程 |
| $\phi'=\phi+\epsilon\Delta_\epsilon$，$K^\mu=0$，$\mathcal L'=\mathcal L$ | 本节连续对称性的假设，$\Delta_\epsilon$ 仅依赖于场 |
| $j_\epsilon^\mu=\dfrac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\Delta_\epsilon$，$j_\epsilon^0=\dot\phi\Delta_\epsilon$ | Noether 流及其时间分量 |
| $\partial_\mu j_\epsilon^\mu=-\mathcal E\Delta_\epsilon=0$ | 算符运动方程给出的流守恒 |
| $[j_\epsilon^0(t,\vec x),\phi(t,\vec y)]=-i\Delta_\epsilon(\phi(t,\vec x))\delta^3(\vec x-\vec y)$ | 由板书的对易子计算合并得到的接触项系数 |
| $\partial_\mu^{(x)}\langle j_\epsilon^\mu(x)\phi_1\cdots\phi_N\rangle=-i\sum_{n=1}^N\delta^4(x-x_n)\langle\phi_1\cdots\phi_{n-1}\Delta_\epsilon(\phi_n)\phi_{n+1}\cdots\phi_N\rangle$ | 一般 Ward–Takahashi 恒等式 |
| $\delta_{xy}=\delta^4(x-y)$，$\phi_x=\phi(x)$，$D_{xy}=D_F(x-y)$ | 接触项、场与传播子的简记 |
| $(\Box_x-m^2)D_{xy}=i\delta_{xy}$ | 费曼传播子方程 |
| $D_{xy}\delta_{yz}=\int d^4y\,D_F(x-y)\delta^4(y-z)=D_{xz}$ | DeWitt 隐含积分约定的例子 |
| $\langle O\rangle=\langle\Omega\vert T\{O\}\vert\Omega\rangle$ | 时间排序真空期望值的简记 |
| $\langle\phi_1\cdots\phi_N\rangle=-iD_{x1}(\Box_x-m^2)\langle\phi_x\phi_2\cdots\phi_N\rangle$ | 传播子与分部积分得到的命题 |
| $V_{\mathrm{int}}=0$，$(\Box_x-m^2)\phi_x=0$ | 自由理论条件 |
| $(\Box_x-m^2)\langle\phi_x\phi_2\cdots\phi_N\rangle=i\sum_{n=2}^N\delta_{xn}\langle\phi_2\cdots\widehat{\phi_n}\cdots\phi_N\rangle$ | 自由场 Schwinger–Dyson 方程 |
| $\langle\phi_1\cdots\phi_N\rangle=\sum_{n=2}^N D_{1n}\langle\phi_2\cdots\widehat{\phi_n}\cdots\phi_N\rangle$ | 自由场多点函数的递推关系 |
| $D_{xy}=D_{yx}$，$\delta_{xy}=\delta_{yx}$ | 标量传播子及接触项的对称性 |
| $\langle\phi(x_n)\rangle=0$，$\langle\Omega\vert\Omega\rangle=1$ | 递推的终点 |
| $N$ 为奇数：$\langle\phi_1\cdots\phi_N\rangle=0$ | 自由理论的奇数点函数 |
| $N$ 为偶数：$\langle\phi_1\cdots\phi_N\rangle=\text{所有完全收缩之和}$ | 自由理论的偶数点函数 |
| $\overbrace{\phi_1\phi_2}^{\text{收缩}}=D_{12}$ | 一对场的收缩 |
| $\langle\phi_1\phi_2\phi_3\phi_4\rangle=D_{12}D_{34}+D_{13}D_{24}+D_{23}D_{14}$ | 自由场四点函数的三种完全收缩 |
| $T\{\phi_1\cdots\phi_N\}=\mathcal N\{\phi_1\cdots\phi_N+(\text{所有收缩项})\}$ | 一般形式的 Wick 定理 |
| $\mathcal N\{a_{\vec p}a_{\vec q}^{\dagger}a_{\vec k}\}=a_{\vec q}^{\dagger}a_{\vec p}a_{\vec k}$ | 正规序的板书例子 |



