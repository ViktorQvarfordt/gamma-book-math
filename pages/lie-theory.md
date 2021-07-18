# Lie theory

:::intuition
TODO
:::

:::context
- $A$ is a set.
- $+$ is a [closed](operation#closure) [binary operation on](??#definition-binary-operation-on-a-set) $A$ with [identity element](#identity-element) $0$.
- $\times$ is a closed binary operation on $A$.
:::

:::definition[Jacobi identity]
The *Jacobi identity* is the property of $\times$ such that
$$
\forall a, b, c \in A \,\big( a \times (b \times c) + b \times (c \times a) + c \times (a \times b) = 0\big).
$$

:::remark
This can be seen as a weaker form of associativity, since if $\times$ is associative then the Jacobi identity holds, but not the other way around.
:::

:::definition[Lie algebra]
A *Lie algebra* is a [vector space]() $\mathfrak {g}$ equipped with an [alternating]() [bilinear]() [function]() $\mathfrak {g}\times \mathfrak {g} \to \mathfrak {g}; (x,y) \mapsto [x,y]$ called the Lie bracket that satisfies the [Jacobi identity]().
:::

:::definition[Lie group]
A *Lie group* is a group $(G, m, i)$ such that $G$ is a [smooth manifold]() and group multiplication $m$ and group inversion $i$ are [smooth functions](smooth function).
:::
