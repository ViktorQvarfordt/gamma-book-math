# Dirac notation

Let $\{e_j\}_j$ and $\{f_j\}_j$ be two orthonormal [bases](basis). We thus have two resolutions of the identity,

$$
I = \sum_j \vert e_j \rangle\langle e_j \vert =
\sum_j \vert f_j \rangle\langle f_j \vert.
$$

## Vectors

A vector $\vert\psi\rangle$ can be expanded in either basis

$$
\vert\psi\rangle =
\sum_j \vert e_j \rangle\langle e_j \vert\psi\rangle =
\sum_j \vert f_j \rangle\langle f_j \vert\psi\rangle.
$$

The components are related by

$$
\begin{aligned}
\langle e_j \vert \psi \rangle &= \sum_k \langle e_j \vert f_k \rangle \langle f_k \vert \psi \rangle \\
\iff \psi^e_j                  &= \sum_k S_{jk} \psi^f_k \\
\iff \psi^e                    &= S \psi^f
\end{aligned}
$$

where $S$ is the matrix with elements $S_{jk} = \langle e_j \vert f_k \rangle$.

## Matrices

A matrix $A$ can be expanded in either basis

$$
A = \sum_{j,k} \vert e_j \rangle \langle e_j \vert A \vert e_k \rangle \langle e_k \vert
= \sum_{j,k} \vert f_j \rangle \langle f_j \vert A \vert f_k \rangle \langle f_k \vert
$$

The components are related by

$$
\begin{aligned}
\langle e_j \vert A \vert e_k \rangle &= \sum_{p,q} \langle e_j \vert f_p \rangle \langle f_p \vert A \vert f_q \rangle \langle f_q \vert e_k \rangle \\
\iff A^e_{jk} &= \sum_{p,q} S_{jp} A^f_{pq} S^{-1}_{qk} \\
\iff A^e &= S A^f S^{-1}
\end{aligned}
$$

Where

$$
\left(SS^{-1}\right)_{jk} =
\sum_m S_{jm} S^{-1}_{mk} =
\sum_m \langle e_j \vert f_m \rangle \langle f_m \vert e_k \rangle =
\langle e_j \vert e_k \rangle =
\delta_{jk}
$$

shows that $S^{-1}$ indeed is the inverse of $S$.
