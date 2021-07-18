# Operator

:::definition[Operator]
An operator is a function between vector spaces.
:::

:::definition[Linear operator]
A linear operator is an operator $A:X→Y$ such that
$$
A(αu+βv) = αAu+βAv.
$$
:::

:::notation[Omitting parenthesis]
We write $Au$ to denote $A(u)$.
:::

::::notation[Operators on functions]
:::context
Let $A:X→Y$ be an operator where $X, Y$ are function spaces. Let $f$ be a function in $X$.
:::
We write $(Af)(x)$ to denote that the operator $A$ operates on the function $f∈X$ and gives a function $Af∈Y$, which in turn is applied to an element $x$ from the domain of functions in $Y$.
::::

:::notation[Composition of operators]
$$
(ABf)(x) ≔ (A(Bf))(x)
$$
:::

:::definition[Equality of operators]
Let $A_1: X_1 → Y_1$ and $A_2: X_1 → Y_2$ be operators. The equation
$$
A_1 = A_2
$$
should be understood as
1. $X_1 = X_2$.
2. $A_1f = A_2f$ for all $f∈X_1$.
:::

:::definition[Bounded operator and operator norm]
A bounded operator is an operator $A:X→Y$ for which there exists a constant $C∈ℝ$ such that
$$
\lVert Ax \rVert ≤ C \lVert x \rVert \quad  ∀x∈X.
$$

The norm $\lVert A \rVert$ of $A$ is the infimum over all such constants $C$. If no such $C$ exists, we say that $A$ is unbounded.
:::

:::definition[Isometric operator]
An isometric (norm preserving) operator is an operator $A:X→Y$ such that
$$
\lVert Ax \rVert_Y = \lVert x \rVert_X \quad \forall x \in X.
$$
:::

:::definition[Unitary operator]
A unitary operator is an operator $A: X \to Y$ such that it is defined on the whole space $X$, is isometric and surjective. In particular this gives that $A$ is invertible and
$$
AA^* = A^*A = I.
$$
:::
