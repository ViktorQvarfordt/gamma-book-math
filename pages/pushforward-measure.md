# Pushforward measure

:::intuition
A pushforward measure is obtained by "pushing forward" a measure from one measurable space to another using a measurable function.
:::

:::context
* Let $(X_1, \mathcal{A}_1)$ and $(X_2, \mathcal{A}_2)$ be measurable spaces.
* Let $f: X_1 \to X_2$ be a measurable function.
* Let $\mu$ be a measure on $\mathcal{A}_1$.
:::

::::definition[Pushforward measure]
The pushforward of $\mu$ (from $X_1$ to $X_2$ by $f$) is the measure $\mu \circ f^{-1}$ on $\mathcal{A}_2$.

:::details
A common notation is $f_*(\mu) = \mu \circ f^{-1}$. Spelled out, the pushforward measure is

$$
(f_*(\mu))(B) = \mu(f^{-1}(B)) \quad \forall \, B\in\mathcal{A}_2.
$$
:::
::::

:::theorem[Change of variable]
A measurable function $g$ on $X_2$ is integrable with respect to the pushforward measure $f_*(μ)$ if and only if the composition {$g\circ f$ is integrable with respect to the measure $μ$. In that case, the integrals coincide, i.e.,

$$
\int_{X_{2}} g \, d(f_{*}\mu) = \int_{X_{1}} g \circ f \, d\mu.
$$
:::
