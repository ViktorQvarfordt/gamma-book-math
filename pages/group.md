---
prerequisites:
  - algebraic-structure
  - monoid
  - operation
  - inverse-element
---

# Group

:::definition[Group]
A group  is a [monoid]() $(G, *)$ such that each element of $G$ has an [inverse element]() under $*$, denoted $-x$ (_additive notation_) or $x^{-1}$ (_multiplicative notation_).

An alternative notation for a group $(G, *)$ is $(G, m, i)$ where $m$ is the _multiplication function_ and $i$ is the _inverse element function_, given by:

- $m : G \times G \to G; \; (x, y) \mapsto x * y$
- $i : G \to G; \; x \mapsto x^{-1}$
:::

:::definition[Anticommutative]
Let $(G, *)$ be a group, then $*$ is anticommutative if
$$
\forall x, y \in G \, \big( x * y = - (y * x) \big).
$$
:::

:::definition[Group action]
A group action is a monoid action of a group. (This makes sense because a group is a monoid.)
:::
