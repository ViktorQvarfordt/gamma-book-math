# Measure

:::context
* Let $X$ be a [set]()
* Let $\mathcal{A}$ be a [$σ$-algebra](sigma-algebra) over $X$
:::

:::definition[Measure]
A function $μ$ from $\mathcal{A}$ to the extended real number line ($\mathbb{R}\cup\{\infty\}$) is called a measure if it satisfies the following properties:

* Non-negativity: $E \in \mathcal{A} \implies μ(E) ≥ 0$
* Null empty set: $\mu(\emptyset) = 0$
* Countable additivity (or $σ$-additivity): For all countable collections $\{E_{k}\}_{k=1}^{\infty}$ of pairwise disjoint sets in $\mathcal{A}$,

$$
\mu \left(\bigcup _{k=1}^{\infty }E_{k}\right)=\sum _{k=1}^{\infty }\mu (E_{k})
$$
:::
