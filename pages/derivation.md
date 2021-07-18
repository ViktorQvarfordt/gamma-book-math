---
prerequisites:
  - manifold
---

# Derivation

:::definition[Derivation on manifold]
A function $v_p: C^\infty(M) \to ℝ$ is called a *derivation* at $p \in M$ if it is linear and satisfies the *Leibniz rule*
$$
v_p(fg) = v_p(f)g(p) + f(p)v_p(g)
$$
for all $f, g \in C^\infty(M)$.
:::

:::definition[Differential]
Let $F: M \to N$ be a smooth function between smooth manifolds $M$ and $N$. The *differential* of $F$ at $p \in M$ is a function
$$dF_p : T_pM \to T_{F(p)}N$$
such that
$$dF_p(v)(f) = v(f \circ F)$$
:::
