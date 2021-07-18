---
prerequisites:
  - set
---

# Cartesian product

:::definition[Cartesian product]
The _cartesian product_ of two sets $A$ and $B$ is the set of all pairs $(a, b)$ for all combinations of $a \in A$ and $b \in B$.

In [set builder notation]() we write this as:

$$
A × B \coloneqq \{(a,b) : a \in A, b \in B\}.
$$

:::definition[Cartesian product ($n$-fold)]
Let $A$ be a set. The $n$-fold cartesian product $A^n$ of $A$ is the cartesian product of $n$ copies of $A$. That is,

$$
A^n = A \times A \times \cdots \times A \quad\text{($n$ copies)}.
$$

The elements of $A^n$ are on the form $(a_1, a_2, \ldots, a_n)$.

:::remark
Note that elements of $A\times A\times A$ are on the form $(a_1, a_2, a_3)$ while elements of $(A\times A)\times A$ are on the form $((a_1, a_2), a_3)$. That is, formally speaking, $A\times A\times A \ne (A\times A)\times A$, meaning that that the cartesian product is not associative. However, there is a natural isomorphism $A\times A\times A \cong (A\times A)\times A$. Therefore, this distinction is typically not made in practice.
:::

:::example
Let $A = \{a, b\}$ and $B = \{1, 2, 3\}$, then

$$
\begin{aligned}
A \times B =
\big\{ & (a, 1), (a, 2), (a, 3), \\
& (b, 1), (b, 2), (b, 3) \big\},

\\[0.5em]

B \times A =
\big\{ & (1, a), (1, b), \\
& (2, a), (2, b), \\
& (3, a), (3, b) \big\}.
\end{aligned}
$$
:::
