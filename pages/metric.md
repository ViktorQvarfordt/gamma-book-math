---
prerequisites:
  - function
  - sequence
---

# Metric

:::definition[Metric]
A _metric_ (aka _distance function_) on a set $X$ is a [symmetric function]() $d: X \times X \to \mathbb{R}$ such that for all $x, y, z \in X$ the following holds:

- $d(x, y) = 0 \iff x = y$ (identity of indiscernibles)
- $d(x, y) + d(y, z) \ge d(x, z)$ (triangle inequality or subadditivity)
:::

:::definition[Metric space]
A _metric [space]()_ is a [set]() equipped with a metric. We write $(X, d_X)$ for a metric space with underlying set $X$ and metric $d_X$.
:::

:::example[Standard metric]
The real numbers $\mathbb{R}$ equipped with the metric $d(x, y) = |x - y|$ is a metric space.
:::


:::definition[Limit of sequence]
The limit $L$ of a sequence $(a_n)_n$ in a metric space with metric $d$ is such that
$$
\forall \epsilon > 0 \; \exists N \in \mathbb{N} : n > N \implies d(x_n, L) \lt \epsilon.
$$

If a sequence has a limit, the sequence is said to be _convergent_, otherwise _divergent_.

The limit $L$ can be either in the metric space or not.
:::


:::definition[Completeness]
A metric space is _complete_ if all Cauchy sequences converge to an element in the space.
:::


:::definition[Cauchy sequence]
Let $(X, d)$ be a metric space. A _Cauchy sequence_ in $X$ is a sequence $(x_n)_\mathbb{N}$ such that
$$
\forall \epsilon > 0 \; \exists N \in \mathbb{N} : n, m > N \implies d(x_n, x_m) \lt \epsilon.
$$
:::


:::theorem[Cauchy convergence criterion]
A sequence $(a_n)_n$ is convergent iff it is a Cauchy sequence.
:::


:::definition[Limit of function]
Let $(X, d_X)$ and $(Y, d_Y)$ be metric spaces. Let $f: X \to Y$ be a function. The _limit_ $L$ of $f$ as $x$ approaches $c$ is denoted by
$$
\lim_{x \to c} f(x) = L.
$$
The limit satisfies
$$
\begin{gathered}
\forall \epsilon \gt 0 \; \exists \delta \gt 0 : \forall x \in X : \\
d_X(x, c) \lt \delta \implies d_Y(f(x), L) \lt \epsilon.
\end{gathered}
$$
:::

:::remark
The definition of a limit of a sequence is recovered from the definition of a limit of a function by choosing $X = \mathbb{N}$ and $c = \infty$.
:::

:::definition[Continuous function]
A function $f: X \to Y$ is continuous at a point $c$ if
$$
\lim_{x\to c} f(x) = f(c).
$$
A function is said to be _continuous_ if it is continuous at every point in the domain.
:::
