# Generating GARCH time series with Python

The GARCH model is commonly employed in modeling financial time series. I show how to implement this model in python and generate data that have the properties of the stock market.

<!--toc-->


## Background

The [GARCH](https://en.wikipedia.org/wiki/Autoregressive_conditional_heteroskedasticity#GARCH) process was subject for the [Nobel Prize in Economics in 2003](https://www.nobelprize.org/nobel_prizes/economic-sciences/laureates/2003/press.html), rewarded to Robert F. Engle and Clive Granger, *"for methods of analyzing economic time series with time-varying volatility (ARCH)"*. In fact, GARCH is a generalized version of ARCH.


### Definition

The GARCH(p, q) model is defined by
\begin{align*}
  y_k &= \sigma_k \varepsilon_k \\
  \sigma_k^2 &= \omega + \sum_{i=1}^p \alpha_i y_{k-i}^2 + \sum_{j=1}^q \beta_j \sigma_{k-j}^2
\end{align*}
where $\omega > 0$, $\alpha_i \ge 0$, $\beta_j \ge 0$ and $\varepsilon_i$ are IID. See [Lecture notes: Financial time series, ARCH and GARCH models](http://stats.lse.ac.uk/fryzlewicz/lec_notes/garch.pdf) for more details.


**Remark:** Sometimes the definition is written as
\[ y_k = x_k \theta + \sigma_k \varepsilon_k \]
where $(x_k)$ is some input time series, used as a baseline for the generated data, where $\theta$ is a parameter deciding "how much" to re-use the information from $(x_k)$ time series in the resulting $(y_k)$ time series.


## Implementing the GARCH model

There are many theoretical sources on the web discussing the GARCH process. Code examples are less common, which is why I share some code here.


### Python code

```python
import numpy as np
import matplotlib.pyplot as plt


def garch(ω, α, β, n_out=1000):
    p = len(α)
    q = len(β)

    # Since the first max(p, q) number of points are not generated from the garch
    # process, the first points are garbage (possibly extending beyond max(p, q)),
    # so we drop n_pre > max(p, q) number of points.
    n_pre = 1000
    n = n_pre + n_out

    # Sample noise
    ɛ = np.random.normal(0, 1, n)

    y = np.zeros(n)
    σ = np.zeros(n)

    # Pre-populate first max(p, q) values, because they are needed in the iteration.
    for k in range(np.max([p, q])):
        σ[k] = np.random.normal(0, 1)
        y[k] = σ[k] * ɛ[k]

    # Run the garch process, notation from
    # http://stats.lse.ac.uk/fryzlewicz/lec_notes/garch.pdf
    for k in range(np.max([p, q]), n):
        α_term = sum([α[i] * y[k-i]**2 for i in range(p)])
        β_term = sum([β[i] * σ[k-i]**2 for i in range(q)])
        σ[k] = np.sqrt(ω + α_term + β_term)
        y[k] = σ[k] * ɛ[k]

    return y[n_pre:]


# Make a cumulative series from a "delta series".
def delta_to_cum(ys):
    ys_cum = []
    y_cum = 0
    for y in ys:
        y_cum += y
        ys_cum.append(y_cum)
    return ys_cum


# Define a garch(1,1) process
ω = 0.1
α = [0.3]
β = [0.2]
y = garch(ω, α, β)
x = range(len(y))

# The resulting series looks like stock returns and
# the cumulative series looks like stock prices.
plt.subplot(1,2,1)
plt.plot(x, y)
plt.title('Returns')
plt.subplot(1,2,2)
plt.plot(x, delta_to_cum(y))
plt.title('Prices')
plt.show()
```


### Fitting data to a GARCH model

The python package [arch](https://pypi.python.org/pypi/arch) can be used to fit a GARCH model to existing data.
