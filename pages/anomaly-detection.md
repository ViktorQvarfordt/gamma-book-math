# Anomaly detection

:::context
- $f: X \to \mathbb{R}$ is the underlying deterministic function that we want to model.
- $\hat{f}: X \to \mathbb{R}$ is our model of $f$.
- $y: X \to \mathbb{R}$ is the stochastic function that we can measure.
- $y(x) = f(x) + \varepsilon$ where $\varepsilon \sim$ [$\mathcal{N}(0 ,\sigma^2)$](normal-distribution) represents noise causing an irreducible error.
:::

Let $(y_t)_t$ be a time series. The model $\hat{f}_{\le t}$ of $f$ has access to $y_k$ for all $k \le t.$

Let $e_t = y_t - \hat{f}_{\le t-1}(t)$ be the prediction error at timestep $t$. Then, we define the mean and variance of the prediction error during the last $n$ timesteps as:
$$
\begin{aligned}
\mu_{t,n} &= \frac{1}{n} \sum_{k = t - n}^t e_k \\
\sigma_{t,n}^2 &= \frac{1}{n-1}\sum_{k = t - n}^t (e_k - \mu_{t,n})^2
\end{aligned}
$$
Next, let $m \lt n$, then we define the *anomaly likelihood* as
$$
L_t = \Phi\left(\frac{\mu_{t,m} - \mu_{t,n}}{\sigma_{t,n}}\right)
$$
where $\Phi$ is the cumulative distribution function of the normal distribution.
In this way we have, for given threshold $\varepsilon > 0$, that
$$
P(\text{anomaly detected}_{t, \varepsilon}) \coloneqq L_t \ge 1 - \varepsilon.
$$
