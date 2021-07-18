---
prerequisites:
  - operation
---

# Identity element

:::definition[Identity element]
An element $e\in A$ of a binary operation $*$ on $A$ is an identity element if:
- $\forall a \in A \,\big( e*a = a \big)$; left identity
- $\forall a \in A \,\big( a*e = a \big)$; right identity
:::

:::proposition[Uniqueness of identity]
If a binary operation $*$ has an identity element, then it is unique.
:::

:::proof
Assume that both $e$ and $f$ are identity elements of $*$. Then,
* $e * f = e$, because $e$ is a left identity.
* $e * f = f$, because $f$ is a right identity.
* Since the left hand sides of the above equations are equal, also the right hand sides must be equal, thus $e = f$.
:::
