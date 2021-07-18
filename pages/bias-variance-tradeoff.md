# Bias–variance tradeoff

:::context
- $f: X \to \mathbb{R}$ is the underlying deterministic function that we want to model.
- $\hat{f}: X \to \mathbb{R}$ is our model of $f$.
- $y: X \to \mathbb{R}$ is the stochastic function that we can measure.
- $y(x) = f(x) + \varepsilon$ where $\varepsilon \sim$ $\mathcal{N}(0 ,\sigma^2)$ represents noise causing an irreducible error.
:::

:::theorem[Bias–variance tradeoff]
$$
{\displaystyle \operatorname {E} {\Big [}{\big (}y-{\hat {f}}(x){\big )}^{2}{\Big ]}={\Big (}\operatorname {Bias} {\big [}{\hat {f}}(x){\big ]}{\Big )}^{2}+\operatorname {Var} {\big [}{\hat {f}}(x){\big ]}+\sigma ^{2}}
$$

:::proof
[ref](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff#Derivation)
:::

:::intuition
The more complex the model $\hat{f}(x)$ is, the more data points it will capture, and the lower the bias will be. However, complexity will make the model "move" more to capture the data points, and hence its variance will be larger. [[ref](https://en.wikipedia.org/w/index.php?title=Bias%E2%80%93variance_tradeoff&oldid=930258148)]

Since all three terms are non-negative, this forms a lower bound on the expected error on unseen samples. [[ref](https://en.wikipedia.org/w/index.php?title=Bias%E2%80%93variance_tradeoff&oldid=930258148)]
:::
