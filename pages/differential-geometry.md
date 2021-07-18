# Differential geometry

:::intuition[Local linear approximation]
:::

::::intuition[Manifolds without ambient space]
The vector space $ℝ^n$ can be viewed in two ways:

- _Space:_ Elements of $ℝ^n$ are seen as as points in space, whose only property is location, expressed by the coordinates $(x_1, \ldots, x_n)$.
- _Directions:_ Elements of $ℝ^n$ are seen as vectors, which are objects that have direction and magnitude, but whose location is irrelevant.

Based on this idea we introduce the following definition.

:::definition
Let $a ∈ ℝ^n$, the geometric tangent space to $ℝ^n$ at $a$ is $ℝ^n_a = \{a\} \times ℝ^n$. We write $v_a$ or $v|_a$ to denote a vector in $ℝ^n_a$.
:::

In this way $ℝ^n_a$ and $ℝ^n_b$ are distinct. Think of $ℝ^n_a$ as the vector space $ℝ^n$ with origin at $a$.

<img src="https://math.viktorqvarfordt.com/imgs/tangent-space-to-sphere.png" style="width: 175px; float: right;" />

Consider a manifold embedded in an ambient space, for example $𝕊^2 \subset ℝ^3$. The tangent space to $𝕊^2$ at a point $a$ is then simply the subspace of $ℝ^3_a$ that is orthogonal to the line containing $0$ and $a$.

In fact, we can define the tangent space in this way for any manifold that we can embed into $ℝ^n$, and due to [Whitney embedding theorem](https://en.wikipedia.org/wiki/Whitney_embedding_theorem) this is always possible. However, working only with submanifolds of $ℝ^n$ will not be satisfying. The modern approach is to deal with manifolds in an _intrinsic_ manner, without reference to any ambient space. It turns out that the construction of tangent spaces in this context, when there is no ambient space to refer to, is much more involved and farther from the intuitive picture. When talking about intrinsic properties of a manifold we only have the concepts of smooth functions on the manifold and smooth coordinate charts.
::::
