# Topological space

:::definition[Topological space]
A topological space is a tuple$(X, \tau)$ where

* $X$ is a set
* $\tau$ is a topology on $X$
:::

:::definition[Topology on a set]
A topology $\tau$ on a set $X$ is a collection of subsets of $X$ such that:

* $\emptyset, X \in \tau$

* Closed under infinite unions
  $$
  \displaystyle \{x_k\}_k \subset \tau \implies \bigcup_k x_k \in \tau
  $$

* Closed under finite intersections
  $$
  x_1, x_2 \in \tau \implies x_1 \cap x_2 \in \tau
  $$
:::

:::definition[Open set]
A subset $A \subset X$ of a topological space $(X, \tau)$ is said to be

* _open_ if $A \in \tau$,
* _closed_ if $A^c \in \tau$.
:::

:::definition[Trivial topology]
The trivial topology of a set $X$ is $\{\emptyset,X\}$.
:::

:::definition[Discrete topology]
The discrete topology of a set $X$ is the [set of all subset](power-set) of $X$.
:::

[Standard topology]()
