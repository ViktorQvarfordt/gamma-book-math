# R²: Coefficient of determination

:::context
- $y = (y_i)_i$ is a sequence of observations.
- $\widehat{y} =(\widehat{y}_i)_i$ is the corresponding sequence of predicted values.
- $\overline{y}$ is the mean of the observations.
:::

:::definition[R²: Coefficient of determination]
$$
\begin{aligned}
R^2
&= 1 - \frac{\sum_i (y_i - \widehat{y}_i)^2}{\sum_i (y_i - \overline{y})^2} \\[1em]
&= 1 - \frac{\text{squared observation deviation}}{\text{squared mean deviation}}
\end{aligned}
$$
:::

:::intuition
$R^2$ is the proportion of the variance in the dependent variable that is predictable from the independent variable(s).
:::
