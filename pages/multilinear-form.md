---
prerequisites:
  - module
---

# Multilinear form

:::definition[Multilinear form]
Let $(M_k,R,+_{M_k},\cdot_{M_k}), 1 \le k \le n$ and $(N,R,+_N,\cdot_N)$ be [modules](module) and let $f : \prod_{k=1}^n M_k \to N$, then $f$ is a _multilinear function_ if $f$ restricted to $M_k$ is a [module homomorphism]() for $1 \le k \le n$.

If $f$ is multilinear with $n = 2$ we say that $f$ is **bilinear**.

If $f$ is multilinear with $M_j = M_k$ for all $i \le j, k \le n$ we say that $f$ is a **multilinear form**.
:::

:::definition[Alternating]
Let $f : M^n \to N$ be a [multilinear form], then $f$ is **alternating** if it satisfies
$$
\forall x_1, \ldots, x_n \in M,\, \forall j \ne k \;
\allowbreak
\big( f(x_1, \ldots, x_j, \ldots, x_k, \ldots, x_n) =
- f(x_1, \ldots, x_k, \ldots, x_j, \ldots, x_n) \big).
$$
It follows that if $x_j = x_k$ for $j \ne k$ then $f(x_1, \ldots, x_j, \ldots, x_k, \ldots, x_n) = 0$.
:::

ref: https://en.wikipedia.org/wiki/Multilinear_form
