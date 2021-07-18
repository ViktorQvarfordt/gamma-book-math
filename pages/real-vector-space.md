---
prerequisites:
  - cartesian-product
---

# Real vector space

::::definition[Real vector space]
The _real vector space_ of dimension $n$ is the triple $(\mathbb{R}^n, +, \cdot)$, where

- $ℝ^n$ is the $n$-fold cartesian product of $\mathbb{R}$.
- $+$ is vector addition.
- $\cdot$ is scalar multiplication.

A vector $x \in \mathbb{R}^n$ is written $x = (x_1, x_2, \ldots, x_n)$ where $x_j \in \mathbb{R}$.

:::definition[Vector addition]
Vector addition is given by component-wise addition; if $x, y \in ℝ^n$ then

$$
\begin{aligned}
x + y &= (x_1, x_2, \ldots, x_n) + (y_1, y_2, \ldots, y_n) \\
      &= (x_1 + y_1, x_2 + y_2, \ldots, x_n + y_n).
\end{aligned}
$$
:::

:::definition[Scalar multiplication]
Scalar multiplication of $k \in \mathbb{R}$ with $x \in \mathbb{R}$ is given by

$$
\begin{aligned}
kx &= k(x_1, x_2, \ldots, x_n) \\
   &= (kx_1, kx_2, \ldots, kx_n).
\end{aligned}
$$
:::
::::

:::exercise
Verify that the this is a vector space according to the abstract definition.
:::

:::definition[Scalar product]
Let $x, y \in \mathbb{R}^n$, the _scalar product_ $x\cdot y$ of $x$ and $y$ is
$$
x \cdot y = \sum_{k=1}^n x_k y_k.
$$
:::


::::lemma[Scalar product and geometry]
Let $u, v \in \mathbb{R}^n$ and let $\theta$ be the angle between $u$ and $v$, then
$$
u \cdot v = |u| |v| \cos \theta.
$$


:::proof
Using the [law of cosines]() and then expanding resulting expression proves the theorem.
$$
\begin{aligned}
|u - v|^2 &= |u|^2 + |v|^2 + 2|u||v|\cos \theta \\
\iff |u||v|\cos \theta &= \frac{1}{2}\left(|u|^2 + |v|^2 - |u - v|^2 \right) \\
&= \frac{1}{2}\left( \sum u_k^2 + v_k^2 - (u_k - v_k)^2 \right) \\
&= \frac{1}{2}\left( \sum u_k^2 + v_k^2 - u_k^2 - v_k^2 + 2u_kv_k \right) \\
&= \sum u_kv_k \\
&= u \cdot v
\end{aligned}
$$
:::

Note that this result depends on the [law of cosines], i.e. requiring that the space has a corresponding Euclidean geometry in which notions of distances and angles are defined. However, in the general setting of a vector space with an inner product, this result can be used to _define_ the notion of angles.

:::remark
In this sense an inner product defines a geometry of a vector space, endowing it with the notion of distances and angles by defining, for vectors $u$ and $v$:
$$
\begin{aligned}
\text{norm:} && |u| &= \sqrt{\langle u, u \rangle} \\
\text{distance:} && d(u, v) &= |u - v| \\
\text{angle:} && \angle(u, v) &= \arccos\left( \frac{\langle u, v \rangle}{|u| |v|} \right)
\end{aligned}
$$
:::
::::


## Example: Implementation of $ℝ^3$ in Julia

```julia
import Base.+
import Base.*

Scalar = Number

# Define a type to represent 3-dimensional vectors
struct Vec3d
    x::Scalar
    y::Scalar
    z::Scalar
end

# Define vector addition
function +(u::Vec3d, v::Vec3d)::Vec3d
    return Vec3d(u.x + v.x, u.y + v.y, u.z + v.z)
end

# Define scalar multiplication
function *(k::Scalar, v::Vec3d)
    return Vec3d(k * v.x, k * v.y, k * v.z)
end

u = Vec3d(1, 2, 3)
v = Vec3d(1, 1, 1)

k = 5

println("test of vector addition: ", u + v)
println("test of scalar multiplication: ", k * u)

# test of vector addition: Vec3d(2, 3, 4)
# test of scalar multiplication: Vec3d(5, 10, 15)
```
