---
title: "量子场论导论 Lecture 9.1"
date: 2026-11-03
tags:
  - 量子场论导论
  - lecture
  - Wick定理
  - 费曼规则
  - 对称因子
  - 蝌蚪图抵消
  - 反项
source: "课堂板书"
---

# Lecture 9.1: 相互作用理论的微扰展开、费曼规则与蝌蚪图抵消

## 本节内容概览

本节先回顾 Schwinger–Dyson 方程与 Wick 定理，说明自由场时间排序乘积的真空期望值只保留完全收缩。随后以三次相互作用为例，逐步计算二点函数至二阶，并将各项表示为费曼图。课堂接着给出一般多项式相互作用的位置空间费曼规则，解释顶点的阶乘约定和图的对称因子。最后从一点函数非零的问题出发，引入线性反项，推导蝌蚪图抵消条件，并指出重合点传播子所含的发散。

<!-- date 为整理日期；板书未标明授课日期。正文依次整理 Picture/9.1/1.jpg 至 15.jpg。原图引用保留目录，避免与其他课次的同名图片混淆。收缩连线用传播子 D_{ij} 排版，并在文字中保留配对关系；费曼图同时保留原图与连接结构说明。反项系数的手写 Y 统一排版为 Y。 -->

---

# 1. 上节回顾：传播子恒等式与 Wick 定理

对应图片：

- 1

## 板书整理

![[Picture/9.1/1.jpg]]

课堂提醒：考试（Reminder: exam）。

上次课的内容（Last time）：

- Schwinger–Dyson 方程。
- Ward–Takahashi 恒等式。
- 微扰论与费曼图。

板书右上角回顾：

$$
\langle\phi_1\cdots\phi_N\rangle
=-iD_{x1}(\Box_x-m^2)
\langle\phi_x\phi_2\cdots\phi_N\rangle.
\tag{1}
$$

这里的式号 $(1)$ 沿用后续板书对这条关系的援引。

自由理论：

$$
V_{\mathrm{int}}=0.
$$

Wick 定理：

$$
T\{\phi_1\cdots\phi_N\}
=\mathcal N\!\left\{
\phi_1\cdots\phi_N+
\bigl(\text{所有收缩项}\bigr)
\right\}.
$$

板书将“所有收缩项”分成：

$$
\text{所有收缩项}
=\text{部分收缩项}+\text{完全收缩项}.
$$

完全收缩项不再含有场算符 $\phi$。

收缩（contraction）的定义与图示：

$$
\text{$\phi_1$ 与 $\phi_2$ 的收缩}
\equiv D_{12}
\equiv \text{连接 $x_1$ 与 $x_2$ 的一条线}.
$$

## 解释

$\mathcal N$ 表示正规序，$T$ 表示时间排序。沿用课堂简记，$\phi_i=\phi(x_i)$，尖括号表示时间排序的真空关联函数；下标 $\mathrm{free}$ 出现时，特指自由理论。式 $(1)$ 中内部时空标签 $x$ 隐含积分，后续公式中的内部顶点也采用这一简记：每个内部顶点的位置积分一次，$D_{xx}$ 本身表示重合点传播子。

式 $(1)$ 用自由传播子作为微分算符 $\Box-m^2$ 的逆核。后面会反复使用它，将相互作用关联函数中的一个外部场换成微分算符作用下的关联函数。

---

# 2. 真空期望值中的完全收缩与四场例子

对应图片：

- 2

## 板书整理

![[Picture/9.1/2.jpg]]

把完全收缩项单独提出：

$$
T\{\phi_1\cdots\phi_N\}
=\mathcal N\!\left\{
\phi_1\cdots\phi_N+
\bigl(\text{部分收缩项}\bigr)
\right\}
+\bigl(\text{完全收缩项}\bigr).
$$

板书注明：

$$
\langle0|\mathcal N\{\text{anything}\}|0\rangle=0,
$$

但**不再含有任何 $\phi$ 的项除外**。

因此：

$$
\langle0|T\{\phi_1\cdots\phi_N\}|0\rangle
=\text{所有完全收缩项之和}.
$$

例：四个场的时间排序乘积。板书先写无收缩项，再画出 $(1,2)$、$(1,3)$ 两种部分收缩，最后在下一行画出 $(1,2)(3,4)$ 的完全收缩：

$$
\begin{aligned}
T\{\phi_1\phi_2\phi_3\phi_4\}
={}&\mathcal N\!\left\{
\phi_1\phi_2\phi_3\phi_4
+D_{12}\phi_3\phi_4
+D_{13}\phi_2\phi_4
+\cdots
\right\}\\
&+D_{12}D_{34}+\cdots.
\end{aligned}
$$

省略号沿用原板书，表示其余收缩方式；这里没有把板书的例子改写成另一套推导。

## 解释

自由真空中，只要正规序乘积仍含有场算符，其真空期望值就为零。完全收缩后留下的是传播子的乘积，因此自由场多点关联函数的计算转化为配对计数。

---

# 3. 三次相互作用与二点函数的递推起点

对应图片：

- 3

## 板书整理

![[Picture/9.1/3.jpg]]

相互作用理论：

$$
V_{\mathrm{int}}=\frac{g}{3!}\phi^3
\quad\Longrightarrow\quad
V'_{\mathrm{int}}=\frac{g}{2!}\phi^2.
$$

板书标注：$3!$ 是约定性的归一化因子（conventional），$g$ 是耦合常数（coupling constant）。

Schwinger–Dyson 方程：

$$
\begin{aligned}
(\Box_x-m^2)
\langle\phi_x\phi_2\cdots\phi_N\rangle
={}&\left\langle
\frac g2\phi_x^2\phi_2\cdots\phi_N
\right\rangle\\
&+i\sum_{n=2}^{N}\delta_{xn}
\langle\phi_2\cdots\phi_{n-1}\phi_{n+1}\cdots\phi_N\rangle.
\end{aligned}
\tag{2}
$$

考虑二点函数。先使用式 $(1)$：

$$
\langle\phi_1\phi_2\rangle
\overset{(1)}=
-iD_{x1}(\Box_x-m^2)
\langle\phi_x\phi_2\rangle.
$$

再代入式 $(2)$：

$$
\langle\phi_1\phi_2\rangle
\overset{(2)}=
-iD_{x1}\left[
\frac g2\langle\phi_x^2\phi_2\rangle
+i\delta_{x2}
\right].
$$

板书关于微扰论的说明：

$$
|g|\ll\text{“}1\text{”}.
$$

更准确地说，假设结果可以按 $g$ 作级数展开。

## 解释

$\delta_{xn}$ 表示 $\delta^{(4)}(x-x_n)$。接触项移除了 $\phi_x$ 与 $\phi_n$，而相互作用项用 $\phi_x^2$ 替换了 $\phi_x$，从而把不同场数的关联函数联系起来。

板书给“$1$”加了引号，并进一步说明要假设结果能按 $g$ 展开。这里关注的是逐阶求解的组织方式，不把“$|g|\ll1$”理解成脱离量纲和所考察尺度的独立条件。

---

# 4. 再次使用 Schwinger–Dyson 方程：二点函数展开到二阶所需的量

对应图片：

- 4

## 板书整理

![[Picture/9.1/4.jpg]]

接上图，先处理接触项：

$$
\langle\phi_1\phi_2\rangle
=-\frac{ig}{2}D_{x1}\langle\phi_x^2\phi_2\rangle+D_{12}.
$$

接着对三场关联函数中的 $\phi_2$ 使用式 $(1)$：

$$
\langle\phi_x^2\phi_2\rangle
=-iD_{y2}(\Box_y-m^2)
\langle\phi_x^2\phi_y\rangle.
$$

板书以红字将其中的三场关联函数写成 $\langle\phi_x\phi_x\phi_y\rangle$，强调两个场都位于 $x$。

对括号中微分算符作用的部分使用式 $(2)$：

$$
(\Box_y-m^2)\langle\phi_x^2\phi_y\rangle
=\left\langle\frac g2\phi_y^2\phi_x^2\right\rangle
+2i\delta_{yx}\langle\phi_x\rangle.
$$

> 此处使用了 Schwinger–Dyson 方程中的接触项求和；两个同在 $x$ 点的场分别给出一个相同的接触项。

代回二点函数：

$$
\langle\phi_1\phi_2\rangle
=D_{12}
-\frac{ig}{2}D_{x1}
\left[
-\frac{ig}{2}D_{y2}\langle\phi_x^2\phi_y^2\rangle
+2D_{x2}\langle\phi_x\rangle
\right].
$$

展开系数后：

$$
\langle\phi_1\phi_2\rangle
=D_{12}
-\frac{g^2}{4}D_{x1}D_{y2}
\langle\phi_x^2\phi_y^2\rangle
-igD_{x1}D_{x2}\langle\phi_x\rangle.
$$

板书在四场关联函数下方注明：

$$
\langle\phi_x^2\phi_y^2\rangle
=\langle\phi_x^2\phi_y^2\rangle_{\mathrm{free}}
+O(g),
\qquad \mathrm{free}:\ g=0.
$$

由于这一项前已有 $g^2$，若只求结果至 $O(g^2)$，可忽略四场关联函数中的 $O(g)$ 修正。

对最后一项，板书标注：需要把 $\langle\phi_x\rangle$ 求到 $O(g)$。

## 解释

微扰阶数由“显式耦合因子”与“关联函数本身的展开阶数”共同决定。因此，二点函数算到二阶只需要自由四场关联函数和一阶一点函数；并不需要把所有中间关联函数都算到二阶。

---

# 5. 一点函数的一阶结果与自由四场收缩

对应图片：

- 5

## 板书整理

![[Picture/9.1/5.jpg]]

先计算一点函数：

$$
\langle\phi_x\rangle
\overset{(1)}=
-iD_{xy}(\Box_y-m^2)\langle\phi_y\rangle.
$$

板书在微分算符作用的部分下方写出：

$$
(\Box_y-m^2)\langle\phi_y\rangle
=\frac g2\langle\phi_y^2\rangle+0
=\frac g2\langle\phi_y^2\rangle_{\mathrm{free}}+O(g^2).
$$

这里的 $+0$ 对应没有其他外部场可产生接触项。

因此：

$$
\langle\phi_x\rangle
=-\frac{ig}{2}D_{xy}\langle\phi_y^2\rangle_{\mathrm{free}}
+O(g^2).
$$

使用 Wick 定理：

$$
\langle\phi_y^2\rangle_{\mathrm{free}}=D_{yy}.
$$

另外，对前面需要的四场关联函数：

$$
\langle\phi_x^2\phi_y^2\rangle_{\mathrm{free}}
\overset{\mathrm{Wick}}=
D_{xx}D_{yy}+2D_{xy}^2.
$$

## 解释

四场收缩中，两个 $x$ 点的场相互收缩、两个 $y$ 点的场相互收缩，给出 $D_{xx}D_{yy}$。把两个 $x$ 点的场分别与两个 $y$ 点的场配对共有两种方式，给出 $2D_{xy}^2$。板书在此保留的是足以完成前一步二阶计算的精度。

---

# 6. 二点函数的二阶结果及其费曼图

对应图片：

- 6

## 板书整理

![[Picture/9.1/6.jpg]]

将上一部分的结果代回，板书最终得到：

$$
\begin{aligned}
\langle\phi_1\phi_2\rangle
=D_{12}-g^2\Bigl[
&\frac14D_{x1}D_{y2}D_{xx}D_{yy}
+\frac12D_{x1}D_{y2}D_{xy}^2\\
&+\frac12D_{x1}D_{x2}D_{xy}D_{yy}
\Bigr]+O(g^3).
\end{aligned}
$$

板书随后按同一顺序画出四种图，并在左侧再次写明：

$$
V_{\mathrm{int}}=\frac{g}{3!}\phi^3.
$$

图形与上式各项一一对应：

| 顺序 | 原图的连接结构 | 对应的传播子乘积及系数 |
| --- | --- | --- |
| 1 | 外点 $x_1$ 与 $x_2$ 直接用一条线连接 | $D_{12}$ |
| 2 | $x_1$ 连到 $x$，$x$ 上有自环；另一个独立部分由 $y$ 上的自环与通向 $x_2$ 的线组成 | $-\frac{g^2}{4}D_{x1}D_{y2}D_{xx}D_{yy}$ |
| 3 | $x_1$ 连到 $x$，$x$ 与 $y$ 之间有两条线，$y$ 再连到 $x_2$ | $-\frac{g^2}{2}D_{x1}D_{y2}D_{xy}^2$ |
| 4 | $x_1$、$x_2$ 都连到 $x$，$x$ 再连到带自环的 $y$ | $-\frac{g^2}{2}D_{x1}D_{x2}D_{xy}D_{yy}$ |

原图用箭头标明：一条外接线对应 $D_{x1}$，重合点自环对应 $D_{xx}$ 或 $D_{yy}$，连接 $x$ 与 $y$ 的两条线对应 $D_{xy}^2$。图形求和末尾同样保留 $O(g^3)$。

## 解释

这些图记录的是公式中的收缩连接关系。第二幅图虽然不连通，但每个连通部分都含有一个外点，所以它仍是当前完整二点函数的一部分。图形行中的加号表示各图贡献相加，各图的负号和数值系数已包含在上方公式中。

---

# 7. 一般多项式相互作用的位置空间费曼规则

对应图片：

- 7
- 8

## 板书整理

### 图片 7：外点、内部顶点与连线

![[Picture/9.1/7.jpg]]

考虑：

$$
V_{\mathrm{int}}=\frac{g}{n!}\phi^n.
$$

板书提出：计算 $\langle\phi_1\cdots\phi_N\rangle$ 到 $O(g^v)$。其中 $v$ 是内部顶点数。

1. 画出 $N$ 个点 $\{x_1,\ldots,x_N\}$，称为**外点**（external points）。
2. 画出 $v$ 个点 $\{y_1,\ldots,y_v\}$，称为**内点**（internal points）或**顶点**（vertices）。
3. 画出所有可能的图，每个相互作用顶点上有 $n$ 条线，线也称为边（edges）。
4. 计算每一幅图，具体规则接下一张板书。

### 图片 8：把图转成表达式

![[Picture/9.1/8.jpg]]

每条连接 $x$ 与 $y$ 的边给出：

$$
\text{边 }(x,y)\quad\longleftrightarrow\quad D_{xy}.
$$

每个 $n$ 条腿的顶点给出：

$$
\text{$n$ 腿顶点}\quad\longleftrightarrow\quad -ig.
$$

板书红字解释其中的阶乘抵消：

$$
\frac{n!}{n!}=1,
$$

分子来自 $n$ 条腿的组合计数，分母来自 $V_{\mathrm{int}}$ 中的 $n!$。

然后：

- 对内部顶点的位置积分。
- 除以对称因子（symmetry factor）。

## 解释

固定 $v$ 个顶点给出含 $g^v$ 的项；若要求完整结果至该阶，还要把较低阶的贡献一并相加。每个外点对应一个插入场，因此接一条线；内部顶点的腿数由相互作用中场的次数决定。

> [!warning]
> **板书检查提醒：图求和的适用范围**
>
> 位置：图片 7–8，“所有可能的图”的规则。
>
> 板书内容：画出所有可能的图，并乘传播子、顶点因子，积分后除以对称因子。
>
> 检查结果：此处未单独注明归一化真空关联函数中对纯真空部分的处理。
>
> 说明：这里的尖括号是归一化关联函数，完全不连接任何外点的真空图因子应与真空归一化抵消；“所有图”应在这一前提下理解。图片 6 的第二幅图每个部分都有外点，并不属于应抵消的纯真空部分。
>
> 注意：以上为适用范围检查，未修改原板书规则。

---

# 8. 顶点归一化与剩余的组合因子

对应图片：

- 9

## 板书整理

![[Picture/9.1/9.jpg]]

主题：对称因子（Symmetry factor）。

对于一种场，采用约定：

$$
V_{\mathrm{int}}(\phi)=\frac{g}{n!}\phi^n.
$$

对于多种场：

$$
V_{\mathrm{int}}(\phi,\chi,\psi,\ldots)
=\frac{g}{n!\,m!\,\ell!\cdots}
\phi^n\chi^m\psi^\ell\cdots.
$$

这些阶乘因子处理了每个顶点处的组合计数。

但是，一幅图仍可能因边的交换而具有其他组合因子，因此还必须除以这个因子。

## 解释

顶点中的阶乘归一化与整幅图的对称因子是两个层次的计数。前者处理一个顶点内同种场的排列，后者处理保持图不变的等价交换；顶点已经写成 $-ig$，并不意味着所有图的数值系数都是 $1$。

---

# 9. 对称因子的定义与四个例子

对应图片：

- 10

## 板书整理

![[Picture/9.1/10.jpg]]

对称因子定义：

$$
S=\text{保持外点固定时，使一幅图等价不变的置换数}.
$$

板书强调：外点必须保持固定（the external points remain fixed）。

例子按图中位置记录如下：

| 位置 | 图的结构与板书标记 | 板书给出的对称因子 |
| --- | --- | --- |
| 左上 | 两个内部顶点间有两条平行线，每个顶点各接一个外点；蓝色箭头交换上下两条线 | $S=2$ |
| 右上 | 两个内部顶点间有三条平行线，每个顶点各接一个外点 | $S=3!$ |
| 左下 | 三个内部顶点 $x,y,z$ 构成一圈，分别接固定外点 $x_1,x_2,x_3$；图上标有 $D_{xy}$、$D_{yz}$ 及交换箭头 | $S=1$ |
| 右下 | 两个外点通过同一上方顶点相连，该顶点向下连到一个带两个自环的顶点；两个环各标一个 $2$，环之间交换再给一个 $2$ | $S=2\cdot2\cdot2=8$ |

## 解释

前两个例子分别计数两条或三条等价平行线的置换。三外点环图的外点标签固定后，交换环上不同位置的线不能保持原来的连接关系，因此只有恒等置换。最后一图中，每个自环都可交换两个接头，而两个相同自环也可以互换，得到三个独立的因子 $2$。

---

# 10. 不同场的顶点备注与一点函数条件

对应图片：

- 11

## 板书整理

![[Picture/9.1/11.jpg]]

板书备注：如果顶点的所有腿分别对应不同的场，则任意图中都有：

$$
S=1.
$$

原文强调“in any diagram”。右侧配有两种顶点：

- 三条腿分别标为 $\phi$、$\chi$、$\psi$。
- 电磁相互作用顶点，标为 $e^-$、$e^+$ 与波浪线 $\gamma$，旁注 EM。

> [!warning]
> **板书检查提醒：对“任意图”的限定**
>
> 位置：图片 11，关于不同场顶点的备注。
>
> 板书内容：顶点的腿对应不同场时，“任意图”均有 $S=1$。
>
> 检查结果：若把“任意图”理解为也包括纯真空图，表述过宽。
>
> 说明：依据图片 10 的定义，必须检查整幅图保持外点固定的等价置换，不能只检查单个顶点的腿。例如，把两个 $\phi\chi\psi$ 顶点分别用一条同种场线相连，所得真空图可以交换两个内部顶点，仍有非平凡对称性。在各连通部分都含固定外点、且每个顶点的腿种类可区分的课堂语境中，可使用这一简化结论。
>
> 注意：保留板书原话与 $S=1$，这里只补充其适用范围。

随后板书转向：**蝌蚪图抵消**（Tadpole cancellation）。

定义场，使它满足：

$$
\langle\Omega|\phi(x)|\Omega\rangle=0.
$$

## 解释

对称因子的判断需要同时保留外点标签和场的种类。本图下半部分引入的新条件要求相互作用真空中的一点函数为零；接下来的板书将检查前面得到的微扰结果是否满足这一条件。

---

# 11. 非零一点函数与线性反项

对应图片：

- 12

## 板书整理

![[Picture/9.1/12.jpg]]

然而，前面已经求得：

$$
\langle\phi_x\rangle
=-\frac{ig}{2}D_{xy}D_{yy}+O(g^2).
$$

板书画出相应图形：外点 $x$ 通过一条线连接内部顶点 $y$，$y$ 上带一个自环。

因此，需要修改拉格朗日量，加入一个**反项**（counter-term）：

$$
\mathcal L
=-\frac12(\partial\phi)^2
-\frac{m^2}{2}\phi^2
-\frac{g}{3!}\phi^3
+Y\phi.
$$

板书用括号标出 $Y\phi$ 为新增的反项，并注明 $Y$ 是常数（constant）。

## 解释

当前三次相互作用给出非零的一点函数，与上一图规定的场定义不相符。线性项 $Y\phi$ 提供一个新的可调贡献，用来满足 $\langle\phi\rangle=0$；这一步是课堂主动修改理论中的参数项，不是整理时改动原板书。

---

# 12. 加入新顶点后重新计算一点函数

对应图片：

- 13

## 板书整理

![[Picture/9.1/13.jpg]]

现在的相互作用势为：

$$
V_{\mathrm{int}}
=\frac{g}{3!}\phi^3-Y\phi.
$$

两种顶点的规则：

$$
\text{三腿顶点}\quad\longleftrightarrow\quad -ig,
$$

$$
\text{带叉记号的一腿顶点}\quad\longleftrightarrow\quad +iY.
$$

板书说明：必须重新计算，把这个新顶点包括进来。

一点函数先用图形表示为：

$$
\langle\phi_x\rangle
=\text{原来的单自环图}
+\text{从 $x$ 连到 $y$ 处带叉顶点的图}
+O(g^2).
$$

再写成代数式：

$$
\langle\phi_x\rangle
=-\frac{ig}{2}D_{xy}D_{yy}
+D_{xy}\cdot iY
+O(g^2).
$$

## 解释

线性反项只有一条腿，其顶点因子为 $+iY$，符号与 $V_{\mathrm{int}}$ 中的 $-Y\phi$ 一致。新的贡献与原图都带有从 $x$ 到 $y$ 的传播子，因此可以通过选择 $Y$ 让它们相互抵消。

---

# 13. 确定反项系数：蝌蚪图抵消条件

对应图片：

- 14

## 板书整理

![[Picture/9.1/14.jpg]]

接上图，提出共同的传播子因子，并施加一点函数为零的条件：

$$
\langle\phi_x\rangle
=iD_{xy}\left[-\frac g2D_{yy}+Y\right]
+O(g^2)
=0.
$$

因此：

$$
Y=\frac g2D_{yy}+O(g^2).
$$

板书在 $D_{yy}$ 下方注明：

$$
D_{yy}=D_F(y-y)=D_F(0)=\text{常数}.
$$

最终框出的结果为：

$$
\boxed{Y=\frac g2D_F(0)+O(g^2).}
$$

旁注：蝌蚪图抵消（Tadpole cancellation）。

## 解释

这里使用了传播子的平移不变性：当两个端点重合时，坐标差恒为零，所以 $D_{yy}$ 不依赖 $y$。于是常数 $Y$ 可以抵消括号中的一阶贡献。板书给出的是 $Y$ 的最低阶确定式，更高阶项仍由 $O(g^2)$ 表示。

---

# 14. 重合点传播子的发散

对应图片：

- 15

## 板书整理

![[Picture/9.1/15.jpg]]

板书最后注明：

$$
D_F(0)
=-i\int\frac{d^4p}{(2\pi)^4}
\frac{1}{p^2+m^2-i\epsilon}
=\text{“常数”}
=\infty.
$$

下方写出主题：蝌蚪图（Tadpole diagrams）。本张图片没有继续列出新的图或后续计算。

> [!warning]
> **板书检查提醒：发散表达式的含义**
>
> 位置：图片 14–15，$D_F(0)$ 与“常数 $=\infty$”。
>
> 板书内容：$D_F(0)=-i\int\frac{d^4p}{(2\pi)^4}\frac{1}{p^2+m^2-i\epsilon}=\text{“常数”}=\infty$。
>
> 检查结果：这里的“常数”表示与时空位置无关，不表示积分已经给出有限数值；“$=\infty$”是发散的示意写法。
>
> 说明：四维大动量区域中，积分测度与分母的幂次对应于 $\int^{\Lambda}p\,dp$ 的增长。因此未经正规化，不能把 $D_F(0)$ 当作普通有限常数；上一图的反项关系应在一致的正规化处理下理解。板书此处未继续计算正规化后的值。
>
> 注意：原积分、符号和“$=\infty$”均予保留，未代换成其他结果。

## 解释

最后一张板书指出：虽然重合点传播子不依赖坐标，其积分仍然发散。因而前面为了使一点函数为零而引入的反项，正对应了这一蝌蚪图贡献的抵消。

---

# 本节知识结构

上节回顾：Schwinger–Dyson 方程、Ward–Takahashi 恒等式与微扰论  
↓  
自由理论的 Wick 定理：部分收缩与完全收缩  
↓  
正规序的真空期望值 → 自由关联函数等于完全收缩之和  
↓  
三次相互作用 $V_{\mathrm{int}}=g\phi^3/3!$ 与 Schwinger–Dyson 方程  
↓  
二点函数递推 → 三场关联函数 → 四场关联函数与一点函数  
↓  
按所需阶数截断：自由四场收缩与一阶一点函数  
↓  
二点函数的二阶结果及四种图形贡献  
↓  
一般 $\phi^n$ 相互作用的位置空间费曼规则  
↓  
顶点的阶乘约定 → 保持外点固定的对称因子及例子  
↓  
不同场顶点的备注 → 要求 $\langle\Omega|\phi(x)|\Omega\rangle=0$  
↓  
原一点函数非零 → 加入线性反项 $Y\phi$  
↓  
新增一腿顶点 $+iY$ → 重新计算一点函数  
↓  
蝌蚪图抵消条件 $Y=gD_F(0)/2+O(g^2)$  
↓  
重合点传播子 $D_F(0)$ 的发散。

---

# 核心公式清单

以下按课堂首次出现的顺序列出；内部顶点标签继续采用隐含时空积分的板书简记。

| 公式 | 含义 |
| --- | --- |
| $\langle\phi_1\cdots\phi_N\rangle=-iD_{x1}(\Box_x-m^2)\langle\phi_x\phi_2\cdots\phi_N\rangle$ | 用自由传播子逆核改写关联函数，式 $(1)$ |
| $T\{\phi_1\cdots\phi_N\}=\mathcal N\{\phi_1\cdots\phi_N+\text{所有收缩项}\}$ | Wick 定理的算符形式 |
| $\text{$\phi_i$ 与 $\phi_j$ 的收缩}=D_{ij}$ | 收缩与传播子、连线的对应 |
| $\langle0\lvert\mathcal N\{\text{含场算符的乘积}\}\rvert0\rangle=0$ | 正规序项的自由真空期望值；纯数项除外 |
| $\langle0\lvert T\{\phi_1\cdots\phi_N\}\rvert0\rangle=\text{完全收缩之和}$ | 自由多点关联函数的计算规则 |
| $V_{\mathrm{int}}=g\phi^3/3!\,,\quad V'_{\mathrm{int}}=g\phi^2/2!$ | 本节用于展开的三次相互作用 |
| $(\Box_x-m^2)\langle\phi_x\phi_2\cdots\phi_N\rangle=\frac g2\langle\phi_x^2\phi_2\cdots\phi_N\rangle+i\sum_{n=2}^N\delta_{xn}\langle\phi_2\cdots\phi_{n-1}\phi_{n+1}\cdots\phi_N\rangle$ | 相互作用 Schwinger–Dyson 方程，式 $(2)$ |
| $\langle\phi_1\phi_2\rangle=D_{12}-\frac{ig}{2}D_{x1}\langle\phi_x^2\phi_2\rangle$ | 二点函数的第一次递推 |
| $(\Box_y-m^2)\langle\phi_x^2\phi_y\rangle=\frac g2\langle\phi_y^2\phi_x^2\rangle+2i\delta_{yx}\langle\phi_x\rangle$ | 两个相同位置场产生的接触项 |
| $\langle\phi_1\phi_2\rangle=D_{12}-\frac{g^2}{4}D_{x1}D_{y2}\langle\phi_x^2\phi_y^2\rangle-igD_{x1}D_{x2}\langle\phi_x\rangle$ | 第二次递推后的表达式 |
| $\langle\phi_y^2\rangle_{\mathrm{free}}=D_{yy}$ | 同一点的自由收缩 |
| $\langle\phi_x\rangle=-\frac{ig}{2}D_{xy}D_{yy}+O(g^2)$ | 未加反项时的一点函数 |
| $\langle\phi_x^2\phi_y^2\rangle_{\mathrm{free}}=D_{xx}D_{yy}+2D_{xy}^2$ | 四场的三种完全收缩 |
| $\langle\phi_1\phi_2\rangle=D_{12}-g^2[\frac14D_{x1}D_{y2}D_{xx}D_{yy}+\frac12D_{x1}D_{y2}D_{xy}^2+\frac12D_{x1}D_{x2}D_{xy}D_{yy}]+O(g^3)$ | 二点函数至二阶 |
| $V_{\mathrm{int}}=g\phi^n/n!$ | 一般单场顶点的归一化约定 |
| $\text{边 }(x,y)\leftrightarrow D_{xy}\,,\quad\text{$n$ 腿顶点}\leftrightarrow-ig$ | 位置空间费曼规则；内部点积分并除以 $S$ |
| $V_{\mathrm{int}}=\frac{g}{n!m!\ell!\cdots}\phi^n\chi^m\psi^\ell\cdots$ | 多场相互作用的阶乘约定 |
| $S=\text{固定外点时图的等价置换数}$ | 对称因子；本节例子为 $2,3!,1,8$ |
| $\langle\Omega\lvert\phi(x)\rvert\Omega\rangle=0$ | 对场的一点函数条件 |
| $\mathcal L=-\frac12(\partial\phi)^2-\frac{m^2}{2}\phi^2-\frac g{3!}\phi^3+Y\phi$ | 加入线性反项后的拉格朗日量 |
| $V_{\mathrm{int}}=\frac g{3!}\phi^3-Y\phi\,,\quad\text{一腿顶点}\leftrightarrow+iY$ | 新反项对应的新顶点 |
| $\langle\phi_x\rangle=iD_{xy}[-\frac g2D_{yy}+Y]+O(g^2)=0$ | 两种一点图的抵消条件 |
| $D_{yy}=D_F(y-y)=D_F(0)$ | 平移不变性下的重合点传播子 |
| $Y=\frac g2D_F(0)+O(g^2)$ | 最低阶线性反项系数 |
| $D_F(0)=-i\int\frac{d^4p}{(2\pi)^4}\frac1{p^2+m^2-i\epsilon}=\text{“常数”}=\infty$ | 原板书对重合点传播子发散的写法；含义见对应检查提醒 |
