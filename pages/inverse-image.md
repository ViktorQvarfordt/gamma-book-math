# Inverse image (preimage)

:::context
Let $f: X \to Y$ be a function.
:::

:::definition[Inverse image]
The inverse image $f^{-1}(A)$ of a set $A \subseteq X$ under a function $f$ is the set of all elements in $X$ that map to $A$, i.e.,

$$
f^{-1}(A) = \{ x \in X \mid f(x) \in A \}.
$$
:::

:::definition[Inverse image function]
The construct of inverse images gives rise to to the inverse image function $f^{-1}: \href{power-set}{\mathcal{P}}(Y) \to \mathcal{P}(X)$ of $f$. I.e., it maps subsets of $Y$ to subsets of $X$ by the preimage as defined above.
:::

:::remark
The inverse image function $f^{-1} : \mathcal{P}(Y) \to \mathcal{P}(X)$ is not to be confused with the inverse function $f^{-1} : Y \to X$.

The preimage of a singleton set $\{y\}$ is sometimes called the _fiber_ of $y$, or _level set_ when $Y = \mathbb{R}$.
:::
