---
prerequisites:
  - entropy
  - conditional-probability
---

# Conditional entropy

:::context
* Let $X$ and $Y$ be correlated discrete random variables with probability mass functions $P_X$ and $P_Y.$ Let $P_{XY}$ be the PMF of their joint distribution.
* Assume that we seek information about $X$ but we can only observe $Y$. E.g., communication over a noisy channel.
:::

:::definition[Conditional entropy]
$$
S_{X|Y} = S_{XY} - S_Y
$$
:::

:::intuition[Conditional entropy]
The conditional entropy $S_{X|Y}$ is the entropy that remains of $X$ after we have observed $Y$.
:::

:::definition[Entropy of a probability mass function]
$$
\begin{aligned}
S_X &= -\sum_i P_X(x_i) \log(P_X(x_i)) \\
S_{XY} & = -\sum_{i,j} P_{XY}(x_i,y_j) \log(P_{XY}(x_i,y_j))
\end{aligned}
$$
:::

:::definition[Entropy of]
$$
S_{X|Y=y_j} = - \sum_i P_{X|Y}(x_i|y_j) \log(P_{X|Y}(x_i|y_j))
$$
:::

:::definition[Mutual information]
The mutual information $I(X;Y)$ of $X$ and $Y$ is the information we learn about $X$ after observing $Y,$ given by
$$
I(X;Y) = S_X - S_{X|Y} = S_X + S_Y - S_{XY}.
$$
:::
