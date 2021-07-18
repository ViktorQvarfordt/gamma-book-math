---
prerequisites:
  - category
---

# Functor

:::intuition
Every sufficiently good analogy is yearning to become a functor.
-- John Baez
:::

:::definition[Functor (abstract definition)]
A functor is a morphism in the category of categories.
:::

:::definition[Functor (basic definition)]
Let $\mathbf{C}$ and $\mathbf{D}$ be [categories](category).

A functor $F: \mathbf{C} \to \mathbf{D}$ consists of:

* A mapping of objects $X$ in $\mathbf{C}$ to objects $F(X)$ in $\mathbf{D}$, and
* A mapping of arrows $f: X \to Y$ in $\mathbf{C}$ to arrows $F(f): F(X) \to F(Y)$ in $\mathbf{D}$, such that:
  * F preserves identities: $F(\text{Id}_X) = \text{Id}_F(X)$
  * F preserves composition: $F(f \circ g) = F(f) \circ F(g)$.
:::
