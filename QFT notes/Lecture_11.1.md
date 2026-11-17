---
title: "量子场论导论 Lecture 11.1"
date: null
tags:
  - 量子场论导论
  - lecture
  - 费曼图
  - 散射截面
  - Mandelstam变量
source: "课堂板书"
---

# Lecture 11.1: 动量空间费曼规则与散射截面

## 本节内容概览

本节先回顾上一讲的 Pauli–Villars 正则化、动量空间费曼规则和一圈 $1\to1$ 散射。随后整理一般费曼图的动量分配、内部线、顶点、圈积分和对称因子规则，并讨论连通图与非连通图。接着以 $\phi^4$ 与 $\phi^3$ 理论中的 $2\to2$ 散射为例，引入质心系、Mandelstam 变量、散射角以及微分和总截面。最后讨论相同粒子的末态对称因子，并给出非相对论和超相对论极限的板书结果。

## 1. 上一讲回顾：一圈 $1\to1$ 散射

对应图片：1、2

![[Picture/11.1/1.jpg]]

### 板书整理

板书首先列出上一讲内容：

- Pauli–Villars regularization。
- Feynman rules in momentum space。
- $1\to1$ scattering。

对于外线动量 $p$ 与 $p'$，板书写出 LSZ 形式的表达式：
$$
\langle f|\hat S|i\rangle
=
\left[
i\int d^4x\,e^{ip\cdot x}(p^2+m^2)
\right]
\left[
i\int d^4x'\,e^{-ip'\cdot x'}(p'^2+m^2)
\right]
\left[
-\frac{g^2}{2}
\int
\frac{d^4k}{(2\pi)^4}
\frac{d^4k'}{(2\pi)^4}
\frac{d^4q}{(2\pi)^4}
\,
\frac{(2\pi)^4\delta^4(k-k')e^{ik\cdot x}e^{-ik'\cdot x'}}
{(k^2+m^2-i\epsilon)(k'^2+m^2-i\epsilon)(q^2+m^2-i\epsilon)((k-q)^2+m^2-i\epsilon)}
\right].
$$

利用傅里叶积分得到动量守恒：
$$
\int d^4x\longrightarrow (2\pi)^4\delta^4(k-p),
\qquad
\int d^4x'\longrightarrow (2\pi)^4\delta^4(k'-p').
$$

化简后，板书得到
$$
\langle f|\hat S|i\rangle
=
\frac{g^2}{2}(2\pi)^4\delta^4(p'-p)
\int\frac{d^4q}{(2\pi)^4}
\frac{1}
{(q^2+m^2-i\epsilon)\big((p-q)^2+m^2-i\epsilon\big)}.
$$

板书随后回顾
$$
\langle f|\hat S|i\rangle
=
(\text{trivial})
+
(2\pi)^4\delta^4(p_f-p_i)\,i\mathcal M.
$$

因此一圈贡献写成
$$
i\mathcal M_{1\to1}
=
\frac{(-ig)^2}{2}
\int\frac{d^4q}{(2\pi)^4}
\frac{(-i)^2}
{(q^2+m^2-i\epsilon)\big((p-q)^2+m^2-i\epsilon\big)}
+\mathcal O(g^4).
$$

板书右侧画出一条外线进入、经过一个泡图、再出射的图，并标注该泡图依赖于外部动量。

### 解释

这一部分把位置空间中的外线约化转换为动量空间积分。外线因子产生动量守恒 delta 函数；内部传播子留下圈动量 $q$ 的积分。一圈泡图的两个内部传播子给出两个费曼分母，前面的 $1/2$ 是该图的对称因子。

## 2. 一般动量空间费曼规则

对应图片：2、3、4

![[Picture/11.1/2.jpg]]

![[Picture/11.1/3.jpg]]

![[Picture/11.1/4.jpg]]

### 板书整理

板书说明，可以直接从动量空间得到 $\mathcal M$，并给出以下规则。

1. 画出所有可能的图（忽略 bubble、tadpole 和 disconnected diagrams），有 $N_{\rm in}+N_{\rm out}$ 条外线；为外线指定动量
   $$
   p_1,\ldots,p_{N_{\rm in}},
   \qquad
   p'_1,\ldots,p'_{N_{\rm out}}.
   $$

2. 在阶数 $\mathcal O(g^n)$ 的微扰论中，考虑带有 $n$ 个顶点的图。板书给出 $\phi^3$ 理论的相互作用：
   $$
   V_{\rm int}=\frac{g}{3!}\phi^3.
   $$

3. 给每条内部线任意指定动量
   $$
   \{q_1,q_2,\ldots\},
   $$
   但要保证每个顶点处的动量守恒。板书注明：动量方向本身不重要。

4. 每条内部线贡献
   $$
   \frac{-i}{q^2+m^2-i\epsilon}.
   $$

5. 每个顶点贡献
   $$
   -ig.
   $$

6. 对所有未确定的内部动量积分：
   $$
   \prod_{\ell}
   \int\frac{d^4q_\ell}{(2\pi)^4}.
   $$
   板书注明积分个数等于圈数。

7. 最后除以对称因子。

### 解释

规则的核心是：先用顶点处的动量守恒固定内部线动量之间的关系，剩下的独立圈动量才需要积分。传播子、顶点因子、圈积分和对称因子共同给出每张图的贡献。

## 3. 连通图、非连通图与示例

对应图片：5、6、7

![[Picture/11.1/5.jpg]]

![[Picture/11.1/6.jpg]]

![[Picture/11.1/7.jpg]]

### 板书整理

板书给出一个 $\phi^3$ 理论中的 $3\to2$ scattering at $1$ loop 示例，并写出相互作用
$$
V_{\rm int}=\frac{g}{3!}\phi^3.
$$

图中内部动量依次出现
$$
p_1-q,\qquad
p_1+p_2-q,\qquad
p_1+p_2+p_3-q,
$$
并在右侧写出完整的一圈积分：
$$
i\mathcal M
=
(-ig)^5
\int\frac{d^4q}{(2\pi)^4}
\frac{(-i)^5}
{
(q^2+m^2-i\epsilon)
\big((p_1-q)^2+m^2-i\epsilon\big)
\big((p_1+p_2-q)^2+m^2-i\epsilon\big)
\big((p_1+p_2+p_3-q)^2+m^2-i\epsilon\big)
\big((p_1+p_2+p_3-q-p'_2)^2+m^2-i\epsilon\big)
}
=i\mathcal M.
$$

板书右上方标有 “5 vertices”。

板书随后强调：

- disconnected diagrams 是物理的，但可以分别计算，因此在计算连通散射振幅时可以忽略；
- 给定 $N_{\rm in}\to N_{\rm out}$，leading contribution 来自没有 loops 的图，即 tree diagrams；
- 以 $\phi^4$ 理论中的 $2\to2$ scattering 为例，
  $$
  V_{\rm int}=\frac{\lambda}{4!}\phi^4.
  $$

树图中没有未确定的圈动量，所以没有圈积分；板书还写出该例的振幅因子为
$$
i\mathcal M=-i\lambda,
\qquad
|\mathcal M|^2=\lambda^2.
$$

### 解释

连通图对应真正连接初态和末态的散射过程；非连通图会因子化为若干相互独立的过程。树图没有圈积分，通常给出给定耦合阶数下的最低阶贡献。第 5 张图片中的五个传播子分母和五个顶点均可辨认，已按板书完整记录。


## 4. $\phi^4$ 理论中的树级 $2\to2$ 散射与微分截面

对应图片：7、8

### 板书整理

板书先给出一般散射过程的说明：给定 $N_{\rm in}\to N_{\rm out}$，leading contribution 由 tree diagrams 给出。

![[Picture/11.1/8.jpg]]

对 $\phi^4$ 理论
$$
V_{\rm int}=\frac{\lambda}{4!}\phi^4,
$$
$2\to2$ 树图的贡献为
$$
i\mathcal M=-i\lambda,
\qquad
|\mathcal M|^2=\lambda^2.
$$

质心系微分截面写成
$$
\left.\frac{d\sigma}{d\Omega}\right|_{\rm CM}
=
\frac{|\vec p'_1|}
{64\pi^2|\vec p_1|E_{\rm CM}^2}
|\mathcal M|^2.
$$

对于相同粒子，质心系中
$$
|\vec p'_1|=|\vec p_1|.
$$

于是板书框出
$$
\left.\frac{d\sigma}{d\Omega}\right|_{\rm CM}
=
\frac{\lambda^2}{64\pi^2s},
\qquad
s=E_{\rm CM}^2.
$$

板书还注明 tree diagrams 没有 loops，因此没有未确定动量，也不需要在传播子中处理 $i\epsilon$ 的圈积分问题。

### 解释

微分截面由振幅平方、初末态三动量比和质心能量共同决定。对于 $\phi^4$ 的四点接触顶点，树级振幅与动量无关，因此角分布是各向同性的。

## 5. Mandelstam 变量与 $\phi^3$ 理论的 $2\to2$ 散射

对应图片：9、10、11、12

![[Picture/11.1/9.jpg]]

![[Picture/11.1/10.jpg]]

![[Picture/11.1/11.jpg]]

![[Picture/11.1/12.jpg]]

### 板书整理

板书定义 Mandelstam 变量
$$
s=-(p_1+p_2)^2,
\qquad
t=-(p_1-p'_1)^2,
\qquad
u=-(p_1-p'_2)^2.
$$

并注明 $s,t,u$ 都是 Lorentz invariants。

在质心系
$$
\vec p_1+\vec p_2=0,
$$
所以
$$
(p_1+p_2)^2
=
-(\omega_1+\omega_2)^2
+
(\vec p_1+\vec p_2)^2
=
-E_{\rm CM}^2,
$$
从而
$$
s=E_{\rm CM}^2.
$$

板书还给出恒等关系
$$
s+t+u
=
m_1^2+m_2^2+m_1'^2+m_2'^2.
$$

随后转到 $\phi^3$ 理论
$$
V_{\rm int}=\frac{g}{3!}\phi^3.
$$

$2\to2$ 散射的三个树级交换图分别对应 $s$、$t$、$u$ 三个道。板书写出
$$
i\mathcal M
=
(-ig)^2
\left[
\frac{-i}{(p_1+p_2)^2+m^2}
+
\frac{-i}{(p_1-p'_1)^2+m^2}
+
\frac{-i}{(p_1-p'_2)^2+m^2}
\right].
$$

用 Mandelstam 变量改写为
$$
i\mathcal M
=
ig^2
\left[
\frac{1}{m^2-s}
+
\frac{1}{t-m^2}
+
\frac{1}{u-m^2}
\right].
$$

散射角定义为 $\vec p'_1$ 与 $\vec p_1$ 之间的夹角 $\theta$。板书给出
$$
t
=
-m_1^2-m_1'^2
-2\omega_1\omega'_1
+2|\vec p_1||\vec p'_1|\cos\theta
\qquad
(\text{in any frame}).
$$

对于相同粒子在质心系，
$$
\omega_1=\omega'_1=\frac{E_{\rm CM}}{2}
=\frac{\sqrt s}{2},
$$
$$
|\vec p_1|=|\vec p'_1|
=
\sqrt{\omega_1^2-m^2}
=
\sqrt{\frac{s}{4}-m^2}.
$$

因此
$$
t
=
-\frac12(s-4m^2)(1-\cos\theta),
$$
$$
u
=
-\frac12(s-4m^2)(1+\cos\theta).
$$

板书进一步给出
$$
|\mathcal M|^2
=
g^4
\left[
\frac{1}{(s-m^2)^2}
+
\frac{1}{
\left(m^2+\frac12(s-4m^2)(1-\cos\theta)\right)^2
}
+
\frac{1}{
\left(m^2+\frac12(s-4m^2)(1+\cos\theta)\right)^2
}
\right].
$$

### 解释

$s,t,u$ 把四动量组合压缩成三个 Lorentz 不变量，分别对应不同交换道。对 $\phi^3$ 理论，$2\to2$ 散射在树级有三个交换图，因此振幅是三个传播子项之和。质心系表达式把 $t,u$ 直接写成散射角的函数，便于计算角分布和总截面。

## 6. 微分截面、总截面与相同粒子对称因子

对应图片：13、14

![[Picture/11.1/13.jpg]]

![[Picture/11.1/14.jpg]]

### 板书整理

质心系微分截面为
$$
\left.\frac{d\sigma}{d\Omega}\right|_{\rm CM}
=
\frac{|\mathcal M|^2}{64\pi^2s}.
$$

总截面按散射角积分：
$$
\sigma
=
2\pi
\int_{-1}^{1}
d(\cos\theta)\,
\frac{d\sigma}{d\Omega}.
$$

对相同粒子，末态存在对称因子。板书写成
$$
S_{\rm out}
=
\prod_i n_i!,
$$
其中 $i$ 遍历粒子种类，例如 $i=1$ 可表示电子、$i=2$ 可表示正电子，而 $n_i$ 是末态中第 $i$ 类粒子的数目。

在当前例子中，
$$
S_{\rm out}=2!,
$$
因为末态有两个相同的标量粒子。

板书给出该例总截面的积分结果：
$$
\sigma
=
\frac{g^4}{32\pi s(s-4m^2)}
\left[
\frac{2}{m^2}
+
\frac{s-4m^2}{(s-m^2)^2}
-
\frac{2}{s-3m^2}
+
\frac{4m^2}{(s-m^2)(s-2m^2)}
\right].
$$

### 解释

微分截面先由 $|\mathcal M|^2$ 给出，再对完整立体角积分得到总截面。若末态含有不可区分的相同粒子，同一物理末态会被多次计数，因此要除以相应的对称因子。

## 7. 非相对论与超相对论极限

对应图片：15

![[Picture/11.1/15.jpg]]

### 板书整理

板书给出非相对论极限
$$
s\simeq 4m^2,
\qquad
|\vec p|\ll m,
$$
并写出
$$
\sigma
\simeq
\frac{25g^4}{1152\pi m^6}.
$$

板书随后写出超相对论极限条件
$$
s\gg m^2,
\qquad
|\vec p|\gg m,
$$
并给出
$$
\sigma
\simeq
\frac{g^4}{16\pi m^2s^2}.
$$

### 解释

非相对论极限在阈值 $s\simeq4m^2$ 附近展开；超相对论极限则忽略质量相对于质心能量的贡献。

# 本节知识结构

上一讲的一圈 $1\to1$ 振幅  
↓  
动量空间费曼规则：内部线、顶点、圈积分、对称因子  
↓  
连通图与非连通图；树图与圈图  
↓  
$\phi^4$ 理论的树级 $2\to2$ 散射  
↓  
Mandelstam 变量 $s,t,u$  
↓  
$\phi^3$ 理论的 $s$、$t$、$u$ 三道交换  
↓  
质心系散射角与微分截面  
↓  
总截面、相同粒子对称因子及极限行为

# 核心公式清单

| 公式 | 含义 |
| --- | --- |
| $\displaystyle \frac{-i}{q^2+m^2-i\epsilon}$ | 动量空间内部传播子 |
| $\displaystyle -ig$ | $\phi^3$ 顶点因子 |
| $\displaystyle \frac{g^2}{2}(2\pi)^4\delta^4(p'-p)\int\frac{d^4q}{(2\pi)^4}\frac{1}{(q^2+m^2-i\epsilon)((p-q)^2+m^2-i\epsilon)}$ | 一圈 $1\to1$ 泡图贡献的板书结果 |
| $\displaystyle s=-(p_1+p_2)^2,\ t=-(p_1-p'_1)^2,\ u=-(p_1-p'_2)^2$ | Mandelstam 变量 |
| $\displaystyle s+t+u=m_1^2+m_2^2+m_1'^2+m_2'^2$ | 四点散射的不变量关系 |
| $\displaystyle i\mathcal M=ig^2\left[\frac1{m^2-s}+\frac1{t-m^2}+\frac1{u-m^2}\right]$ | $\phi^3$ 理论树级 $2\to2$ 振幅 |
| $\displaystyle \left.\frac{d\sigma}{d\Omega}\right|_{\rm CM}=\frac{|\mathcal M|^2}{64\pi^2s}$ | 相同质量、质心系下的微分截面 |
| $\displaystyle S_{\rm out}=\prod_i n_i!$ | 末态相同粒子的对称因子 |
| $\displaystyle \sigma=2\pi\int_{-1}^{1}d(\cos\theta)\,\frac{d\sigma}{d\Omega}$ | 总截面 |

# 板书完整性与数学检查

- 已处理图片：1–15，共 15 张；编号连续，无缺失。
- 所有图片均已在对应小节附近嵌入，原始图片未移动或修改。
- 第 5 张图片的 $\phi^3$ 一圈 $3\to2$ 积分式已完整辨认并记录：包含 $(-ig)^5$、五个传播子分母和 $d^4q$ 圈积分。
- 第 15 张图片的非相对论与超相对论极限公式均可辨认，已完整记录。
- 未发现必须修改原板书的明确数学错误；第 5 张和第 15 张的相关公式均已按照片完整记录。


