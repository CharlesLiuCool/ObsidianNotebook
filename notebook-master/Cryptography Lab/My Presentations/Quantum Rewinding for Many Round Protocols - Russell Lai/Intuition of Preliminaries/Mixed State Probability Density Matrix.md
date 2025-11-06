>**Definition** Mixed State
>A mixed state describes a quantum system that is not in a definite pure state, but rather a probabilistic mixture of several possible pure states.
> 
> Suppose a system can be in pure state $| \psi_i \rangle$ with classical probability $p_i$ (where $p_i \ge 0$ and $\sum\limits_{i} p_i = 1$)
> The system's *mixed state* is represented by the *density matrix*
> $$\rho = \sum\limits_i p_i |\psi_i \rangle \langle \psi_i |$$

Just like in classical systems, we want something that encapsulates the probability weights of certain expected values of outcomes. 

In quantum mechanics, we use the state operator ket-bra to denote the probability density matrix, where applying it on a observable (also ket-bra) and then taking the trace results in the expected value
$$\langle O \rangle = \text{Tr}(\rho O)$$
where $\langle O \rangle$ denotes the expectation value of any observable $O$, $\rho$ is the probability density matrix (ket-bra), and $O$ is any observable.

The trick is when we take the trace on our newly defined $\rho = \sum\limits_i p_i |\psi_i \rangle \langle \psi_i |$, we find the expectation is
$$\text{Tr}\left(\sum\limits_i p_i |\psi_i \rangle \langle \psi_i | O\right) = \sum\limits_i p_i\text{Tr}(|\psi_i \rangle \langle \psi_i | O)$$
since trace has linear properties, so summation and constants can be taken out.

Notice, this is precisely what we want! Expectations of each pure state (a superposition) weighted by probability.

See here for more detail: [[Ket-Bra as Probability Density Matrix]]