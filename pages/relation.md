---
prerequisites:
  - set
---

# Relation

:::definition[(Binary) Relation]

Let $A$ and $B$ be sets. A relation on the [cartesian product]() $A \times B$ (or, a relation between $A$ and $B$) is a tuple $(A\times B, R)$ where $R \subset A \times B$.

Two elements $a\in A$ and $b\in B$ are said to be related by a relation $R$ if $(a, b) \in R$. We write $aRb$ and read “$a$ is related to $b$ (via (relation) $R$)”.
:::

:::definition[$n$-ary relation]

Let $A_1, A_2, \ldots, A_n$ be sets. An $n$-ary relation on $A_1 \times A_2 \times \cdots \times A_n$ is a subset of $A_1 \times A_2 \times \cdots \times A_n$.
:::

:::definition[Converse relation]

The _converse_ relation of a relation $R$ on $A \times B$ is the relation $R^T = \{(y, x) : (x, y) \in R\}$ on $B \times A$.

Aka. _transpose_ and _opposite_ relation.
:::

:::definition[Equality of relations]

Formally we say that a relation is a tuple $(A \times B, R)$ where $A$ and $B$ are sets and $R$ is a subset of $A \times B$.

Two relations $(A_1 \times B_1, R_1)$ and $(A_2 \times B_2, R_2)$ are considered equal if they are equal as tuples. That is, if $A_1 = A_2$, $B_1 = B_2$ and $R_1 = R_2$.
:::

:::observation[Number of relations]
Each relation on $A \times B$ is an element of the [power set]() $\href{power-set}{\mathcal{P}}(A \times B)$ and vice versa.

For a finite set $A$ we have $|\mathcal{P}(A)| = 2^{|A|}$. [[Proof](https://proofwiki.org/wiki/Cardinality_of_Power_Set_of_Finite_Set)]. Thus, assuming $A$ and $B$ to be finite, the number of relations on $A \times B$ is $|\mathcal{P}(A \times B)| = 2^{|A \times B|}$. Similarly, the number of endorelations on a set $A$ is $2^{|A^2|} = 2^{|A|^2}$.
:::

## Types of endorelations

:::definition[Endorelation]
An endorelation on a set $A$ is a relation on $A \times A$.
:::

Let $R$ be an endorelation on $A$. We then define the following types of endorelations:

:::definition[Reflexive]
$\forall a \in A \, (aR a)$
:::

:::definition[Connex]
$\forall a, b \in A \, (aRb \lor bRa)$. Note: Implies reflexivity.
:::

:::definition[Symmetric]
$\forall a,b \in A \, (aRb \rightarrow b{R} a)$
:::

:::definition[Asymmetric]
$\forall a,b \in A \, (aRb \rightarrow \lnot (bRa))$
:::

:::definition[Antisymmetric]
$\forall a,b \in A \, (aRb \land bRa \implies a = b)$
:::

:::definition[Transitive]
$\forall a, b, c \in A \, (aRb \land bRc \implies aRc)$
:::

:::definition[Equivalence relation]
reflexive $\land$ symmetric $\land$ transitive
:::

## Types of relations

Let $R$ be a on $A \times B$. We then define:

:::definition[Left-unique]
$\forall a_1, a_2 \in A, b \in B \, (a_1Rb \land a_2Rb \implies a_1=a_2)$ Aka _injective_.
:::

:::definition[Right-unique]
$\forall a \in A, b_1, b_2 \in B \, (aRb_1 \land aRb_2 \implies b_1=b_2)$ Aka. _partial function_.
:::

:::definition[Left-total]
$\forall a \in A \;\exists b \in B \, (aRb)$
:::

:::definition[Right-total]
$\forall\, b \in B \;\exists\, a \in A \, (aRb)$ Aka. _surjective_.
:::
