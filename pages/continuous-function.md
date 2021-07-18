---
prerequisites:
  - limit
  - topological-space
---

# Continuous function

The notion of a _continuous function_ exists in both Analysis and Topology. The topological definition should be understood as a generalization of the analytical one, motivated by the [theorem for equivalence of the definitions]().

:::definition[Continuous function (basic)]
A function $f: \mathbb{R} \to \mathbb{R}$ is continuous at $x_0 \in \mathbb{R}$ if
$$
\lim_{x\to x_0} f(x) = f(x_0).
$$

We say that $f$ is continuous function if $f$ is continuous at every point in its domain.
:::

:::definition[Continuous function (metric)]
:::

:::definition[Continuous function (topology)]
A [function]() $f:X\to Y$ between [topological space]() is continuous if $f^{-1}(A)$ is [open]() in $Y$ for all [open sets]() $A$ of $X$.

"A function is continuous if inverse images of open sets are open."
:::

:::theorem[Equivalence of definition of continuity]
If $X=Y=\mathbb{R}$ in the definition for [topological continuity]() then this definition is equivalent to [the standard definition in calculus](analytical continuity).

:::proof
[ref](https://proofwiki.org/wiki/Equivalence_of_Definitions_of_Continuity_on_Metric_Spaces)
:::
::::
