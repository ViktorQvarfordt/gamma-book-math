# Entropy

Aka. Shannon entropy

## Intuition

_Entropy_ is the average informational capacity of an _event_, measured in bits. By _event_ we mean a sample of a random variable, or equivalently, a letter in a message of a given alphabet.

We say "informational capacity" rather than "information" since the concept of information is usually associated with the concept of meaning. In this sense, entropy is the measure of information independent of whether any meaning has been assigned to the information.

Think of static noise in an analogue TV. It has high entropy but no meaningful information.

## Definition

The definition of entropy is formulated in terms of a discrete random variable.

:::context[Entropy -- Discrete random variable]
Let $X$ be a discrete random variable with values $x_1, \ldots, x_k$ and probability mass function $P(X = x_j) = p_j.$ By _event_ we refer to a random sample of $X$. Note that $\sum_{j=1}^k p_j = 1.$
:::

Or equivalently, in terms of text messages.

:::context[Entropy -- Message from alphabet]
Suppose a message is created from an alphabet of $k$ symbol $x_1, \ldots, x_k$ where the probability to observe $x_j$ is $p_j$. Let $X$ denote this probability distribution. By _event_ we refer to observing a letter in a given message. Note that $\sum_{j=1}^k p_j = 1.$
:::

:::definition[Entropy]
The entropy $S_X$ of $X$ (per event is)

$$
S_X = -\sum_{j=1}^k p_j \log p_j.
$$
:::

## Understanding the definition

:::theorem[Entropy is a measure of average informational capacity per event]
Consider a sequence of $N$ events of $X$. The outcome $x_j$ will occur approximately $p_j N$ times. The number of distinct ways the given sequence can occur is

$$
\frac{N!}{(p_1N)!\cdots(p_kN)!}.
$$

As $N \to \infty$, this expression approaches $2^{NS_X}$.

Thus, the number of bits of information that one can extract from a sequence of $N$ events is $NS_X.$ Thus, there is on average $S_X$ bits of information per event.
:::

:::proof
$$
\frac{N!}{(p_1N)!\cdots(p_kN)!} \approx \frac{N^N}{\prod_{j=1}^k (p_jN)^{p_jN}} = 2^{NS}
$$

where the approximation is given by Stirling's approximation and the equality can be expanded as follows

$$
\begin{aligned}
2^{NS}
&= \left(2^{-N \sum_j (p_j \log(p_j))}\right) \\
&= \left(2^{\sum_j (p_j \log(p_j))}\right)^{-N} \\
&= \left(\prod_j 2^{p_j \log(p_j)}\right)^{-N} \\
&= \left(\prod_j \left(2^{\log(p_j)}\right)^{p_j}\right)^{-N} \\
&= \left(\prod_j p_j^{p_j}\right)^{-N} \\
&= \left(\prod_j p_j^{p_j N}\right)^{-1} \\
&= \frac{\prod_j N^{(p_j N)}}{\prod_j (p_j N)^{p_j N}} \\
&= \frac{N^{\sum_j (p_j N)}}{\prod_j (p_j N)^{p_j N}} \\
&= \frac{N^{N \sum_j (p_j)}}{\prod_j (p_j N)^{p_j N}} \\
&= \frac{N^N}{\prod_j (p_j N)^{p_j N}}
\end{aligned}
$$
:::

:::definition[Information]
The information $I_X$ of $X$ per event is
$$
I_X = -\log(P(X)).
$$

Note that $I_X$ is a random variable, just like $X$, while $S_X$ is a real number.
:::

:::observation[Entropy is the average information per event]
$$
E[I_X] = E[-\log(P(X))] = -\sum_{j=1}^k p_j \log(p_j) = S_X
$$
:::
