---
prerequisites:
  - ring
---

# Module

:::definition[Module]
A module $M$ is a [tuple]() $(A, R, +, \cdot)$ where

- $A$ is a [set]
- $R$ is a [ring]
- $+$ (_module addition_) is a [function]() $A\times A \to A$
- $\cdot$ (_scalar multiplication_) is [function]() $R \times A \to A$

such that

- $\forall x \in X \, (1_R \cdot x = x)$ (compatibility of identity)
- Scalar multiplication is [compatible](operation#compatibility) with ring multiplication
- $(A, +)$ is an [abelian](algebraic-structure#abelian) [group]()
- $\forall r \in R, x, y \in X \, \big(r \cdot (x + y) = r \cdot x + r \cdot y \big)$
- $\forall r, s \in R, x \in X \, \big((r +_R s) \cdot x = r \cdot x + s \cdot x \big)$

We say that $(A, R, +, \cdot)$ is a module _over_ the ring $R$.
:::

:::intuition
A module should be thought of as a ring action on an abelian group. Indeed, the first two requirements are inherited from [monoid](monoid#monoid-action) for the monoid $(R, \cdot_R)$, the third requirement confirms that the ring is acting on an abelian group and the last two requirements describe the compatibility of the operations of the ring $(R, +_R, \cdot_R)$ and the abelian group $(A, +)$.
:::

:::definition[Module Homomorphism]
Let $(M,R,+_M,\cdot_M)$ and $(N,R,+_N,\cdot_N)$ be modules and let $f : M \to N$, then $f$ is a _module homomorphism_ if $\forall x, y \in M, r \in R$:

- $f(x +_M y) = f(x) +_N f(y)$
- $f(r \cdot_M x) = r \cdot_N f(x)$

Module homomorphisms are often (in particular in linear algebra) called _linear functions_.
:::

:::definition[Free module]
A free module is ... Some nice examples highlighting the difference from vector spaces [here](https://kurser.math.su.se/pluginfile.php/14420/mod_resource/content/1/yishao-zhou-DifferenceModulesVS.pdf).
:::
