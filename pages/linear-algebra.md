# Linear algebra

Linear algebra can be thought of as a subarea of abstract algebra, dealing with vector spaces, primarily the real vector space $\mathbb{R}^n$.

TODO: To be structured:

:::definition[Inner product]
The inner product generalizes the scalar product.
:::

TODO: https://www.math.usm.edu/perry/old_classes/mat681sp14/norm_and_metric.pdf

:::definition[Linear combination]
A linear combination of the vectors $v_1, \ldots, v_n \in V$ is an expression on the form
$$
\sum_{k=1}^n a_k v_k
$$
where $a_k \in \text{field}(V)$.
:::

:::definition[Linear dependence]
The vectors $v_1, \ldots, v_n$ are said to be linearly dependent if
$$
\sum_{k=1}^n a_k v_k = 0
$$
for scalars $a_k$, not all zero.
:::

:::intuition
Equivalent to that one of the vectors is a linear combination of the others.
:::

:::definition[Span]
Let $v_1, \ldots, v_n$ be vectors of a vector space $V$. The span of the vectors is the set of all linear combinations of the vectors,
$$
\text{span}\{v_1, \ldots, v_n\} = \left\{\sum_{k=1}^n a_k v_k : a_k \in \text{field}(V)\right\}.
$$
If $\text{span}\{v_1, \ldots, v_n\} = V$ we say that the vectors span $V$ or that the vectors form a spanning set.
:::

:::definition[Basis]
A set of vectors $\{v_1, \ldots, v_n\}$ of a vector space $V$ is a basis for $V$ if the vectors are linearly independent and $\text{span}\{v_1, \ldots, v_n\} =  V$.
:::

:::definition[Linear map]
A linear map is a module homomorphism between two vector spaces.
:::


## Change of basis

Let $\alpha = \{\alpha_j\}_{j=1}^n$ and $\beta = \{\beta_j\}_{j=1}^n$ be two bases for $V$ with coordinate maps
$$
\begin{aligned}
\varphi_1 &: \mathbb{R}^n \to V; \; e_j \mapsto \alpha_j \\
\varphi_2 &: \mathbb{R}^n \to V; \; e_j \mapsto \beta_j
\end{aligned}
$$
where $\{e_j\}_{j=1}^n$ is the standard basis for $\mathbb{R}^n$.

### Change of basis for vectors

A vector $\xi \in V$ has coordinates $\varphi_1^{-1}(\xi)$ in basis $\alpha$ and $\varphi_2^{-1}(\xi)$ in basis $\beta$. Thus we have
$$
\begin{aligned}
\varphi_2^{-1}(\xi) = (\varphi_2^{-1} \varphi_1) \varphi_1^{-1}(\xi).
\end{aligned}
$$
From this, define the **change of basis matrix**
$$
\begin{aligned}
P^{-1} = \varphi_2^{-1} \varphi_1,
\end{aligned}
$$
i.e. the matrix that takes a vector in $\alpha$-coordinates and gives the $\beta$-coordinate representation.
The matrix $P = \varphi_1^{-1} \varphi_2$ is easily computed by the following observation,
$$
\begin{aligned}
P(e_j) = \varphi_1^{-1} \varphi_2 (e_j) = \varphi_1^{-1} (\beta_j),
\end{aligned}
$$
i.e. the $j$th column of $P$ is the coordinates for the new basis vector $\beta_j$ in the old basis $\alpha$.


## Change of basis for matrices

Let $T : V \to V$ be a linear transformation from $V$ to itself (i.e. $T$ is an endomorphism).
The matrix representation for $T$ in the two coordinates are
$$
\begin{aligned}
&T_\alpha = \varphi_1^{-1} T \varphi_1, \\
&T_\beta  = \varphi_2^{-1} T \varphi_2.
\end{aligned}
$$
With $P^{-1}$ as above, we have
$$
\begin{aligned}
T_\beta = P^{-1} T_\alpha P.
\end{aligned}
$$


## Remark

The similarity transform $SAS^{-1}$ can be viewed as follows: You give it a coordinate vector in terms of the basis $\beta$ made up of the columns of $S^{-1} = P$. Then $S^{-1}$ translates this into the standard basis; then you apply $A$ as usual; then you apply $S$ and translate it back into the basis $\beta$. So you can view $SAS^{-1}$ as performing $A$, but in terms of the basis $\beta$.
