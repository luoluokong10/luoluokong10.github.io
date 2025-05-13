# 01 - 吸引子

> [课程链接](https://www.bilibili.com/video/BV1vw411Y7gS)
> 

## 动机

为了描述 PDEs 解的长期行为，特别是当 $t\to \infty$ 时的极限行为，引入吸引子理论。

\begin{CD}
   u_0 @>t\leq t_{\varepsilon}\>> 落入\mathscr{A} \\\\
@Vt\to\infty VV @VVt\geq t_{\varepsilon}V \\\\
   S(t)u_0 @< \<< ode约化
\end{CD}

在有限时间 $t_\varepsilon$ 解落入吸引子(集合) $\mathscr{A}$ 的 $\varepsilon$ 邻域；借助计算方法处理，如 Galerkin 方法；

在无穷时间，考虑进行有限约化，转换为 $ode$ 方程去处理。

### 约化方法

当分型维数 $\dim_f(\mathscr{A}) \leq n$，存在平面 $L\sim \mathbb{R}^{2n+1}$. 

考虑投影算子 $P: A\to PA \subset L$, 方程 $u_t=F(u)$

作用投影算子 $Pu_t = PF(u) = PF(P^{-1}\cdot Pu)$ 转换为有限维ode，需要确保 $P^{-1}$ 存在。

一般的 $P^{-1}$ 只能保证 Holder 连续, 达不到 ode 解存在唯一的 Lipschitz 连续，结果可能不唯一。

不过此方法与空间结构无关，仅依赖维数。可以考虑进一步的投影/截断 ...

## 吸引子
> 讨论方程上的吸引子

考虑自治方程
$$
\begin{cases}
   u(t) = F(u) \\\\
   u(0) = u_0 \in X,
\end{cases}
$$

其中 $X$ 是 Hausdorff 空间(任意两点可由邻域分离)；解算子 $S(t)$ 满足半群性质。

因为要刻画靠近/吸引的概念，从拓扑上表现为集合的包含、度量上表现为距离的接近，有两种定义，拓扑更本质更广泛；存在不可度量化的拓扑空间，因此从拓扑上考虑吸引子的定义。

### 定义(拓扑)

集合 $\mathscr{A}$ 称为 $B$-吸引子，对某类集 $B\subset 2^X$(满足某些性质，比如在度量意义下，为有界集), 满足

1. $\mathscr{A}$ 紧；
2. 吸引：$\forall B_1\in B, \exists t_0=t_0(\varepsilon, B_1)$, 使得 $t>t_0, S(t)B\subset \mathscr{A}(\varepsilon)$;
3. $\mathscr{A}$ 是满足 1 2 的最小集合.

当 $\mathscr{A}$ 是不变集，条件3满足；条件3 + 算子连续 => $\mathscr{A}$ 是不变集.

### 存在性定理

### 度量空间


---

> 作者: luoluo  
> URL: https://luoluokong10.github.io/notes/01/  

