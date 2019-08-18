# Stanford-Quantum-Mechanics-Note

斯坦福量子力学笔记

## 一、量子比特实验及狄拉克符号

### 记录
学物理犯的最严重的错误就是试图可视化一些抽象的理论概念，实际上那些伟大的物理学家并不是有强大的空间想象能力

要训练自己的抽象思维能力，也就是用数学来表示一切

apparatus 仪器设备，用于量子比特实验

量子的特性，测量行为会影响量子的状态

量子并不是向量，向量是经典物理里面的概念，量子只有-1 +1，当观测角度与方向一致时，就全部都是+1，方向相反时，全部是-1，倾斜时，随机出现+1和-1，平均值会是等于角度的cos余弦

共轭(conjugate)复数，两个实部相等，虚部互为相反数的复数互为共轭复数
```math
a + ib = \overline{a - ib}
```

共轭向量
```math
\vec{a} = \left[ \begin{matrix} 1 \\ i \\ 0 \end{matrix} \right]

\vec{a}^* = \left[ \begin{matrix} 1 \\ -i \\ 0 \end{matrix} \right]
```

厄米共轭，共轭后再转置
```math
\vec{a} = \left[ \begin{matrix} 1 \\ i \\ 0 \end{matrix} \right]

\vec{a}^\dagger = \left[ \begin{matrix} 1 & -i & 0 \end{matrix} \right]

\vec{a}^\dagger \vec{a} = 2
```

狄拉克braket符号，ket右矢为复数向量，bra左矢为厄米共轭向量
```math
ket右矢 \rightarrow \mid A >

bra左矢 \rightarrow < A \mid

\mid A > = < A \mid ^\dagger \rightarrow 厄米共轭

braket内积：< A \mid A >
```

希尔伯特空间是欧几里德空间的一个推广，其不再局限于有限维的情形。其也是一个内积空间，其上有距离和角的概念（及由此引申而来的正交性与垂直性的概念）

量子态空间是复数向量空间，是希尔伯特空间

希尔伯特空间，可以把向量扩展到函数，函数其实就是一个连续的列向量

### 疑问

Q. 量子力学为什么要用复数表示？
-   引入复数是为了描述粒子的波粒二象性。在第一章由于只讨论了量子的自旋，所以看起来用复数是多余的。

Q. 狄拉克符号、复数向量以及量子力学有什么关系？
-   狄拉克符号是用来描述复数向量的符号，也是描述量子力学理论的基本符号。

Q. 复数向量内外积定义与量子力学有什么关系？
-   复数向量与基向量的内积是复数向量在基向量上的投影。后面章节会讲到波函数，就是状态向量与基向量的内积。
-   复数向量与自身的内积具有概率的性质，在后面的章节也会讲到。

## 二、复数向量空间里的正交态

### 记录
复向量空间一定不要尝试像考虑实数向量空间那样，要摆脱这种几何思维，要抽象地去看这个问题

量子态空间两个假设
-   自旋态up down是正交的
-   一个二维的狄拉克向量空间，出现up down的概率对应的是每个向量幅度的平方，这两个平方（概率）之和等于1
```math
<u \mid d> = 0

\mid A > = \alpha_u \mid u > + \alpha_d \mid d >

P_u = \alpha_u^* \alpha_u

P_d = \alpha_d^* \alpha_d

P_u + P_d = \alpha_u^* \alpha_u + \alpha_d^* \alpha_d = 1

< A \mid A > = 1
```

根据假设，left right也是up down的线性组合，一种猜测
```math
<l \mid r> = 0

\mid r > = \frac{1}{\sqrt2} (\mid u > + \mid d >)

\mid l > = \frac{1}{\sqrt2} (\mid u > - \mid d >)

\frac{\mid r > + \mid l >}{\sqrt2} = \mid u >

\frac{\mid r > - \mid l >}{\sqrt2} = \mid d >
```

in out也是up down的线性组合，且应该是复数，猜测如下
```math
<i \mid o> = 0

\mid i > = \frac{1}{\sqrt2} (\mid u > + i\mid d >)

\mid o > = \frac{1}{\sqrt2} (\mid u > - i\mid d >)

\frac{\mid i > + \mid o >}{\sqrt2} = \mid u >

\frac{\mid i > - \mid o >}{\sqrt2i} = \mid d >
```

综上
```math
\mid u > = \left[ \begin{matrix} 1 \\ 0 \end{matrix} \right]
\mid d > = \left[ \begin{matrix} 0 \\ 1 \end{matrix} \right]

\mid r > = \left[ \begin{matrix} \frac{1}{\sqrt2} \\ \frac{1}{\sqrt2} \end{matrix} \right] 
\mid l > = \left[ \begin{matrix} \frac{1}{\sqrt2} \\ -\frac{1}{\sqrt2} \end{matrix} \right] 

\mid i > = \left[ \begin{matrix} \frac{1}{\sqrt2} \\ \frac{i}{\sqrt2} \end{matrix} \right] 
\mid o > = \left[ \begin{matrix} \frac{1}{\sqrt2} \\ -\frac{i}{\sqrt2} \end{matrix} \right]
```

### 疑问
Q. 有学生提问，这里面的left right in out是不是隐含了左手右手系统，老师回答：这是个好问题，是这样，后面讲泡利矩阵时会提到
-   ==这个问题暂不明确是什么意思==

Q. 描述三维量子态空间，为什么要用复向量呢，为什么left right in out像是在复数平面坐标轴上？
-   老师虽然举例用的三维坐标系，但实际上计算正交向量时是在二维复数向量空间里求解，即便老师解答了这个疑问，但这里实际上是有一种矛盾的。而且按老师自己的意思，思考复数向量空间问题需要避免用几何的方式去思考
-   当然老师自己也提到了，三维向量空间可以用二维复数向量空间来描述，复数坐标平面相当于就是二维的，有学生与我有同样的疑惑，也是觉得三维坐标系对应到二维复数向量空间有些奇怪
-   最后老师还提到，态空间和三维向量空间不同，态空间的正交和三维坐标正交不同

Q. 三维量子态空间，为什么只有三组正交向量，没有第四组会出现呢？
-   三维空间里只有三组

Q. 为什么说两个实数可以完全表示两个复数，也就是三维里面的状态？
-   两个复数由四个实数组成，归一化可以去掉一个实数，由于等价变换，相位没有意义，只有相位角度差有意义，再去掉一个实数

Q. 本章讲解态空间和三维正交空间时，提到光子的偏振问题
-   ==不清楚是什么意思==

Q. 测量能否区分x和z轴
-   单次实验区分不了x轴和z轴，因为得到值只有+1 -1，没有其他信息

Q. 投影有何物理意义
-   量子态在基向量上的投影，如果测量大量量子，投影对应的是实际测量的平均值

Q. 对易是什么
-   对易是运算的交换关系，后面讲到泊松括号时会提到

## 三、线性算符

### 记录

ket右矢分解
```math
\mid A > = \sum_i \alpha_i \mid i >

<j \mid A > = \sum_i \alpha_i < j \mid i > = \sum_i \alpha_i \delta_{ji} = \alpha_j

\mid A > = \sum_i \alpha_i \mid i > = \sum_i \mid i > < i \mid A >

< A \mid = \sum_i < A \mid i > < i \mid
```

线性算符
```math
M \mid A > = \mid B >

M z \mid A > = z M \mid A > = z \mid B >

M [ \mid A > + \mid B >] =  M \mid A > + M \mid B >

< i \mid M \mid A > = <i \mid B > = \beta_i

\sum_j < i \mid M \mid j > <j \mid A > = \sum_j < i \mid M \mid j > \alpha_j = \beta_i

线性算符M的矩阵元 < i \mid M \mid j > = M_{ij}

\sum_j M_{ij} \alpha_j = \beta_i
```

线性算符运算
```math

[<A \mid M] \mid B> = <A \mid [M \mid B >]

<i \mid M \mid j> = M_{ij}

\sum_{ij} [<A \mid i>< i \mid M] \mid j ><j \mid B>
= \sum_{ij} \alpha ^*_i M_{ij} \beta_j

M \mid A > = \mid B >

< A \mid M^\dagger = < B \mid

<j \mid M \mid i> = <j \mid i'>

<i \mid M^\dagger \mid j> = <i' \mid j>

<i \mid M^\dagger \mid j> = <j \mid M \mid i> ^*

M^\dagger_{ij} = M^*_{ji}
```

厄米共轭算符
```math
A^T = A^* 或 A^\dagger = A

A =  \left[ \begin{matrix} 3 & 2+i \\ 2-i &  1\end{matrix} \right]
```

本征矢和本征值
```math
M \mid I > = \lambda_I \mid I >
```

厄米算符的本征值是实数
```math
< I \mid M = < I \mid \lambda^*_I

< I \mid M \mid I > = \lambda_I < I \mid I > = < I \mid I > \lambda^*_I

\lambda_I = \lambda^*_I
```

厄米算符，不同的本征值对应的本征矢正交

```math
M \mid I > = \lambda_I \mid I >

M \mid J > = \lambda_J \mid J >

< J \mid M = \lambda_J < J \mid

< J \mid M \mid I > = \lambda_I < J \mid I >

< J \mid M \mid I > = \lambda_J < J \mid I >

(\lambda_I - \lambda_J) < J \mid I > = 0

如果 \lambda_I \neq \lambda_J \rightarrow < J \mid I > = 0
```

量子力学的四个基础假设
-   厄米算符的本征值都是实数，量子力学中用厄米算法代表Observables可观测量
-   可观测的可能值是本征值
-   确切的可观测的态是本征态（本征矢）
-   观测值的概率是量子态在本征矢上投影的内积（玻恩定则）
```math
P(\lambda_I) = <A \mid I> <I \mid A>

\sum_I <A \mid I> <I \mid A> = \sum_I \alpha^*_I \alpha_I = 1

<A \mid A> = 1
```

`$\sigma_z$`本征值和本征矢
```math
\sigma_z \mid u > = +1 \mid u >

\sigma_z \mid d > = -1 \mid d >

<u \mid \sigma_z \mid u > = <u \mid +1 \mid u > = 1

<d \mid \sigma_z \mid d > = <d \mid -1 \mid d > = -1

<u \mid \sigma_z \mid d > = <u \mid -1 \mid d > = 0

<d \mid \sigma_z \mid u > = <d \mid +1 \mid u > = 0

\sigma_z = \left[ \begin{matrix} 1 & 0 \\ 0 & -1\end{matrix} \right]
```

`$\sigma_x$`本征值和本征矢
```math
\sigma_x \mid r > = +1 \mid r >

\sigma_x \mid l > = -1 \mid l >

\mid u > = \frac{\mid r > + \mid l >}{\sqrt2}

\mid d > = \frac{\mid r > - \mid l >}{\sqrt2}

<u \mid \sigma_x \mid u > = \frac{1}{2} <r + l \mid \sigma_x \mid r + l > = \frac{1}{2} <r + l \mid r - l > = 0

<d \mid \sigma_x \mid d > = \frac{1}{2} <r - l \mid \sigma_x \mid r - l > = \frac{1}{2} <r + l \mid r + l > = 0

<u \mid \sigma_x \mid d > = \frac{1}{2} <r + l \mid \sigma_x \mid r - l > = \frac{1}{2} <r + l \mid r + l > = 1

<d \mid \sigma_x \mid u > = \frac{1}{2} <r - l \mid \sigma_x \mid r + l > = \frac{1}{2} <r - l \mid r - l > = 1

\sigma_x = \left[ \begin{matrix} 0 & 1 \\ 1 & 0\end{matrix} \right]
```

`$\sigma_y$`本征值和本征矢
```math
\sigma_y = \left[ \begin{matrix} 0 & -i \\ i & 0\end{matrix} \right]
```

泡利矩阵
-   一组三个2×2的幺正厄米复矩阵
-   共轭转置矩阵为其逆矩阵，就是幺正矩阵（酉矩阵）
-   +1 -1自旋量子态的三个矩阵`$\sigma_x$` `$\sigma_y$` `$\sigma_z$`，就是三个泡利矩阵

### 疑问
Q. 厄米算符是否具有物理性质，算符是否物理可读？
-   这也是到了这一章节的常见问题，厄米算符实际上只是一种数学概念，不具有物理意义。如需要观测量子态，后面的章节会提到需要用到量子纠缠才能观测
-   这里也体现了研究理论不应该试图让任何量有物理意义或者几何意义，很多时候这些都只是抽象概念

## 四、含时薛定谔方程与观测量的期望值

### 记录
量子力学扩展第五个假设
-   厄米算符的本征值都是实数，量子力学中用厄米算法代表Observables可观测量
-   可观测的可能值是本征值
-   确切的可观测的态是本征态（本征矢）
-   观测值的概率是量子态在本征矢上投影的内积（玻恩定则）
-   含时状态，`$U$`是线性算符（历史上`$U$`的定义也有过其他的假设，但都有各种各样的问题）
```math
\mid Ψ(t) > = U(t) \mid Ψ(0)>
```

两个含时系统，如果一开始正交，那么他们随时间一直正交，不受时间影响
```math
\mid \Psi(t) > = U(t) \mid \Psi(0)>

\mid \Phi(t) > = U(t) \mid \Phi(0)>

<\Phi(t) \mid \Psi(t)> = <\Phi(0) \mid U^\dagger (t) U(t) \mid \Psi(0)> =  \ <\Phi(0) \mid \Psi(0)> = 0

\therefore U^\dagger (t) U(t) = I \Rightarrow U(t)为酉算符
```

含时系统瞬间值，取`$\epsilon$`的一次级量
```math
\epsilon \rightarrow 0^+ 

U(\epsilon) = I - i\epsilon H

U^\dagger (\epsilon) = I + i\epsilon H^\dagger

U^\dagger (\epsilon) U(\epsilon) = I + i\epsilon (H^\dagger - H) = I \Rightarrow H^\dagger = H
```

由上式可知，`$H$`为厄米算符，在这里称为哈密顿算符，哈密顿量也就是能量

时间平移不变性，也就是`$H$`不随时间变化

根据含时系统瞬间值，得到微分方程，也就是一般形式的含时薛定谔方程
```math
\frac{\mid Ψ(\epsilon)> - \mid Ψ(0)>}{\epsilon - 0} = \frac{U(\epsilon)\mid \Psi(0)> - \mid \Psi(0) >}{\epsilon - 0} = - iH \mid \Psi(0) >

d\mid Ψ(t)>/dt = -iH \mid Ψ(t)>
```

关于本征值平均的定义
```math
\mid A > = \sum_i \alpha_i \mid \lambda_i >

P(\lambda_i) = \alpha^*_i \alpha_i

\sum_i \lambda_i P(\lambda_i) = < \lambda >

< \lambda > = \sum_i \lambda_i \alpha^*_i \alpha_i = <A \mid L \mid A>

其中L的本征值为\lambda

证明：< A \mid = \sum_j < \lambda_j \mid \alpha^*_j 

<A \mid L \mid A> = \sum_{ij} < \lambda_j \mid \alpha^*_j \alpha_i \lambda_i \mid \lambda_i >

<A \mid L \mid A> = \sum_{i} \alpha^*_i \alpha_i \lambda_i < \lambda_i \mid \lambda_i >
= \sum_{i} \alpha^*_i \alpha_i \lambda_i
```

随时间演化的平均值（海森堡运动方程）
```math
<\Psi(t) \mid L \mid \Psi(t)> = < L(t) >

\frac{d< L(t) >}{dt} = <\frac{d\Psi(t)}{dt} \mid L \mid \Psi(t)> + <\Psi(t) \mid L \mid \frac{d\Psi(t)}{dt}>

\frac{d < \Psi(t) \mid}{dt} = i < \Psi(t) \mid H

\frac{d< L(t) >}{dt} = i < \Psi(t) \mid HL \mid \Psi(t)> - i < \Psi(t) \mid LH \mid \Psi(t)>

= i <\Psi(t) \mid (HL - LH)\mid \Psi(t) > 

= i <\Psi(t) \mid [H,L] \mid \Psi(t) > \ [H,L]称为对易子(commutator)

= i <[H,L]>
```

狄拉克寻找量子力学与经典力学的关系，便是从对易子出发
```math
ih\{L, H\} = [L, H]
```

泊松括号与量子力学对易子的对称关系
```math

\{L,H\}=-\{H,L\}

[L,H]=-[H,L]

\{LM,H\} = \{L,H\}M + L\{M,H\}

[LM,H] = LMH - HLM = [L,H]M + L[M,H]
```

能量（哈密顿量）随时间的变化
```math
\frac{d<H(t)>}{dt} = -\frac{i}{h}[H,H] = -i/h · 0 = 0
```

根据上式，能量随时间变化的平均值的时间微分为0，这便是能量守恒

### 疑问
Q. `$U(e) = I - ieH$`为什么可以这样假定？
-   因为`$U$`是单位算符，长度是`$I$`

Q. 如何选择`$H$`算符？
-   这可以参考经典力学选择哈密顿量和拉氏量的理由，`$H$`也可以与能量有关

Q. 可逆性为什么就是信息守恒？
-   ==这里还不清楚==

Q. 叠加守恒原理是什么？
-   ==这里还不清楚==

Q. 如果`$H$`是时间变化的，那么是否系统还满足能量守恒呢？
-   这一章只分析了`$H$`随时间不变的系统，如果`$H$`变化是否守恒还没有证明
-   ==更一步的暂不清楚==

Q. 老师提到能量守恒有更强意义上的守恒，指的是什么？
-   ==这里还不清楚==

Q. 有学生提问，凭什么知道H就是能量，如何判断这就是能量守恒，老师提到要和经典力学对应，经典力学其实是对量子力学的近似
-   这其实是物理学家的一种直觉，先得到公式，然后再做实验去证明理论是否合理，狄拉克的出发点便是认为量子力学与经典力学应该要有一种对应关系

Q. 测量过程就是建立系统与设备之间的纠缠态的过程，这个如何理解？
-   量子纠缠就是测量，后面的章节能够深入体会其中含义

## 五、含时薛定谔方程

### 记录

如果两件事情是同时可测量的，则这两个算符是可对易的，也就是可以找到一组状态基，同时是两个算符的本征矢

线性无关与正交不一样，数学里的基只需要线性无关

不含时系统，如果用`$H$`哈密顿算符测量，得到的就是能量（物理学家要做的就是找到`$H$`）
```math
H \mid E_i> = E_i \mid E_i>
```

柏松括号里面是一些微分操作，看起来，微分和矩阵存在一些相似性
```math
\frac{dL}{dt} = -i[L,H]

\frac{dL}{dt} = \{L,H\}

\{L,H\} <=> -\frac{i}{h}[L,H]
```
-   其中普朗克常数使得两者量纲一致，这也就是狄拉克确定量子力学的公式
-   如果把量子力学用在经典力学里，量子尺度的力是一个很小的量，这与物理的实际相符合
-   `$L$`可以是任何量，不一定需要是角动量，对于量子力学，`$L$`是厄米算符

entanglement 纠缠态

解薛定谔方程
-   用一般的微分方程求解（核心思想其实就是把矩阵按照正交基分解，然后求系数，也就是解线性代数方程）
```math
\mid \Psi(t)> = \sum_j \alpha_j(t)\mid j >

\frac{d\mid \Psi(t)>}{dt} = \sum_j \alpha_j(t)(-i)H\mid j >

\frac{d\alpha_j(t)}{dt} = -iE_j\alpha_j(t)

\alpha_j(t) = \alpha_j(0)e^{-iE_jt}

\mid \Psi(t)> = \sum_j \alpha_j(0)e^{-iE_jt} \mid j >
```

求解`$L$`随时间变化的平均值
```math
<L> = < \Psi(t) \mid L \mid \Psi(t)>

= \sum_k \alpha_k(0) e^{iE_kt}<k \mid L \sum_j \alpha_j(0)e^{-iE_jt} \mid j >

= \sum_{jk} \alpha_k(0)\alpha_j(0)e^{i(E_k - E_j)t}<k \mid L \mid j>

= \sum_{jk} \alpha_k(0)\alpha_j(0)e^{i(E_k - E_j)t}L_{kj}
```

以上其实就是平均值随时间变化的海森堡矩阵表示

这个矩阵有一个有趣的地方，每一个观测值有两个相关的频率`$E_k$` `$E_j$`

`$\Psi$`也是位置的函数，不只是时间的函数，相当于现在计算的是时间的偏微分，进一步工作后续课程会涉及到

有学生提问对于状态正交的假设是否只是经验事实，老师说有研究者做过其他的尝试，但一直不完善，比如概率不守恒，概率不是正的，非局域性问题，可以从无限远处沟通

有两种科学理论，一种是塑形流体，一种是脆性开裂，塑形流体比如广义相对论可以调整参数一点点改变，而狭义相对论和量子力学就是脆性开裂，稍微改变一点假设就会出问题

计算磁场中的单个自旋问题，假定磁场沿着z轴
```math
H = \frac{w}{2}σ_z

\frac{d\sigma_x}{dt} = -i[\sigma_x,\sigma_z]\frac{w}{2}

\frac{d\sigma_y}{dt} = -i[\sigma_y,\sigma_z]\frac{w}{2}

\frac{d\sigma_z}{dt} = -i[\sigma_z,\sigma_z]\frac{w}{2} = 0

\sigma_z = \left[ \begin{matrix} 1 & 0 \\ 0 & -1\end{matrix} \right]
\sigma_x = \left[ \begin{matrix} 0 & 1 \\ 1 & 0\end{matrix} \right]
\sigma_y = \left[ \begin{matrix} 0 & -i \\ i & 0\end{matrix} \right]

[\sigma_z,\sigma_x] = 2\left[ \begin{matrix} 0 & 1 \\ -1 & 0\end{matrix} \right]
= 2i\sigma_y,
[\sigma_x,\sigma_y] = 2i\sigma_z,
[\sigma_y,\sigma_z] = 2i\sigma_x

\frac{d\sigma_x}{dt} = -w\sigma_y = -w \left[ \begin{matrix} 0 & -i \\ i & 0\end{matrix} \right]

\frac{d\sigma_y}{dt} = -w\sigma_x = -w \left[ \begin{matrix} 0 & 1 \\ 1 & 0\end{matrix} \right]
```

角动量的泊松符号
```math
\{L_z,L_x\} = L_y
```

与经典力学对比，自旋子也是绕着z轴在x和y轴上做圆周运动（平均值），这也就是解出了该问题

上面这个题相当于系统随时间变化是常数，不是时间t的函数，所以求解比较简单，也就不需要用薛定谔方程的一般解了

有学生就提到了，如果把自旋耦合到这个系统中观察实际状态会有什么特征，老师说z轴的up和down的状态是相差一个`$w$`的，自旋会从高能级到达低能级，发射一个光子，光子的能量就是`$w$`

这个例子里的磁场是作为一个设备存在的，也就是不会受到电子或者其他的影响，是一个稳定的很重的设备

自旋沿着n轴旋转
```math
σ · n = \left[ \begin{matrix} nz & nx-iny \\ nx+iny & -nz\end{matrix} \right]
```
写法是，n为单位向量，哈密顿量H就需要按照这个矩阵去算

`$σ · n$`计算本征值
```math
\lambda_1 \lambda_2 = -1

\lambda_1 + \lambda_2 = 0
```

上式解为-1和+1，也就是说，无论自旋沿着哪个轴旋转，在这个系统里，特征值都不变  

随时间状态变化的系统就是动力系统

符号上加一个圆点是微分的意思

指数e的复共轭也是实部不变虚部取反，这可以把指数先用cos和sin表达，然后映射到复平面上去

### 疑问
Q. 为什么说`$\sigma_x$` `$\sigma_y$` `$\sigma_z$`不对易？
-   根据前面章节推导的算符矩阵，进行计算，对易子刚好得到的是正交基中第三个基的线性表达式

Q. 磁场作用下`$H$`为什么这样定义，`$w$`等于多少？
-   ==具体要看电动力学==

Q. 泊松括号的角动量表达式是什么？
-   ==具体要看经典力学==

Q. 为什么量子力学对易子是比经典力学柏松括号更为基本的？
-   物理学家认为经典力学是量子力学的一种近似

Q. 为什么说如果自旋周围没有任何事物，处于一个独立的系统中，能量和哈密顿量为零？
-   因为处于这样一个系统中，状态不随时间变化，相当于时间函数微分为0，`$H$`为0
-   如果把自旋放在磁场中，它会促进自旋，那么就有能量和哈密顿量了，而且哈密顿量和磁场方向有关

Q. 为什么说沿着z轴的磁场，x和y方向的可观测量就像做圆周运动一样？
-   ==具体要看电动力学==

Q. 反复有学生提问，关于磁场`$w$`的方向问题
-   老师强调`$w$`只是大小

Q. 计算矩阵本征值，需要用到迹和行列式
-   ==具体要看线性代数==

## 六、纠缠态

### 记录

由于测量设备也是量子设备，所以测量和系统要合并一起考虑，这是一个复合系统

`$S_A$`（观测设备态）和`$S_I$`（量子自旋态）两个的张量积，组合成一个状态`$S_{AI}$`，维度是`$D_A · D_I$`，这个有些类似于力学中的应力，不同的切面对应的应力不同

关于张量的介绍看笔记的最后部分

如果第一个量子测量z轴，第二个量子测量x轴，分别都得到了+1，状态是
```math
\mid u r> = \mid u u> + \mid u d>
```

两个自旋量子同时测量的例子，两个自旋有4个基向量，组成张量，张量基的系数是4个复数`$\alpha_{uu}$` `$\alpha_{ud}$` `$\alpha_{dd}$` `$\alpha_{du}$`，也就是8个实数，归一化处理，相位绝对值不重要，可以减去两个实数，也就是总共6个实数描述了两个自旋量子的状态

两个自旋量子独立测量的例子，分别为`$\alpha_{u}$` `$\alpha_{d}$` `$\beta_{u}$` `$\beta_{d}$`，分别是两组两个虚数即四个实数表示，减去归一化和相位，是两组2个实数，加起来共4个实数

结合以上两点，可以发现独立观测状态少于同时观测，这说明不是所有的状态都是乘积状态，也就是会有相关性，也就是量子纠缠

复合系统的独立观测
```math
\sigma_x \mid u > = \mid d>，\sigma_x \mid d> = \mid u>

\sigma_x \mid u \ i> = \mid d \ i>，\sigma_x \mid d \ i> = \mid u \ i>
```

复合系统的同时观测
```math
\sigma_x \tau_x \ \mid u \ u> = \tau_x \sigma_x \mid u \ u>
```

以上这种情况，是可对易的，可以同时测量两个量子

对于一个量子自旋系统中，`$\sigma_x$` `$\sigma_y$` `$\sigma_z$`不可能三者内积全部为0，因为总会存在`$\sigma_n$`这个方向恒等于+1

复合系统同时观测两个自旋量子时，存在一些特殊情况，能量在x y z三个方向都为0，例如
```math
\mid u \ d> - \mid d \ u>
```

以上这种状态，就是纠缠态，这说明两个量子之间有了关联性（互为相反），无法独立观测

以上提到的状态是一种能量特别小的状态，两个量子放在一起，发射一个光子后，就很容易达到这种状态，称为singlet

在singlet情况下
```math
< \sigma_z > = 0

< \sigma_x > = 0

< \sigma_y > = 0

< \sigma_x \tau_x> = -1

< \sigma_y \tau_y> = -1

< \sigma_z \tau_z> = -1
```

有个同学提问，singlet是否改变基后也有这个特性，教授回答singlet可以用left right来同样表示，这就是singlet的一个特殊性质，在每个基里都是一样的

### 疑问
Q. 薛定谔方程描述的是纯粹的量子力学，而考虑到使用量子仪器测量时，需要把两者都考虑进来，则有波函数的坍缩问题，这里是什么意思？
-   量子纠缠观测后，量子的波函数坍缩，得到了一个具体的状态

Q. `$\sigma_x$` `$\sigma_y$` `$\sigma_z$`作用在张量上的意义是什么，比如σx|u i> =  |d i>的意义
-   这里指的是哈密顿量`$H$`作用在不同的自旋态上的结果，这个结果反应了观测系统的状态
-   这样做的物理意义是什么，教授回答这只是一种辅助手段，没有特定的物理意义

Q. 非局域性non-locality是什么意思？
-   信息的传递不能超光速

Q. 关于用计算器模拟量子的那一段是什么意思？
-   教授的意思是量子之间并不像计算机用线连着传递了信息，没有传递信息就不违背非局域性，不能用经典逻辑分析量子逻辑
-   但我始终觉得这里有些牵强

Q. 衡量纠缠强度的量子纠缠熵是什么？
-   ==这里不清楚== 

Q. 教授提到约翰贝尔发现的问题是什么？提到了不能用经典推理逻辑运用到量子里，这是为什么，还有提到了并没有非局域性
-   这里其实一直都有争议，也就是EPR佯谬

## 七、密度矩阵

### 记录

波函数
```math
量子态 \mid \Psi >

\mid a \ b \ c >

\mid \Psi > = \sum_{abc} <a \ b \ c \mid \Psi> \mid a b c>

波函数 \Psi(a \ b \ c) = <a \ b \ c \mid \Psi>

\mid \Psi > = \sum_{abc} \Psi(a \ b \ c) \mid a b c>
```

波函数为`$\Psi$`的量子态下`$L$`算符的期望值
```math
<a \mid L \mid a'> = L_{aa'}

< \Psi \mid L \mid \Psi >

< \Psi \mid = \sum_{a'b'c'}<a' \ b' \ c' \mid \Psi^*(a' \ b' \ c')

< \Psi \mid L \mid \Psi > = \sum_{a'b'c'abc}<a' \ b' \ c' \mid \Psi^*(a' \ b' \ c') L \Psi(a \ b \ c) \mid a \ b \ c >

只考虑基a：
< \Psi \mid L \mid \Psi > = \sum_{a'a}<a' \mid \Psi^*(a') L \Psi(a) \mid a>

= \sum_{a'a} \Psi^*(a') L \Psi(a) L_{a'a}
```

Alice Bob系统

```math
基：\mid a> 和 \mid b \}

张量：\mid a \ b >

波函数：<a \ b \mid \Psi> = \Psi(a \ b)

复合系统算符：L_a \ M_b

L_{a'b'ab} = <a' \ b' \mid L \mid a \ b> = δ_{b'b} L_{a'a}

M_{a'b'ab} = <a' \ b' \mid M \mid a \ b> = δ_{a'a} M_{b'b}

Ψ(a b) = Ψ_A(a)Φ_B(b)，Ψ^*(a' b') = Ψ^*_A(a')Φ^*_B(b')

<Ψ|L|Ψ> = \sum_{a'ab'b} Ψ^*_A(a')Φ^*_B(b') L_{a'a} δ_{b'b}Ψ_A(a)Φ_B(b) 

\Rightarrow \sum_{a'ab} Ψ^*_A(a')Φ^*_B(b) L_{a'a}Ψ_A(a)Φ_B(b)  

对Φ_B(b)做归一化处理，Φ^*_B(b)Φ_B(b) = 1

\Rightarrow \sum_{a'a} Ψ^*_A(a')L_{a'a}Ψ_A(a) 
```
这也就是说明在直积态里，Alice的`$L$`算符的期望值与Bob无关

同理，Bob的`$M$`算符的期望值与Alice也无关

考虑`$L$` `$M$`的乘积系统，要注意的点是，这里先不需要考虑`$L$` `$M$`乘积的实际意义
```math
<Ψ|LM|Ψ> = \sum_{a'ab'b} Ψ^*_A(a')Φ^*_B(b') L_{a'a} M_{b'b}Ψ_A(a)Φ_B(b) 

\Rightarrow \sum_{a'ab'b} Ψ^*_A(a')L_{a'a}Ψ_A(a) Φ^*_B(b')L_{b'b}Φ_B(b)  

独立求和 \sum_{a'a} Ψ^*_A(a')L_{a'a}Ψ_A(a)\sum_{b'b}Φ^*_B(b')L_{b'b}Φ_B(b) 

\Rightarrow <LM> = <L><M>
```
#### 纠缠态

Alice和Bob纠缠态的相关性就是
```math
<LM> - <L><M>
```

singlet的量子态
```math
\Psi = \frac{\mid u d> - \mid d u>}{\sqrt{2}}
```

根据之前的计算
```math
\sigma_z = \left[ \begin{matrix} 1 & 0 \\ 0 & -1 \end{matrix} \right]
\sigma_x = \left[ \begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \right]
\sigma_y = \left[ \begin{matrix} 0 & -i \\ i & 0 \end{matrix} \right]

<\sigma_z> = 0
<\tau_z> = 0

<\sigma_x> = 0
<\tau_x> = 0

<\sigma_y> = 0
<\tau_y> = 0

<\sigma_z \tau_z> = -1
<\sigma_x \tau_x> = -1
<\sigma_y \tau_y> = -1
```

`$LM$`其实没有物理意义，只是一种数学运算，这也不是测量，`$L$`和`$M$`都只是算符

除singlet另外还有triplet，是处于高能态

#### 密度矩阵

纠缠态下的期望计算
```math
<Ψ|L|Ψ> = \sum_{a'ab} Ψ^*_{a'b} L_{a'a} δ_{b'b} Ψ_{ab}

\Rightarrow \sum_{a'ab} Ψ^*_{a'b} Ψ_{ab} L_{a'a}

\Rightarrow 密度矩阵 \rho_{a'a} = \sum_{b} Ψ^*_{a'b} Ψ_{ab}

<L> = \rho_{a'a} L_{a'a}
```

有越多的非零本征值说明有越多的纠缠态，如果只有一个非零本征值，说明不纠缠

测量是纠缠的过程

### 疑问
Q. 粒子的x y z位置的三个分量可以对易，而位置和动量的分量不可对易，这是为什么？
-   ==具体原因不清楚==，应该指的是坐标可以同时测量，但位置和动量不可同时测量

Q. 薛定谔的波函数为什么是Ψ(a b c)这个的特例？
-   ==这里不清楚为什么==

Q. a' b'和a b是什么关系？
-   a'和a，b'和b是同一组向量，只是在计算时为了计算方便区分一下

Q. 如下向量点积为什么是厄米算符和哈密顿量，singlet为什么是其本征矢，特征值为什么是-3，为什么Alice不能同时测量`$σ_x$` `$σ_y$` `$σ_z$`？
```math
\vec{\sigma}·\vec{\tau} = \sigma_x \tau_x + \sigma_y \tau_y + \sigma_z \tau_z
```
-   ==这里不清楚为什么==

Q. 密度矩阵求和的`$a'a$`到哪里去了，然后分析直积态的特征值是如何计算的
-   ==这里不清楚为什么==

Q. 密度矩阵坍缩是什么意思？
-   纠缠态下，密度矩阵就是用来描述自身子系统，坍缩指的是概率变为在一个状态上恒定

## 八、连续体系的量子力学

### 记录

时间演化的波函数，可以看到酉矩阵U，使得密度矩阵不会互相干扰，无论是否纠缠，从这个意义来上来说，密度矩阵是不会互相影响的，这里是满足局域性的
```math
Ψ(b) \rightarrow \sum_{b'} U_{bb'} Ψ(b')

Ψ(a b) \rightarrow \sum_{b'} U_{bb'} Ψ(a b')

Ψ^*(a' b) \rightarrow \sum_{b'_1} Ψ^*(a'b'_1) U^+_{bb'_1}

\rho_{aa'} = \sum_{b b' b'_1} Ψ^*(a'b'_1) [U^+_{bb'_1} U_{bb'}] Ψ(a b')

= \sum_{b' b'_1} Ψ^*(a'b'_1) \delta_{b'_1b'} Ψ(a b')

= \sum_{b'} Ψ^*(a'b') Ψ(a b')

```

波函数坍缩就是密度矩阵坍缩，测量时密度重新设置为坍缩态

单个自旋沿一维轴运动，不能同时测量动量和位置，因为这两者不对易

连续位置x的波函数
```math
<x \mid Ψ> = Ψ(x)

P(x) = Ψ^*(x) Ψ(x)

<a \mid a'> = \delta_{aa'} \rightarrow \delta(a - a') 


\sum_{x} P(x) = 1 \rightarrow \int Ψ^*(x) Ψ(x) dx = 1
```

其中`$\delta$`函数就是狄拉克函数，信号与系统里面也见过，是一个冲击函数，并没有数学物理意义，只是从离散扩展到连续后，为了方便计算概率，这是一种抽象思想，不一定非要套上已有的概念

波函数积分，求和转变为了积分
```math
\mid Ψ> = \int dx Ψ(x) \mid x>

<x\mid Ψ> = \int dx' Ψ(x') <x\mid x'> = \int dx' Ψ(x') \delta(x - x')
```

内积计算
```math
<Ψ \mid \Phi> = \int dx Ψ^*(x) \Phi(x)
```

线性算符
```math
M\mid Ψ> \rightarrow \mid Ψ'>

M\mid Ψ(x)> \rightarrow \mid Ψ'(x)>

<\Phi \mid M \mid Ψ> = <\Psi \mid M^\dagger \mid \Phi>^*
```

位置函数x的线性算符
```math
<\Phi \mid f(x) \mid Ψ> = \int \Phi^*(x) f(x) Ψ(x) dx = \int (\Psi^*(x) x \Phi(x))^* dx
```

微分算符
```math
D \mid \Psi > \rightarrow \frac{dΨ(x)}{dx}

<\Psi \mid P \mid \Phi> = \int \Psi^*(x) \frac{d\Phi(x)}{dx}

<\Phi \mid P \mid \Psi> = \int \Phi^*(x) \frac{d\Psi(x)}{dx}

<\Phi \mid P \mid \Psi>^* = - \int \Phi(x) \frac{d\Psi^*(x)}{dx}
```

微分算符中对称的两部分是分部积分的两部分
```math
\int \Psi^*(x) \frac{d\Phi(x)}{dx} = - \int \Phi(x) \frac{d\Psi^*(x)}{dx}
```

动量P微分厄米算符
```math
P = -i \frac{d}{dx}

<\Psi \mid P \mid \Phi> \rightarrow \int \Psi^*(x) (-i\frac{d}{dx}) \Phi(x)
= -i \int \Psi^*(x) \frac{d\Phi(x)}{dx}

<\Phi \mid P \mid \Psi>^* = +i \int \Phi(x) \frac{d\Psi^*(x)}{dx}

<\Psi \mid P \mid \Phi> = <\Phi \mid P \mid \Psi>^*
```

关于动量P微分厄米算符，也是狄拉克认为对易子与柏松括号应该要有对应关系推导而来

x和P对易子
```math
(Px)\Psi(x) = -i\frac{d(x\Psi(x))}{dx} = -i(\Psi(x) + x\frac{d\Psi(x)}{dx})

xP\Psi(x) = -ix \frac{d\Psi(x)}{dx}

[x, P]\Psi(x) = i\Psi(x)

[x, P] = ih

\{x, P\} = 1

```

以上量子力学与经典动力学的对称，是狄拉克研究的出发点，他是反推出了P微分厄米算符

### 疑问
Q. 为什么微分也可以成为算符？
-   是算符，而且也可以证明是线性算符

Q. 复数的分部积分是如何证明的？
-   ==参考微积分==

## 九、位置与动量波函数的变换

### 记录

平面波

```math
e^{ipx} = cos(px) + isin(px)
```

傅立叶变换

其中x是位置，p是频率（动量）

```math
\psi(x) = \int \frac{dp}{\sqrt{2\pi}} \psi_p(p) e^{ipx}

\psi_p(p) = \int \frac{dx}{\sqrt{2\pi}} \psi(x) e^{-ipx}
```

狄拉克`$\delta$`函数的性质

```math
\delta(x - x')F(x) = F(x') \delta(x - x')

\int \delta(x - x') = 1

\int \delta(x - x') F(x) = F(x')

F(x) \int \delta(x - x')dx = F(x')
```

狄拉克`$\delta$`函数与傅立叶变换的关系

```math
\psi(x') = \int \frac{dp}{\sqrt{2\pi}} e^{ipx'} [\int \frac{dx}{\sqrt{2\pi}} \psi(x) e^{-ipx}]
= \int dx \int \frac{dp}{2\pi} e^{ip(x' - x)} \psi(x)
= \int dx \Delta(x' - x) \psi(x)

\int \frac{dp}{2\pi} e^{ip(x - x')} = \delta(x - x')

\int \frac{dx}{2\pi} e^{i(p - p')x} = \delta(p - p')
```

量子的位置动量分析

```math
\mid x >
\mid p >

\mid x p >

\mid \psi > = \int \psi(x) \mid x > dx

<x \mid \psi > = \psi(x)

P(x) = \psi^*(x) \psi(x)

<x' \mid x> = \delta_{xx'} = \delta(x - x')

<\psi \mid \phi> = \int \psi^*(x) \phi(x) dx
```

#### `$X$`一维空间位置算符

参考上一章`$X$`线性算符

```math
X \mid \psi >

X \psi(x) = x \psi(x)
```

根据位置特征，尝试用`$\psi(x) = \delta(x - x_o)$`代入，再利用狄拉克`$\delta$`函数性质
```math
x \delta(x - x_o) = x_o \delta(x - x_o)
```

得到`$X$`算符的本征矢是`$\delta(x - x_o)$`，本征值是`$x_o$`

#### `$P$`动量算符

参考上一章`$P$`动量厄米算符，其中`$D$`是微分算符，有

```math
P = -ihD

P \psi(x) = -ih\frac{d \psi}{d x}
```

以上微分方程求解得到本征矢，也就是指数解（波函数）
```math
< x \mid p > = \psi_{p_o}(x) = e^{\frac{ip_ox}{h}}
```

根据波函数，得到波长`$\lambda$`与动量p的关系
```math
\frac{p_o}{h} \lambda = 2\pi

\lambda = \frac{2\pi h}{p_o}
```

动量本征矢内积（归一化了`$h$`常量）
```math
<p' \mid p> = \int e^{-ip'x} e^{ipx} dx = \int e^{i(p - p')}dx
```

这个函数有如下两个性质，看起来就像狄拉克`$\delta$`函数
-   `$p'$`不等于`$p$`时，根据正交性，上式为应该0，分析`$e^{i(p - p)}$`是正弦波和余弦波的组合，无穷区间的积分由于正负概率相等，积分为0
-   `$p'$`等于`$p$`时，积分得到的是无穷大

根据以上粒子的波函数分析，可以发现测量的位置不确定，但动量是确定的

#### 动量空间波函数

```math
<p \mid \Psi > = \Psi(p) = \int \frac{e^{-ipx}}{\sqrt{2\pi}} \Psi(x) dx

P(p) = \Psi^*(p) \Psi(p)

P = -i\frac{d}{dx}

X = i\frac{d}{dp}
```

#### 哈密顿相对论性粒子

含时薛定谔方程
```math
ih\frac{d \mid \Psi >}{dt} = H \mid \Psi >
```

令H = cp （c是光速常量，p是动量），代入`$P$`算符

```math
ih\frac{d \Psi(x t)}{dt} = -c ih\frac{d \Psi(xt)}{dx}

\Psi(x-ct) = 0

\frac{dH}{dp} = X^o = c

\frac{dH}{dx} = -P^o = 0
```

由`$-P^o = 0$`可知动量守恒，由`$X^o = c$`可知速度为光速

这样的波函数，随时间变化是以速度c匀速运动的

#### 哈密顿非相对论性粒子

经典粒子由如下性质

```math
T = \frac{1}{2}mv^2

P = mv

H = \frac{P^2}{2m}
```

代入薛定谔方程
```math
ih\frac{d\Psi}{dt} = \frac{1}{2m}(-ih)^2\frac{d^2 \Psi(x)}{dx^2}
```

计算过程省略，如上求解得到的波函数具有一个性质，不同波长的波以不同的速度运动，这样的波函数无法保持自身的形状

### 疑问
Q. 位置x的分析时，计算本征值和本征矢`$\delta$`函数时如何得到的？
-   相当于是猜了一组解

Q. 为什么p可以认为是动量？
-   ==具体的不清楚==，简单来说就是具有动量的性质，比如动量守恒

Q. 哈密顿算符是如何推出来的？
-   ==具体的不清楚==

Q. 傅立叶的推导是否严谨？
-   这一章需要去看傅立叶变换相关的书籍，有更严密的论证

Q. 经典粒子的哈密顿量是多少？
-   ==需要参考动力学==

## 十、海森堡不确定性原理

### 记录

根据以上章节，可知x和p不对易，x和p的本征矢完全不同，x的本征矢是狄拉克`$\delta$`函数，而p本征矢是复数，也就是正弦和余弦函数的叠加

不确定性定义

其实也就是概率中的方差

```math
(\Delta x)^2 = <x^2> - (<x>)^2

其中<x> = 0

\rightarrow (\Delta x)^2 = <x^2>
```

位置的不确定性

```math
(\Delta x)^2 = <x^2> = \int \Psi^*(x) \Psi(x) x^2 dx
```

动量的不确定性

```math
(\Delta p)^2 = <p^2> = \int \Psi^*(x) \Psi(x) p^2 dx

其中 p=-i\frac{d}{dx}, p^2 = -\frac{d^2}{dx^2}

(\Delta p)^2 = -\int \Psi^*(x) \frac{d^2\Psi(x)}{dx^2} dx

\because \int F \frac{dG}{dx} dx = - \int \frac{dF}{dx}Gdx

\therefore (\Delta p)^2 = \int \frac{\Psi^*(x)}{dx} \frac{d\Psi(x)}{dx} dx
```

三角不等式

```math
\mid A \mid + \mid B \mid > \mid C \mid

\mid A \mid + \mid B \mid > \mid A+B \mid

\mid A \mid \cdot \mid B \mid > \mid A \cdot B \mid
```

不确定性原理不等式

定义`$X$` `$P$`算符作用在波函数上有
```math
\mid A > = X \mid \Psi> = x \Psi(x)

\mid B > = P \mid \Psi> = -i\frac{d\Psi(x)}{dx}

\mid A \mid ^2 = (\Delta x)^2 = \int \Psi^*(x) \Psi(x) x^2 dx

\mid B \mid ^2 = (\Delta p)^2 = \int \frac{\Psi^*(x)}{dx} \frac{d\Psi(x)}{dx} dx

\mid A \cdot B \mid ^2 = \int \Psi(x) x \frac{d\Psi(x)}{dx}dx \int \Psi(y) y \frac{d\Psi(y)}{dy}dy 

\because \frac{1}{2}\frac{d\Psi^2}{dx} = \Psi\frac{d\Psi}{dx}

\therefore \mid A \cdot B \mid ^2 = \frac{1}{4} \int x \frac{d\Psi^2(x)}{dx}dx \int y \frac{d\Psi^2(y)}{dy}dy
= \frac{1}{4} \int \frac{dx}{dx} \Psi^2(x)dx \int \frac{dy}{dy} \Psi^2(y)dy
= \frac{1}{4} \int \Psi^2(x)dx \int \Psi^2(y)dy

\because \Psi^2是归一化的概率密度 \rightarrow \int \Psi^2(x)dx = 1

\therefore \mid A \cdot B \mid ^2 = \frac{1}{4} \rightarrow \Delta x \Delta p > \frac{1}{2} 

考虑到h常数 \rightarrow \Delta x \Delta p > \frac{h}{2}
```

时间与能量，角度与角动量，都有不确定性性质

经典粒子分析，把粒子放在力场中，受到势能V
```math
H = \frac{p^2}{2m} + V(x)
```

代入薛定谔方程
```math
\frac{d\Psi(x,t)}{dt} = \frac{i}{2m} \frac{d^2\Psi(x)}{dx^2} + V(x) \Psi(x)

\frac{d\Psi^*(x,t)}{dt} = -\frac{i}{2m} \frac{d^2\Psi^*(x)}{dx^2} + iV(x) \Psi^*(x)
```

分析位置x的时间微分，也就是速度v
```math
\frac{d<x>}{dt} = \frac{d}{dt} \int \Psi^*(x) x \Psi(x) dx = \int d\Psi^* x \Psi + \int \Psi ^* x d\Psi

两部分复共轭 \rightarrow \frac{d<x>}{dt} = 2 \int \Psi^* x d\Psi
= 2 \int \Psi^* x (\frac{i}{2m} \frac{d^2 \Psi}{dx^2} - iV(x)\Psi)

去掉虚部 \rightarrow \frac{d<x>}{dt} = 2 \int \Psi^* x (\frac{i}{2m} \frac{d^2 \Psi}{dx^2})
= -2 \int \Psi^* \frac{i}{2m} \frac{d}{dx} \Psi
= \frac{1}{m} \int \Psi^* p \Psi
= <\Psi \mid \frac{p}{m} \mid \Psi> = \frac{<p>}{m}

\rightarrow \frac{d<x>}{dt} = \frac{<p>}{m}
```

分析动量p的时间微分，也就是力F
```math
\frac{d<p>}{dt} = \frac{d}{dt} \int \Psi^*(xt) \frac{d}{dx} \Psi(xt) (-i)
= -i (\int \frac{d\Psi^*}{dt} \frac{d\Psi}{dx} - \int \frac{d\Psi^*}{dx} \frac{d\Psi}{dt})

两部分复共轭 \rightarrow \frac{d<p>}{dt} = 2i \int \frac{d\Psi^*}{dx} \frac{d\Psi}{dt})

代入薛定谔方程，去掉虚部 \rightarrow \frac{d<p>}{dt} = 2 \int \frac{d\Psi^*}{dx} V(x) \Psi

代入复共轭部分 \rightarrow \frac{d<p>}{dt} = \int \frac{d\Psi^*}{dx} V(x) \Psi + \int \Psi^* V(x) \frac{d\Psi}{dx} = \int V(x) \frac{d\Psi^* \Psi}{dx}
= - \int \Psi^* \frac{dV(x)}{dx} \Psi

\rightarrow \frac{d<p>}{dt} = - <\frac{dV}{dx}>
```

如下关系只在波函数集中在很窄区域内才等价
```math
<F(x)> = F(<x>)
```

关于不确定性的分析，m很大时，波函数很集中，势能平滑，m很小时，势能尖锐不稳
```math
\Delta x \Rightarrow \frac{h}{m \Delta v}
```

### 疑问
Q. 费米子与泡利不相容是什么？波色子是什么？
-   ==不清楚，需要看相关书籍==

## 备注

### 学习过程中的思考
中学时期老师讲课大家听不懂的原因是没有讲思想，数学物理思想对应的方法论掌握了一切都是一个套路，概率论和分析数学的思路不同，线性代数的思路又不同，三者代表了三种思想，同时也是应用在了不同类型的物理理论上

分析数学用来求微积分，解决经典力学的问题

概率论用来解热力学和统计力学的问题

线性代数用于量子力学中，是在多维度层面抽象解决问题

动力学就是状态随时间变化的系统，随机过程其实也可以认为是概率论动力学，把概率论放在时间状态变化的系统里进行分析

量子力学，由于自旋状态是离散的，用线性代数好分析，如果是热力学，比如气体分子，就只能用概率论的方法去分析，比如用随机过程的泊松过程

现代物理学是四大力学，经典力学，电动力学，量子力学，统计力学

### 张量
张量的意义，当参照系变化时（其实就是基向量变化），其分量也会相应变化，最后结果就是基向量与分量的组合（也就是张量）保持不变

标量是零阶张量，向量是一阶张量

固体物理的力学分析，其中表面分为`$S_x$` `$S_y$` `$S_z$`三个方向，力在表面也分为`$F_x$` `$F_y$` `$F_z$`三个方向，所以表明所有的方向，需要这样的3 x 3的组合共9个量，也就是二阶张量

再继续扩展，三阶张量则是3 x 3 x 3共27个量

两个或多个无相互作用的粒子之间的耦合态就是这两个粒子态之间的张量积
