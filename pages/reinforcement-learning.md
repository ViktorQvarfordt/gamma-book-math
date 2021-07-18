# Reinforcement learning

Mostly following the notation of Reinforcement Learning - Sutton, Barto.

## Basics

The set of states, actions and rewards is denoted $\mathcal{S}$, $\mathcal{A}$ and $\mathcal{R}$, respectively.

Probability of transition to state $s'$ with reward $r$, from state $s$ and action $a$:


:::definition[MDP dynamics]
Probability of transition to state $s'$ with reward $r$, from state $s$ and action $a$:
$$
p(s', r | s, a) = P(S_t = s', R_t = r \mid\allowbreak S_{t-1} = s, A_{t-1} = a)
$$
:::

:::definition[State-transition probabilities]
Probability of transition to state $s'$, from state $s$ taking action $a$:
$$
p(s' | s, a) = P(S_t = s' \mid\allowbreak S_{t-1} = s, A_{t-1} = a) = \allowbreak
\sum_{r \in \mathcal{R}} p(s', r | s, a)
$$
:::

:::definition[Expected reward]
Expected immediate reward from state $s$ after action $a$:
$$
r(s, a, s') = E(R_t | S_{t-1} = s, A_{t-1} = a) = \allowbreak
\sum_{r \in \mathcal{R}, s' \in \mathcal{S}} r\,p(s', r | s, a)
$$
Expected immediate reward on transition from $s$ to $s'$ under action $a$:
$$
r(s, a) = E(R_t | S_{t-1} = s, A_{t-1} = a, S_t = s') = \allowbreak
\sum_{r \in \mathcal{R}} r \frac{p(s', r | s, a)}{p(s' | s, a)}
$$
:::

:::definition[Return]
$$
G_t = \sum_{k=t+1}^T \gamma^{k-t-1} R_k
$$
where $T = \infty$ or $\gamma = 1$ (but not both) to allow for both episodic and continuing tasks.
:::

::::observation[Recursion formula]
$$
G_t = R_{t+1} + \gamma G_{t+1}
$$

:::proof
$$
\begin{aligned}
  G_t &= R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \ldots \\
  &= R_{t+1} + \gamma (R_{t+2} + \gamma R_{t+3} + \gamma^2 R_{t+4} + \ldots ) \\
  &= R_{t+1} + \gamma G_{t+1}
\end{aligned}
$$
:::
::::


:::definition[Policy]
A _policy_ $\pi$ is a mapping from states to probabilities of selecting each possible
action. An agent acting according to a policy will select action $a$ when in state $s$ with probability $\pi(a|s)$.
Furthermore, we introduce the notation $E_\pi(X)$ to denote the expected value of $X$ given that the agent follows policy $\pi$.
:::

:::definition[State-value function]
$$
v_\pi(s) = E_\pi(G_t \mid S_t = s)
$$
:::

:::definition[Action-value function]
$$
q_\pi(s, a) = E_\pi(G_t \mid S_t = s, A_t = a)
$$
:::

:::observation[Relation between $v_\pi(a)$ and $q_\pi(s, a)$]
$$
v_\pi(s) = \sum_{a \in \mathcal{A}} q(s, a) \pi(a|s)
$$
$$
q_\pi(s, a) = \sum_{s' \in \mathcal{S}} v_\pi(s') p(s' | s, a)
$$
:::

::::theorem[Bellman equation]
$$
v_\pi(s) = \sum_{a, r, s'} \pi(a|s) p(s', r | s, a) (r + \gamma v_\pi (s'))
$$
:::proof
$$
\begin{aligned}
v_\pi(s) &= E_\pi(G_t | S_t = s) \\
&= E_\pi(R_{t+1} + \gamma G_{t+1} | S_t = s) \\
&= \sum_{a, r, s'} \pi(a|s) p(s', r | s, a) (r + \gamma v_\pi (s') )
\end{aligned}
$$
:::

:::intuition
When in state $s$ the agent will take action $a$ with probability $\pi(a|s)$ and thereafter get reward $r$ and end up in state $s'$ with probability $p(s', r | s, a)$. At this point—which can be seen as a branch of the future that occurs with probability $\pi(a|s)p(s',r|s,a)$, accounting for the first two factors of the summand—the agent has received reward $r$ and the expected future reward is $\gamma v_\pi(s')$, i.e. $(r + \gamma v_\pi(s'))$ accounts for the third factor of the summand.
:::
::::

:::definition[Optimal policy]
A [partial order]() of policies is given by $\pi \ge \pi'$ if and only if $v_\pi(s) \ge v_{\pi'}(s)$ for all $s \in \mathcal{S}$.
An optimal policy $\pi_*$ is such that $v_{\pi_*}(s) \ge v_\pi(s)$ for all policies $\pi$ and states $s$. We write $v_* \coloneqq v_{\pi_*}$.
The optimal state- and action-value function are given by
$$
\begin{aligned}
v_*(s) &= \max_\pi v_\pi(s) \\
q_*(s,a) &= \max_\pi q_\pi(s, a).
\end{aligned}
$$
:::

:::theorem[Bellman optimality equation]
$$
\begin{aligned}
v_*(s) &= \max_a q_*(s, a) \\
&= \max_a E_{\pi_*}(G_t | S_t = s, A_t = a) \\
&= \max_a E_{\pi_*}(R_{t+1} + \gamma G_{t+1} | S_t = a, A_t = a) \\
&= \max_a E(R_{t+1} + \gamma v_*(S_{t+1}) | S_t = a, A_t = a) \\
&= \max_a \sum_{s',r} p(s', r | s, a) (r + \gamma v_*(s')) \\
q_*(s, a) &= E(R_{t+1} + \gamma v_*(S_{t+1}) | S_1 = s, A_t = a) \\
&= E(R_{t+1} + \gamma \max_{a'} q_*(S_{t+1}, a') | S_1 = s, A_t = a) \\
&= \sum_{s', r} p(s', r | s, a)(r + \gamma \max_{a'}q_*(s', a'))
\end{aligned}
$$
:::

### References

- https://drive.google.com/open?id=1opPSz5AZ_kVa1uWOdOiveNiBFiEOHjkG
- http://incompleteideas.net/book/the-book-2nd.html
- https://github.com/ShangtongZhang/reinforcement-learning-an-introduction


## Bandits, contextual bandits and general RL


- **General RL:** Actions affect the next state and reward.
- **Contextual bandit:** Actions affect only the immediate reward.
- **Bandit:** Trivial state space $|S| = 1$.
