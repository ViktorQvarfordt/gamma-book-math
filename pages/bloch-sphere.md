---
prerequisites:
  - qubit
---

# Bloch sphere

The space of the two parameters determining a qubit is the Cartesian product of the interval $[0,1]$ representing the possible values for $a$, and the circle $[0,2\pi]$ with endpoints $0$ and $2\pi$ considered equal. The circle represent the possible values for the relative phase $\beta - \alpha$.

The resulting space is a cylinder with the property that all points on the circles at $a = 0$ and $a = 1$, respectively, are considered equal, since the relative phase is non-physical at these points. The resulting space of physically distinguishable states is topologically equivalent to a sphere. This space is called the Bloch sphere.

:::definition[Bloch sphere]
The Bloch sphere can be parameterized by spherical coordinates and every qubit state can be written uniquely as
$$
\vert\psi\rangle = \cos(\theta/2) \vert0\rangle + e^{i\phi}\sin(\theta/2) \vert1\rangle
$$
where $0 \le \theta \le \pi$ and $0 \le \phi < 2\pi$. This provides geometric intuition for single-qubit operations.

<img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/Bloch_sphere.svg" width=300 />
:::

## References

* http://urn.kb.se/resolve?urn=urn:nbn:se:kth:diva-207177
