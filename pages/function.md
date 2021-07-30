---
prerequisites:
  - relation
---

# Function

:::intuition[Informal notion of functions]
A function $f(x)$ is a rule that gives some output $y = f(x)$ for each input $x$.
:::

:::definition[Function (as a relation)]
A function $f: X \to Y$ is a [binary relation]() $\mapsto$ on $X \times Y$ that is [right-unique]() and [left-total](). We write $f(x) = y$ to denote $x \mapsto y.$ The set $X$ is the _domain_ and $Y$ is the _codomain_.
:::

:::remark
Note that the notation $f:X\to Y$ is shorthand for saying that $(X\times Y, f)$ is a relation that is right-unique and left-total. We use the notation:

* $\operatorname{dom}(f) \coloneqq X$
* $\operatorname{codom}(f) \coloneqq Y$
* If $X' \subseteq X$ then $f(X') = \{f(x) : x \in X'\}$.
* If $X = X_1 \times X_2$ and $x = (x_1, x_2) \in X$ then $f(x_1, x_2) = f(x)$ (multivariate function).
:::

Since functions are merely a special class of relations, the concept of [injective](left-unique) and [surjective](right-total) function is directly inherited from the corresponding definitions for relations.

:::observation[Equality of functions]
As a consequence of equality of [relations](relation) we have that two functions $f_1: X_1 \to Y_1$ and $f_2: X_2 \to Y_2$ are considered equal if $X_1 = X_2$, $Y_1 = Y_2$ and $f_1(x) = f_2(x)$ for all $x \in X_1 = X_2$.
:::

:::definition[Restricted function]
Let $f : A \to B$ and let $A' \subseteq A$, then $f$ restricted to $A'$ is the function $f|_{A'} : A' \to B; a \mapsto f(a)$.
:::

:::remark[Wider notion of functions]
A function is sometimes called a _map_ (often with additional structure). More generally a function can be seen as a _morphism_, the name being motivated by the fact that a function “changes the shape” (morphs) its domain. The notion of morphisms is explored further in [abstract algebra]() and generalized in [category theory]().
:::

::::intuition
A function is a thing that produces an output when given an input. For any given function and input the output is always the same. Note that one makes a distinction between a function and a functional expression: Let $f: \mathbb{R} \to \mathbb{R}$ and $g: \mathbb{Z} \to \mathbb{R}$ be functions with the functional expression $x \mapsto 2x + 1$, the functions $f$ and $g$ are formally different functions. However, $f$ restricted to $\mathbb{Z}$ is equal to g, written $f|_{\mathbb{Z}} = g$.

:::example
Let $f(x) = x^2 + 1$ be a function on $ℝ$ (meaning $f : ℝ \to ℝ$). Then $f(3) = 10$.
:::
::::

:::definition[Bijective function (Bijection)]
A function is bijective if it is injective and surjective. Also known as 'one-to-one'.
:::

:::definition[Symmetric function]
A function $f: X\times X \to Y$ is symmetric if

$$
f(x_1, x_2) = f(x_2, x_1) \quad \forall \, x_1, x_2 \in X.
$$

More generally, a function $f: X^n \to Y$ is symmetric if

$$
f\big(\sigma(x)\big) = f(x) \quad \forall \, x \in X^n,
$$

for all permutations $\sigma(x)$ of $x = (x_1, x_2, \ldots, x_n)$.
:::

:::definition[Inverse function]
A function $f: X \to Y$ has an inverse if and only if the [converse relation]() is a function. In this case, the converse relation is the inverse function $f^{-1}: Y \to X$.

Equivalently, a function $f$ has an inverse iff $f$ is bijective.
:::

:::observation[Cardinality of set of functions]
The number of functions from $X$ to $Y$ is $|Y|^{|X|}$ when $X$ and $Y$ are finite sets.
:::

:::proof
Each $x \in X$ can be mapped to $|Y|$ different elements Thus we have $|Y|\cdot|Y|\cdots|Y|$ possible functions, where the product contains $|X|$ factors, one for each element of $X$.
:::

:::definition[Set of functions]
The set of all functions from $X$ to $Y$ is denoted $Y^X$. The notation is motivated by the fact that the number of functions from $X$ to $Y$ is $|Y|^{|X|}$ when $X$ and $Y$ are finite sets.
:::
