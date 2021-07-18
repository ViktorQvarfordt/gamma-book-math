# Quantum Perceptron

<!--break-->

*A brief introduction to quantum computing and an algoritm for a quantum perceptron.*

<!--break-->

## Intro

Quantum mechanics is best though of as infinite-dimensional linear algebra (aka. functional analysis where the linear equations are partial differential equations).<!--break-->

We are mostly interested in one single equation,
$$
i \frac{\partial}{\partial t} \vert \psi(t) \rangle = \hat{H} \vert \psi(t) \rangle,
$$
where $\psi(t) \in \mathbb{C}^k$ (considered as a Hilbert space) and the Hamiltonian $\hat{H}$ is Hermitian.<!--break--> The general solution to the equation is given by
$$
\vert \psi(t) \rangle = e^{-i\hat{H}t}\vert \psi(0) \rangle.
$$
<!--break-->
One can show that $\hat{U} = e^{-i\hat{H}t}$ is unitary when $\hat{H}$ is hermitian, thus we see that quantum states have unitary time evolution.<!--break-->

Generally $\hat{H} = \hat{T} + \hat{V} = \nabla_x^2 + V(x, t)$ and the wave functions are $L_2(\mathcal{C})$ functions $\vert \psi \rangle : \mathcal{C} \to \mathbb{C}$ defined on some configuration space $\mathcal{C}$.
<!--break-->

### Quantum computing

Quantum computing is a special case of quantum mechanics where the quantum systems are finite-dimensional.
<!--break-->

Quantum computation is performed by manipulating qubits, similar
to how classical computation performs computation by manipulating bits. A
classical bit consists of exactly two discrete states, 0 and 1. A qubit is much
richer, it has two orthonormal states, $|0⟩$ and $|1⟩$, analogous to the classical case. In addition to this a qubit can also be in linear combinations (superpositions)
of these states.<!--break-->

### Qubit

Formally, a *qubit* is a two-dimensional quantum state
$$
\vert \psi \rangle =
c_0 \vert 0 \rangle + c_1 \vert 1 \rangle =
c_0 \begin{pmatrix} 1 \\ 0 \end{pmatrix} + c_1 \begin{pmatrix} 0 \\ 1 \end{pmatrix},
$$
<!--break-->
where $c_0, c_1 \in \mathbb{C}$ and $|c_0|^2+|c_1|^2 = 1$. $|c_j|^2$ is the probability of a measurement outcome yielding the state $\vert j \rangle$.
<!--break-->
Because of the conditions on $c_j$ it follows from a topology argument that the pure states of a qubit are on the surface of a sphere.
<!--break-->

### Bloch sphere

<img src="https://upload.wikimedia.org/wikipedia/commons/f/f4/Bloch_Sphere.svg" style="display: block; width: 80%; max-width: 300px; margin: 0 auto; margin-bottom: 1rem;" />

$$
\lvert\psi\rangle = \cos(\theta/2)\lvert 0\rangle + e^{i\phi}\sin(\theta/2)\lvert 1\rangle
$$
<!--break-->

### Rotating a qubit

A qubit is manipulated by rotating it along the bloch sphere by applying a unitary operator, representing the time evolution governed by the Hamiltonian and the Schrödinger equation.<!--break-->

Common single-qubit operations include the Pauli matrices
$$
  \sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix},
  \sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix},
  \sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}
$$
that rotate a state $\vert\psi\rangle$ $\pi$ radians along the $x$-, $y$- and $z$-axis, respectively.<!--break--> Note that $\sigma_x$ corresponds to the classical NOT gate, mapping $\vert 0 \rangle \mapsto \vert 1 \rangle, \vert 1 \rangle \mapsto \vert 0 \rangle$.<!--break-->

The phase shift gate
$$
R(\phi) = \begin{pmatrix} 1 & 0 \\ 0 & e^{i\phi} \end{pmatrix}; \quad \vert 0 \rangle \mapsto \vert 0 \rangle, \quad \vert 1 \rangle \mapsto e^{i\phi} \vert 1 \rangle
$$
(possibly implemented by shining a laser of a duration proportional to $\phi$ onto an atom whose spin represents a qubit)
<!--break-->

The Hadamard gate introduces superpositions,
$$
\begin{gather}
  H = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 & 1 \\ 1 & -1 \end{pmatrix} \\
  \quad \vert 0 \rangle \mapsto \frac{1}{\sqrt{2}} (\vert 0 \rangle + \vert 1 \rangle),
  \quad \vert 1 \rangle \mapsto \frac{1}{\sqrt{2}} (\vert 0 \rangle - \vert 1 \rangle).
\end{gather}
$$
<!--break-->

### Multi-qubit systems

Let $\mathcal{H}_1, \mathcal{H}_2, \ldots, \mathcal{H}_N$ be the Hilbert spaces of $N$ qubits. Their total space $\mathcal{H}$ is "the space of all possible superpositions of all possible combinations of single-qubit states", formally this is the tensor product
$$
\mathcal{H} = \mathcal{H}_1 \otimes \mathcal{H}_2 \otimes \cdots \otimes \mathcal{H}_N
$$
<!--break-->

The tensor product makes the space grow exponentially in size
$$
\begin{pmatrix} a \\ b \end{pmatrix} \otimes \begin{pmatrix} c \\ d \end{pmatrix} = \begin{pmatrix} ac \\ ad \\ bc \\ bd \end{pmatrix}
$$
<!--break-->
$$
  \vert 00 \rangle = \begin{pmatrix} 1 \\ 0 \\ 0 \\ 0 \end{pmatrix}, \quad
  \vert 01 \rangle = \begin{pmatrix} 0 \\ 1 \\ 0 \\ 0 \end{pmatrix}, \quad\ldots
$$
<!--break-->

For multi-qubit system, qubits can be *entangled*, effectively creating a spacetime independent correlation. This is what Einstein referred to as "spooky action at a distance". This is one of the special properties of quantum mechanics that makes quantum computing very powerful.<!--break-->

A general state can then be written as
$$
\vert \psi \rangle = \sum_{j=0}^{2^N-1} c_k \vert j \rangle
$$

## Quantum Perceptron

We shall now describe a quantum algorithm for computing the output of a classical perceptron.
<img src="perceptron.png" style="max-width: 300px; display: block; margin: 0 auto;" />
<!--break-->

The idea is to apply two unitary operators in succession to emulate the classical computation, then measure the result on an *ancilla* qubit.<!--break-->

Quantum schematic:
<img src="quantum-perceptron.png" style="max-width: 300px; display: block; margin: 0 auto;" /><!--break-->

It will be able to perform image classification
<img src="img-classification.png" style="max-width: 300px; display: block; margin: 0 auto;" /><!--break-->

Consider an $m$-dimensional classical input $\vec{i}$ and weight vector $\vec{w}$, where $i_j, w_j \in \{-1, 1\}$. This will be encoded on the quantum hardware by using $N$ qubits, where $m = 2^N$ as follows:<!--break-->

$$
\begin{align}
  \vec{i} =
  \begin{pmatrix}
    i_0 \\ i_1 \\ \vdots \\ i_{m-1}
  \end{pmatrix},
  \quad
  \vec{w} =
  \begin{pmatrix}
    w_0 \\ w_1 \\ \vdots \\ w_{m-1}
  \end{pmatrix}
\end{align}
$$
<!--break-->
$$
\begin{align}
  \vert \psi_i \rangle = \frac{1}{\sqrt{m}} \sum_{j=0}^{m-1} i_j \vert j \rangle,
  \quad
  \vert \psi_w \rangle = \frac{1}{\sqrt{m}} \sum_{j=0}^{m-1} w_j \vert j \rangle
\end{align}
$$
<!--break-->

Initialize the qbits in the state $\vert 0 \rangle^{\otimes N}$. Then, define a unitary operator $\hat{U}_i$ such that
$$
\hat{U}_i \vert 0 \rangle^{\otimes N} = \vert \psi_i \rangle
$$
<!--break-->
Next, define a unitary operator $\hat{U}_w$ (that essentially will perform the inner product between $\vec{i}$ and $\vec{w}$) such that
$$
\hat{U}_w \vert \psi_i \rangle = \vert 1 \rangle^{\otimes N} = \vert 2^N - 1 \rangle
$$
<!--break-->

If we apply $\hat{U}_w$ after $\hat{U}_i$ the overall state becomes
$$
\hat{U}_w \hat{U}_i \vert 0 \rangle^{\otimes N} = \hat{U}_w \vert \psi_i \rangle = \sum_{j=0}^{2^N-1} c_j \vert j \rangle \equiv \vert \phi_{i,w} \rangle
$$
<!--break-->

The inner product of $\vert \psi_i \rangle$ and $\vert \psi_w \rangle$ can be computed with a clever trick as
$$
\begin{align}
  \langle \psi_w \vert \psi_i \rangle
  &= \langle \psi_w \vert \hat{U}^\dagger_w \hat{U}_w \vert \psi_i \rangle \\
  &= \langle \hat{U}_w\psi_w \vert \hat{U}_w \psi_i \rangle \\
  &= \langle 2^N - 1 \vert \phi_{i,w} \rangle \\
  &= c_{2^N-1}
\end{align}
$$
<!--break-->

It can also be computed directly from definition as
$$
\langle \psi_w \vert \psi_i \rangle = \frac{1}{m} \sum_{j=0}^{2^N-1} i_j w_j = \vec{i} \cdot \vec{w}.
$$
<!--break-->

Now, observe that the output of the classical perceptron is a coefficient of quantum state,
$$
\vec{i} \cdot \vec{w} = m \langle \psi_w \vert \psi_i \rangle = m c_{2^N-1}
$$
<!--break-->

Extracting this information from the quantum state can be done with by measuring the ancilla qubit after performing a CNOT gate:
<img src="https://upload.wikimedia.org/wikipedia/en/5/58/Cnot-compared-to-xor.svg" style="max-width: 400px; display: block; margin: 0 auto;" /><!--break-->

Performing a multi-controlled CNOT gate on $\vert \hat{U}_w \hat{U}_i \vert 0 \rangle^{\otimes N}$ yields
$$
\vert \hat{U}_w \hat{U}_i \vert 0 \rangle^{\otimes N} \mapsto
\sum_{j=0}^{2^N-2} c_j \vert j \rangle \otimes \vert 0 \rangle_a + c_{2^N-1} \vert 2^N - 1 \rangle \otimes \vert 1 \rangle_a
$$
<!--break-->

Finally, a measurement of the ancilla qubit will yield a collaps of the wave function and result in the outcome corresponding to state $\vert 1 \rangle_a$ with probability
$$
|c_{2^N-1}|^2.
$$
<!--break-->

The difficulty lies in effectively constructing the operators $\hat{U}_i$ and $\hat{U}_w$. Examples:
<img src="2-qubit-perceptron.png" style="max-width: 100%; display: block; margin: 0 auto;" /><!--break-->

Quantum circuit of a $N = 4$ perceptron. In this example, the input vector has elements $i_0 = i_1 = -1$, and $i_j = 1$ for $j = 2, \ldots , 15$, while the weight vector has elements $w_2 = w_3 = w_4 = -1$, and $1$ in all other entries:
<img src="4-qubit-perceptron.png" style="max-width: 100%; display: block; margin: 0 auto;" /><!--break-->


## References

- https://www.technologyreview.com/s/612435/machine-learning-meet-quantum-computing/
- https://arxiv.org/abs/1811.02266
- http://urn.kb.se/resolve?urn=urn:nbn:se:kth:diva-207177 Section 7.1

<!--break-->










<script>
  function findComments (el) {
    const arr = []
    for (let i = 0; i < el.childNodes.length; i++) {
        const node = el.childNodes[i]
        if (node.nodeType === 8) {
            arr.push(node)
        } else {
            arr.push.apply(arr, findComments(node))
        }
    }
    return arr
  }

  if (document.location.search.indexOf('presentation') !== -1) {
    const commentNodes = findComments(document.querySelector('.content'))
    let i = 1;
    for (const node of commentNodes) {
      if (node.nodeValue.startsWith('break')) {
        const div = document.createElement('div')
        div.setAttribute('id', i.toString())
        div.setAttribute('class', 'break')
        node.replaceWith(div)
        i++
      }
    }
    window.maxBreaks = i - 1

    window.i = 0
    function scrollTo(i) {
      const els = document.querySelectorAll('.break')
      for (let i = 0; i < els.length; i++) {
        els[i].style['padding-top'] = ''
        els[i].style['margin-bottom'] = ''
        els[i].style['display'] = 'inline'
      }
      document.getElementById(i).style['margin-bottom'] = '1000px'
      document.getElementById(i).style['display'] = 'block'
      document.getElementById(i).style['padding-top'] = `${window.innerHeight * 0.15}px`

      setTimeout(() => {
        document.getElementById(i).scrollIntoView({
          behavior: 'smooth',
          block: 'end',
          inline: 'nearest'
        })
      }, 0)

      // location.href = `#${i}`
    }

    document.addEventListener('keydown', e => {
      if (e.key === 'ArrowRight') {
        window.i = Math.min(window.i + 1, window.maxBreaks)
      } else if (e.key === 'ArrowLeft') {
        window.i = Math.max(window.i - 1, 0)
      } else {
        return
      }
      console.log('scrolling', window.i)
      scrollTo(window.i)
    })
  }
</script>


<script>
  var newUrl = window.location.protocol + "//" + window.location.host + window.location.pathname + '?theme=white';
  window.history.replaceState(null, null, newUrl)
</script>
