# Incompleteness

The paper in which the theorems are presented:
* [Über formal unentscheidbare Sätze der Principia Mathematica und verwandter Systeme](http://www.w-k-essler.de/pdfs/goedel.pdf)
* [On Formally Undecidable Propositions of Principia Mathematica and Related Systems](https://monoskop.org/images/9/93/Kurt_G%C3%B6del_On_Formally_Undecidable_Propositions_of_Principia_Mathematica_and_Related_Systems_1992.pdf) (translated)

Encyclopedic info about the paper on [wikipedia](https://en.wikipedia.org/wiki/On_Formally_Undecidable_Propositions_of_Principia_Mathematica_and_Related_Systems).

:::context[Formal system]
Let $S$ be a formal system.
:::

:::definition[Syntactic completeness]
A formal system $S$ is *syntactically complete* if for each closed formula $\varphi$ of the system either $\varphi$ or $\lnot\varphi$ is a theorem of $S$.

Equivalently, a formal system is syntactically complete if and only if no unprovable sentence can be added to it without introducing an inconsistency.
:::

:::definition[Semantic completeness (complete with respect to tautologousness)]
$$
\models_S\varphi \implies \ \vdash_S\varphi
$$
Which means that formulas that are true under every interpretation of the language of the system are consistent with the rules of the system.

Semantically complete when all its tautologies are theorems
:::

:::definition[Sound]
$$
 \vdash_S\varphi \implies \ \models_S\varphi 
$$
:::

:::observation{inline}
Syntactive completeness is stronger than semantic completeness.
:::

:::theorem[First incompleteness theorem]
If a (logical or axiomatic formal) system is omega-consistent, it cannot be syntactically complete.
:::


:::theorem[Second incompleteness theorem]
The consistency of axioms cannot be proved within their own system.
:::
