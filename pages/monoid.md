---
prerequisites:
  - magma
  - operation
  - identity-element
---

# Monoid

:::definition[Monoid]
A monoid is a [magma]() $(A, *)$ such that:
* $*$ is [associative]()
* $*$ has [identity element]()
:::

:::definition[Monoid action]
Let $(A, *)$ be a monoid with [identity element]() $e$ and let $X$ be a [set](). A (left) monoid action of $(A, *)$ on $X$ is a [function]() $\star : A \times X \to X$ such that
- $\forall x \in X \, (e \star x = x)$; compatibility of identity.
- $*$ and $\star$ are [compatible operations](compatible-operations).
:::
