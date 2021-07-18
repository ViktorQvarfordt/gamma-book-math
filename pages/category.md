# Category

:::definition[Category]
A category $C$ is a pair $(\text{Obj}, \text{Arr})$ where

* $\text{Obj}$ is a class of _objects_.
* $\text{Arr}$ is a class of _arrows_ (aka. $\text{Mor}$; _morphisms_) between objects, such that;
  * Each object $X$ has an _identity arrow_ $\text{Id}_X: X \to X$.
  * Arrows can be _composed_. I.e., there is an associative binary operation $\circ$ on arrows, such that if $f, g \in \text{Arr}$ then $g \circ f \in \text{Arr}$.
:::

:::example[Category of three objects]
Consider the category such that:
- $\text{Obj} = \{ X, Y, Z \}$
- $\text{Mor} = \{ \text{Id}_X, \text{Id}_Y, \text{Id}_Z, f, g, g\circ f \}$
Note that the identity morphisms are required by definition, they are typically omitted in images like the one below. The composite arrow $g\circ f$ is required to exist since $f$ and $g$ exists.

<img height=200 src='https://upload.wikimedia.org/wikipedia/commons/e/ef/Commutative_diagram_for_morphism.svg' />
:::
