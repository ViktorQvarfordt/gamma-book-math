---
prerequisites:
  - measurable-space
  - probability-space
  - pushforward-measure
  - measurable-function
  - inverse-image
---

# Random variable & Probability distribution

:::context
Let $(\Omega, \mathcal{A}, P)$ be a [probability space]().
:::

:::definition[Random variable (abstract)]
A random variable is a measurable function $X:\Omega \to E$ where $(E, \mathcal{B})$ is a [measurable space]().
:::

::::definition[Probability distribution (abstract)]
The probability distribution of $X$ is the pushforward measure $P_X = X_*(P) = P \circ X^{-1}$ such that $(E, \mathcal{B}, P_X)$ is a probability space.

:::intuition
Think of this as the probability measure $P$ pushed forward by the random variable $X$ from the event space $\mathcal{A}_1$ to $\mathcal{A}_2$.
:::
::::

::::definition[Random variable (real-valued)]
A real-valued random variable is a measurable function $X:\Omega\to \mathbb{R}$.

:::note[Measurability of $X$]
It is implicitly assumed that the $\sigma$-algebra of $\mathbb{R}$ is the Borel algebra $\mathcal{B}(\mathbb{R})$ of $\mathbb{R}$.

Thus, the fact that $X$ is measurable means that $\sigma(X) = \{ X^{-1}(E) : E \in \mathcal{A} \} \subseteq \mathcal{B}(\mathbb{R})$.
:::
::::

:::definition[Probability distribution (real-valued)]
The probability distribution of $X$ is the pushforward measure $P_X = X_*(P) = P\circ X^{-1}$ such that $(\mathbb{R}, \mathcal{B}(\mathbb{R}), P_X)$ is a probability space.
:::

There probability distribution is a measure

:::definition[Cumulative distribution function]
$$
F_X(x) = P(X \le x)
$$
:::

:::definition[Probability density function]
If $F_X$ is differentiable we can define

$$
P_X(x) = \frac{dF_X(x)}{dx}
$$

There is much more detail to all this. This is really the Radon-Nikodym derivative.
:::

:::intuition[Probability distribution]
Given a random variable $X : \Omega \to \mathbb{R}$ we can ask "What is the probability that the value of $X$ is $x$?". The answer is $P(X = x)$. Due to technical complications this can not necessarily be generalized to a function of $x$.

I.e., this can (but not necessarily) give rise to a probability distribution $P_X$ for $X$. However, it always gives rise to a cumulative distribution function.
:::

:::example[Illustrating why $P_X$ may not exist]
The cantor distribution is a common example. But a simpler example is as follows.

Let $P(X = x_0) = 1$, i.e., all probability mass is concentrated to one point $x_0$. Then, for $P_X$ to be a function it would have to be a such that $\int_{-\infty}^a P_X = 0$ for all $a < x_0$ and $\int_{-\infty}^a P_X = 1$ for all $a ≥ x_0$. No such function exists (only the Dirac delta "function").
:::

:::intuition
A random variable $X$ can be used to "push-forward" the measure $P$ on $\Omega$ to a measure $P_X$ on $\mathbb{R}$. The underlying probability space $\Omega$  is a technical device used to guarantee the existence of random variables, sometimes to construct them, and to define notions such as correlation and dependence or independence based on a joint distribution of two or more random variables on the same probability space. In practice, one often disposes of the space $\Omega$altogether and just puts a measure on $\mathbb{R}$ that assigns measure $1$ to the whole real line, i.e., one works with probability distributions instead of random variables.
:::

:::notation
Generically, a random variable will be denoted $X$, $Y$, $Z$, etc. The probability to observe $X = x$ is denoted $P_X(x)$, so if $x_1, \ldots, x_n$ are the possible values of $X$, then $\sum_i P_X(x_i) = 1$.

Similarly, if $X$, $Y$ are two random variables, the probability to observe $X = x$ and $Y = y$ is denoted $P_{X,Y}(x, y).$
:::

:::notation
$$
\begin{aligned}
[X = x] &= \{ \omega \in \Omega \mid X(\omega) = x \} = X^{-1}(\{x\}) \\
[X ⊂ A] &= \{ \omega \in \Omega \mid X(\omega) ⊂ A \} = X^{-1}(A)
\end{aligned}
$$

And therefore

$$
\begin{aligned}
P(X = x) &= P(\{ω ∈ Ω \mid X(ω) = x\}) = P(X^{-1}(\{x\})) \\
P(X ∈ A) &= P(\{ω ∈ Ω \mid X(ω) ∈ A\}) = P(X^{-1}(A))
\end{aligned}
$$
:::

:::note
In applications, the notions of random variable and probability distribution are used interchangeably when there is no risk for confusion. The probability distribution captures most relevant properties of a random variable.
:::

In the discrete case, we can get by without any measure theory. One typically defines discrete random variables without reference to the underlying sample space $\Omega$ or the corresponding $\sigma$-algebra $\mathcal{A}$.

:::definition[Discrete random variable]
$X$ is a discrete random variable if the range of $X$ is $\{x_i\}_{i=1}^n$ and $P(X=x_i) = p_i$.
:::

Note that there is no reference to $\Omega$ or $\mathcal{A}$. Indeed, different choices of $\Omega$ can describe $X$, as demonstrated by the examples below.

::::example[Construct $\Omega$ and $\mathcal{A}$ from a discrete random variable: Simple case]
Let $\Omega = \{\omega_i\}_{i=1}^n$ and $\mathcal{A} = \mathcal{P}(\Omega)$, such that $X(\omega_i) = x_i$, and $P(X = x_i) = P(\{\omega_i\}) = p_i$.

:::example[Explicit $n = 2$]
* $\Omega = \{\omega_1, \omega_2\}$
* $\mathcal{A} = \big\{\{\}, \{\omega_1\}, \{\omega_2\}, \{\omega_1, \omega_2\}\big\}$
* $X(\omega_1) = x_1, X(\omega_2) = x_2$
* $P(X = x_1) = P(\{\omega_1\}) = p_1$, and similarly for $x_2$
:::
::::

::::example[Construct $\Omega$ and $\mathcal{A}$ from a discrete random variable: Redundant case]
To produce more examples, we can assign $k$ elements in $\Omega$ for each $x_i$.

Let $\Omega = \{\omega_{ij}\}_{i=1,j=1}^{i=n,j=k}$ and let $\mathcal{A}$ be a subset of $\mathcal{P}(\Omega)$ such that if $\omega_{ij}$ is in an element of $\mathcal{A}$ then also $\omega_{ij'}$ is in that element, for all $j' = 1, \ldots, k$. This last constraint is to ensure that $P$ is defined on all elements of $\mathcal{A}$. Let $X(\omega_{ij}) = x_i$ for all $j = 1, \ldots, k$. Let $P(X = x_i) = P(\{\omega_{ij}\}_{j=1}^k) = p_i$.

The sample space contains a sort of redundancy for the discrete random variable $X$.

:::example[Explicit $n = k = 2$]
* $\Omega = \{ \omega_{11}, \omega_{12}, \omega_{21}, \omega_{22} \}$
* $\mathcal{A} = \big\{ \{\}, \{\omega_{11}, \omega_{12}\}, \{\omega_{21}, \omega_{22}\}, \{\omega_{11}, \omega_{12}, \omega_{21}, \omega_{22}\} \big\}$
* $X(\omega_{11}) = x_1, X(\omega_{12}) = x_1, X(\omega_{21}) = x_2, X(\omega_{22}) = x_2$
* $P(X=x_1) = P(\{\omega_{11}, \omega_{12}\}) = p_1$, and similarly for $x_2$
* $P(\{\omega_{11}, \omega_{21}\}) = \text{undef.}$ (this would correspond to that "part of outcome $x_1$ and $x_2$ occurred", which is not meaningful)
:::
::::


## References

* https://en.wikipedia.org/wiki/Random_variable
