---
prerequisites:
  - continuous-function
  - limit
---

# Derivative

:::definition[Derivative]
The _derivative_ at $x$ of a function $f: \mathbb{R} \to \mathbb{R}$ is
$$
f'(c) = \lim_{h\to 0} \frac{f(x+h)-f(x)}{h}.
$$
If this limit exists, the function is said to be _differentiable_ at $c$.

A function is said to be _differentiable_ if it is differentiable at every point in the domain, in this case the derivative $f'$ of $f$ is viewed as a function.

Repeatedly differentiating a function $k$ times gives rise to the $k$th derivative, denoted $f^{(k)}$, if it exists.
:::

:::definition[Continuously differentiable]
A function $f: \mathbb{R} \to \mathbb{R}$ is _continuously differentiable_ if its derivative is a continuous function.

The set of $k$ times continuously differentiable functions is denoted $C^k(\mathbb{R})$.
:::
