>**Definition** Projector
>A *projector* is a special kind of linear operator $\Pi$ on a Hilbert space $\mathcal{H}$ that satisfies two key properties:
>$$\Pi^2 = \Pi \text{ and } \Pi^{\dagger} = \Pi$$
> 
> In other words, its Hermitian and idempotent.
> - *Hermitian ($\Pi^\dagger = \Pi$)*
> This means the operator corresponds to an *observable* (it has real eigenvalues)
> - *Idempotent ($\Pi^2 = \Pi$)*
> Applying the projector twice is the same as applying it once, once you've projected, you stay projected.

>**Definition** Projective Measurement
>A *projective measurement* is a collection of such projectors $\{\Pi_i\}_{i \in S}$, where $S$ is the set of all possible measurement outcomes,  that satisfy
>
>- *Completeness*: $\sum_i \Pi_i = \textbf{I}$
>- *Orthogonality*: $\Pi_i\Pi_j = 0 \text{ for }i \neq j$

### **Geometric Intuition**

Suppose for a Hilbert space $\mathcal{H}$, there is a subspace $V \subseteq \mathcal{H}$.

The projector $\Pi_V$ is the operator that projects any vector onto $V$.

So for any vector $| \psi \rangle$,
$$\Pi_V |\psi \rangle = (\text{component of }|\psi \rangle \text{ lying in }V)$$
and 
$$(1-\Pi_V) |\psi \rangle = (\text{component orthogonal to }V)$$

We can see that if we have multiple orthogonal subspaces
$$\mathcal{H} = \bigoplus_{i\in S}V_i$$
$$V_i \perp V_j \;\forall\;i \neq j$$
collected together in a projective measurement, they effectively *partition* the Hilbert space.

### **Completeness**
Each $P_i$ corresponds to one possible outcome.

The probability of getting outcome $i$ is:
$$p_i = \langle \psi | P_i | \psi \rangle$$

For probabilities to make sense, they must sum to $1$:
$$\sum\limits_ip_i = 1$$

Which means:
$$\sum\limits_i p_i = \sum\limits_i \langle \psi | P_i | \psi \rangle = \langle \psi | \left( \sum\limits_i P_i \rangle \right) |\psi \rangle$$

### **(Very Simple) Example**

Suppose our space is $\Bbb{C}^2$ (one qubit) with basis vectors $|0\rangle = \begin{bmatrix} 1 \\ 0 \end{bmatrix}$ and $|1\rangle = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$.

Define
$$\Pi_0 = |0 \rangle \langle 0 | = \begin{bmatrix} 1 & 0 \\ 0 & 0 \end{bmatrix}, \Pi_1 = | 1 \rangle \langle 1 | = \begin{bmatrix} 0 & 0 \\ 0 & 1 \end{bmatrix}$$

These satisfy:

*Idempotent*: $\Pi_0^2 = \Pi_0$, $\Pi_1^2 = \Pi_1$
*Hermitian*: $\Pi_0^\dagger = \Pi_0$, $\Pi_1^\dagger = \Pi_1$
*Completeness*: $\Pi_0 + \Pi_1 = \textbf{I}$
*Orthogonality*: $\Pi_0\Pi_1 = 0$