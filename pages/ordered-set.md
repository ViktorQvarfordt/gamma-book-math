---
prerequisites:
  - set
  - relation
---

# Ordered set

When we constructed relations we took a set (or a pair of sets) and _added some structure_ to the set, in the form of a relation on the set. This is a very common procedure; taking a set and adding some structure to construct a new mathematical object. We read $(A, S)$ as “the set $A$ is equipped with structure $S$”. This notion is explored further in [abstract algebra]().

Here we define some common sets with added structure.

:::definition[Proset]
A _proset_ (short for _preordered set_) is a tuple $(A, \leq)$ where $A$ is a set and $\leq$ is a _preorder_; a binary relation satisfying:

- [Reflexivity](relation#reflexivity)
- [Transitivity](relation#transitivity)
:::

:::definition[Poset]
A _poset_ (short for _partially ordered set_) is a tuple $(A, \leq)$ where $A$ is a set and $\leq$ is a _partial order_; a binary relation satisfying:

- [Reflexivity](relation#reflexivity)
- [Transitivity](relation#transitivity)
- [Antisymmetry](relation#antisymmetry)
:::

:::definition[Totally ordered set]
A _totally ordered set_ is a tuple $(A, \lt)$ where $A$ is a set and $\lt$ is a _total order_; a binary relation satisfying

- [Connex](relation#connex)
- [Transitivity](relation#transitivity)
- [Antisymmetry](relation#antisymmetry)
:::

:::remark
The above definitions have corresponding _strict_ versions (_strict partial order_ and _strict total order_), where all reflexive relations are removed.
:::
