# Qubit

:::intuition[Qubit]
Quantum computation performs computation by manipulating qubits, similar to how classical computation performs computation by manipulating bits. A classical bit consists of exactly two discrete states, $0$ and $1$. A qubit is much richer, it has two orthonormal states, $|0⟩$ and $|1⟩$, analogous to the classical case. In addition to this, a qubit can also be in linear combinations (superpositions) of these states.
:::

::::definition[Qubit]
A qubit is a quantum system with two distinct states, $|0⟩$ and $|1⟩$. Thus, the state of a qubit can be represented as

$$
|ψ⟩ = c_1 |0⟩ + c_2 |1⟩
$$

where $c_1, c_2 ∈ ℂ$

:::definition[With real numbers]
Let $c_1 = a e^{iα}$ and $c_2 = b e^{iβ}$. We can then express $\vert\psi\rangle$ as

$$
|ψ⟩ = a e^{iα} |0⟩ + b e^{iβ} |1⟩
$$

where $a, b \ge 0$ and $α, β ∈ [0, 2π)$.
:::
::::

## Non-physical qubit states

The [Born rule]() states that $a^2$ and $b^2$ are the probabilities of finding the state $\vert\psi\rangle$ in state $\vert0\rangle$ and $\vert1\rangle$, respectively. A superposition cannot be directly observed. This is the . Because of this, we must have $a^2+b^2 = 1$. That is, one parameter is uniquely determined by the other. Therefore, it suffices to specify on parameter $a = \sqrt{1-b^2}$ which ranges between $0$ and $1$. Furthermore, the global phase of a quantum system is not physical, see [global vs relative phase], thus an overall factor $e^{i\omega}$ is not visible and we have

$$
\vert\psi\rangle = e^{i\omega}\left( a e^{i(\alpha-\omega)} \vert0\rangle + b e^{i(\beta-\omega)} \vert1\rangle \right)
$$

where $\omega$ is not known. Therefore, information of both $\alpha$ and $\beta$ is not available, only the difference $\beta-\alpha$, as seen by eliminating $\omega$ by letting $\omega = \alpha$ so that we have

$$
\vert\psi\rangle = e^{i\omega}\left( a\vert0\rangle+be^{i(\beta-\alpha)}\vert1\rangle \right),
$$

or if we instead choose $\omega = \beta$ we put the relative phase $\alpha-\beta$ on the $\vert0\rangle$ state

$$
\vert\psi\rangle = e^{i\omega}\left( ae^{i(\alpha-\beta)}\vert0\rangle+b\vert1\rangle \right).
$$

In conclusion, the state $\vert\psi\rangle$ is determined by two real parameters, $0 \le a \le 1$, and $\beta - \alpha$ which is $2\pi$ periodic. Finally, note that for $a = 0$ and $a = 1$, the relative phase is no longer physical, it is part of the global phase. In conclusion, the elements of the Hilbert space are not in one-to-one correspondence with physical states.

The Bloch sphere is the space obtained by identifying physically indistinguishable states.

## References

* http://urn.kb.se/resolve?urn=urn:nbn:se:kth:diva-207177
