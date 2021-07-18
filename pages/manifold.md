---
prerequisites:
  - topological-space
  - homeomorphism
---

# Manifold

:::intuition[Manifolds unify linear algebra and topology]
Vector spaces and topology are, in a sense, two extreme viewpoints of manifolds. A manifold is a space which locally looks like $ℝ^n$ (or $ℂ^n$) but not necessarily globally. As a first approximation, we may model a small part of a manifold by a Euclidean space $ℝ^n$ (or $ℂ^n$) (a small area around a point on a surface can be approximated by the tangent plane at that point); this is the viewpoint of a vector space. In topology, however, we study the manifold as a whole. We want to study the properties of manifolds and classify manifolds using some sort of ‘measures’. Topology usually comes with an adjective: algebraic topology, differential topology, combinatorial topology, general topology and so on. These adjectives refer to the measure we use when classifying manifolds.

--- M. Nakahara -- Geometry, Topology and Physics.
:::

:::definition[Topological manifold]
A topological manifold $M$ of dimension $n$ is a [topological space]() such that:
- $M$ is a [Hausdorff space]().
- $M$ is [second-countable]().
- $M$ is a [locally euclidean space]() of dimension $n$:
:::

:::definition[Hausdorff space]
A Hausdorff space $X$ is a [topological space]() such that:
- For every pair of distinct points $p, q \in X$, there are disjoint [open subset](open-set) $U, V \subseteq X$ such that $p \in U$ and $q \in V$.
:::

:::definition[Second-countable space]
A second-countable space is a [topological space]() $(X, \tau)$ such that:
<negative-space />
- There exists a countable basis for the topology $\tau$ on $X$.
:::

:::definition[Locally euclidean space]
A locally euclidean space $X$ of dimension $n$ is a [topological space]() such that:
<negative-space />
- Each point of $X$ has a [neighborhood]() that is [homeomorphic](homeomorphism) to an open subset $\mathbb{R}^n$.
:::
