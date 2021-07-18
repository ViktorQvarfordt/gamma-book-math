# Inverse element

:::definition[Inverse element]
Let $(A, *)$ be a [magma]() with identity element $e$. An element $a^{-1} \in A$ is an inverse of $a \in A$ if it satisfies both:

- $a^{-1} * a = e$; left inverse
- $a * a^{-1} = e$; right inverse
:::

:::proposition[Uniqueness of inverse]
Let $(A, *)$ be a monoid, let $a \in A$. If $a$ has an inverse $a^{-1}$, then it is unique.
:::

:::proof
Let $(A, *)$ be a monoid. Let $a \in A$. Assume that both $a^{-1}$ and $b^{-1}$ are inverse elements of $a$. Then,

- $e = a^{-1} * a$.

- $e = b^{-1} * a$.

- The above together with uniqueness of identity implies
  $$
  a^{-1} * a = b^{-1} * a
  $$

- Operating with $a^{-1}$ from right gives
  $$
  (a^{-1} * a) * a^{-1} = (b^{-1} * a) * a^{-1}
  $$

- By associativity
  $$
  (a^{-1} * a) * a^{-1} = (b^{-1} * a) * a^{-1} \implies a^{-1} * (a * a^{-1}) = b^{-1} * (a * a^{-1})
  $$

- By property of inverse
  $$
  a^{-1} * e = b^{-1} * e \implies a^{-1} = b^{-1}
  $$
:::

:::remark
The theorem does not hold if $*$ is not associative [[ref](https://proofwiki.org/wiki/Inverse_not_always_Unique_for_Non-Associative_Operation)].
:::
