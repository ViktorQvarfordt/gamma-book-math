# Correlation

## Adding correlations

Let $X$ and $Y$ be random variables. The correlation between $X$ and $Y$ is
given by
$$
\rho_{X,Y} =
\text{corr}(X,Y) =
\frac{\text{cov}(X,Y)}{\sigma_X\sigma_Y} =
\frac{E[(X-\mu_X)(Y-\mu_Y)]}{\sigma_X\sigma_Y}.
$$

Assume that we have a number of samples of pairs $(X_i,Y_i)$, being independent
and identically distributed. Let $r_k$ for $k=1,\ldots,n$ be the sample
correlations of n (disjoint) subsets of samples. Let $r$ denote the correlation
for the union of the subsets of samples.

The combined correlation $r$ is *not* given by the average of the correlations
$\frac{1}{n}\sum_{k=1}^n r_k$. Adding correlations by themselves is meaningless.
However, $r$ is approximately given by transforming the correlations with the
[Fisher transformation](https://en.wikipedia.org/wiki/Fisher_transformation),
then adding the transformed values and finally taking the inverse transform. The
Fisher transformation is given by
$$
z = \text{arctanh}(r).
$$

That is, the combined correlation is given by
$$
r = \tanh\left(\frac{\sum_{k=1}^n\text{arctanh}(r_k)}{n}\right)≥
$$
This works because the Fisher transformation of a correlation is normally
distributed and it *is* meaningful to sum such values.

### References

- https://mathoverflow.net/questions/57908/combining-correlation-coefficientse
- https://en.wikipedia.org/wiki/Fisher_transformation
