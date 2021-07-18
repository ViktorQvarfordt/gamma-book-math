# Operation

:::definition[Binary operation]
A binary operation on a [set]() $A$ is a [function]() $*: A \times A \to B$ where $A \subseteq B$.

We use the infix notation $a*b$ to denote $*(a,b)$.
:::

# Properties of binary operations

:::definition[Associative]
A binary operation $*$ on a set $A$ is associative iff
$$
\forall a, b, c \in A :\, a*(b*c) = (a*b)*c.
$$
:::

:::definition[Commutative (Abelian)]
A binary operation $*$ on a set $A$ is commutative iff
$$
\forall a, b \in A :\, a*b = b*a.
$$
:::

:::definition[Closure]
Let $*$ be a binary operation on $A$.
<negative-space />
- We say that $*$ is <em>closed</em> if $*(A) \subseteq A$.
- Let $A' \subseteq A$. We say that $A'$ has <em>closure</em> under $*$, or that $*$ is <em>closed</em> on $A'$, if $*(A') \subseteq A'$.

<intuition>
Subtraction (as a binary operation) on $\mathbb{Z}^+$ is not closed because there exists $a, b \in \mathbb{Z}^+$ such that $a - b \not\in \mathbb{Z}^+$ (for example $a = 0, b = 1$).

Addition (as a binary operation) on $\mathbb{Z}^+$ is closed.
</intuition>
:::

:::definition[Distributivity]
Let $*$ and $\star$ be two binary operations on a set $A$, we say that $*$ is distributive over $\star$ if:
<negative-space />
- $\forall a, b, c \in A \, \big(a * (b \star c) = (a * b) \star (a * c)\big)$ (left distributive)
- $\forall a, b, c \in A \, \big((b \star c) * a = (b * a) \star (c * a)\big)$ (right distributive)
:::

:::definition[Compatibility]
Let $*$ and $\star$ be two binary operations on a set $A$, we say that $*$ and $\star$ are compatible if
$$
\forall a, b, c \in A \, \big(a * (b \star c) = (a * b) \star c\big).
$$
:::

# Generalization

:::definition[Operation]
An operation $\omega$ is a function of the form $\omega : X \to Y$, where $V
\subset X_1 \times \cdots \times X_k$. The sets $X_k$ are called the domains of the operation, the set $Y$ is called the codomain of the operation, and the fixed non-negative integer $k$ (the number of arguments) is called the type or arity of the operation. Thus a unary operation has arity one, and a binary operation has arity two. An operation of arity zero, called a nullary operation, is simply an element of the codomain $Y$. An operation of arity $k$ is called a $k$-ary operation. <ref href="https://en.wikipedia.org/w/index.php?title=Operation_(mathematics)&oldid=930151180">
:::
