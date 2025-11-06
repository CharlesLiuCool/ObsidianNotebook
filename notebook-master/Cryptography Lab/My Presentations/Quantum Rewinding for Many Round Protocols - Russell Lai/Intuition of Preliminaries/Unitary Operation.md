>**Definition** (Unitary Operation)
>A *unitary operation* $U$ is a linear operator acting on a complex Hilbert space (the vector space of quantum states).
>$$U: \mathcal{H} \to \mathcal{H}, U^{\dagger}U = UU^{\dagger} = \bf{I}$$
>If you choose an orthonormal basis, you can represent $U$ as a *complex square matrix* that satisfies
>$$U^{\dagger} = U^{-1}$$
>So a unitary matrix is just a complex generalization of an *orthogonal matrix* (which preserves lengths and angles in real vector spaces)

### **Motivating The Definition: How it Transforms**

#### **Thought Experiment**

Imagine you have two vector of unit length that starts on the origin and lands on some sphere. What kind of operations would preserve both their magnitudes and the angle (together, their "overlap") between them?

![[Unitary Operation 2025-11-05 13.46.33.excalidraw|center]]

That's right, a rotation works! That is an example of a unitary operator, among many others. Intuitively, the whole point of a unitary operator is we need something to protect the "overlap" between two vectors, because in quantum mechanics, that represents *probability*!

#### **Transforming Kets**

The unitary operation transforms kets as such:
$$|\psi \rangle \leftarrow U|\psi\rangle$$

Why?
- It must preserve probability, which is the same as *preserving inner products*

Suppose we have two states $|\psi\rangle$ and $|\phi\rangle$ which have overlap $\langle \phi | \psi \rangle$. The transformation should not change the magnitude of that overlap
$$|\langle \phi | \psi \rangle |^2 = |\langle \phi'|\psi'\rangle|^2$$
where $|\phi'\rangle = U|\phi\rangle$ and $|\psi' \rangle = U|\psi\rangle$.
We then find
$$|\langle \phi'|\psi'\rangle|^2 = \langle \phi | U^{\dagger} U |\psi \rangle = \langle \phi | \psi \rangle$$

We see, $U^\dagger U = \bf{I}$ is a requirement for unitary transformation on kets to work!

#### **Transforming Density Matrices**

Russell Lai's paper mentions that probability density matrices under unitary transformation look like:
$$U \rho U^{\dagger}$$

We see that for $\rho = | \psi \rangle \langle \psi |$ when we do $|\psi'\rangle = U | \psi \rangle$,
$$\rho' = | \psi' \rangle \langle \psi' | = U | \psi \rangle \langle \psi | U^{\dagger} = U \rho U^{\dagger}$$

### **Why $\text{Tr}(\rho) = 1$ Means Total Probability Holds**

In probability, the some of the probability of all the outcomes in the sample space has to add to one. Suppose a set of positive measurement operators $\{E_i\}$. The probability of some outcome $i$ is given by *Born's rule*
$$P(i) = \text{Tr}(\rho E_i)$$

These $E_i$ must satisfy
$$\sum\limits_i E_i = \bf{I}$$
or the quantum version of total probability law (total probability sums to $1$).

Recall, each of these $E_i$ are projective measurements that partition the Hilbert space into a bunch of (possibly overlapping) subregions, one for each possible outcome. 

This condition guarantees when you do a measurement, something will happen.

For any state $|\psi \rangle$:
$$\sum\limits_i \langle \psi | E_i | \psi \rangle = \langle \psi | I | \psi \rangle = 1$$

We see that because the sum of all the outcomes has to equal $1$,
$$\sum\limits_i P(i) = 1$$
we get
$$\sum\limits_iP(i) =  1 =\sum\limits_i\text{Tr}(\rho E_i) = \text{Tr}(\rho \sum\limits_i E_i) = \text{Tr}(\rho)$$

We thus see why
$$\text{Tr}(\rho) = 1$$

>*Takeaway*
>The following are equivalent
>1. $\sum\limits_i E_i = \bf{I}$
>2. $\text{Tr}(\rho) = \sum\limits_i P(i)$

### **Trace is Cyclic**

For a mixed/pure state described by the density operator, probabilities are measured by
$$P(E) = \text{Tr}(\rho E)$$

What's interesting is that because trace is cyclic, or in other words:
$$\text{Tr}(ABC) = \text{Tr}(BCA) = \text{Tr}(CAB)$$

>*Proof*
>First, prove $\text{Tr}(AB) = \text{Tr}(BA)$
>$\text{Tr}(AB)  = \sum\limits_{i=1}^n (AB)_{ii} = \sum\limits_{i=1}^n \sum\limits_{k=1}^n A_{ik} B_{ki}$
>$\text{Tr}(BA) = \sum\limits_{i=1}^n (BA)_{ii}  = \sum\limits_{i=1}^n \sum\limits_{k=1}^n B_{ik}A_{ki}$
>Notice if we just reverse the name of the indices $i$ and $k$, these two are the same!
>Next, notice that if we have
>$\begin{align}\text{Tr}(A_1A_2 ...A_n) &= \text{Tr}((A_1A_2 ...A_{n-1})A_n) \\ &= \text{Tr}(A_n (A_1A_2 ... A_{n-1}))\end{align}$
>We thus easily observe the cyclical property.
> 
> In fact, any function where $f(AB) = f(BA)$ is invariant under cyclic shifts!

### **Unitary Preserves Probability**

Earlier, we found unitary transformations on states look like $U \rho U^{\dagger}$.

It's easy to see that probability preservation holds. Suppose $\rho' = U \rho U^{\dagger}$, we get:
$$\text{Tr}(\rho) = 1 \implies \text{Tr}(\rho') = 1$$

Since
$$\text{Tr}(\rho') = \text{Tr}(U \rho U^{\dagger}) = \text{Tr}(\rho U^{\dagger}U) = \text{Tr}(\rho) = 1$$

### **Pictures of Transformation**

We see that when we apply the transformation $U \rho U^{\dagger}$,
$$\text{Tr}(EU \rho U^{\dagger}) = \text{Tr}(U^{\dagger}EU \rho )$$

This means to achieve the same transformation effect, we can either apply unitaries on the measurement operator, or the probability density matrix (state)!

That's the essense of *Schrödinger* vs. *Heisenberg picture*.


There are two equivalent perspectives in quantum mechanics regarding unitary transformation:

*Schrödinger Picture*:
- The state evolves $\rho' = U\rho U^{\dagger}$
- Measurement operators $E$ stay fixed

Then $P'(E) = \text{Tr}(E\rho') = \text{Tr}(EU\rho U^{\dagger})$

*Heisenberg Picture:*
- The state stays fixed: $\rho' = \rho$
- The observable measurement evolves: $E' = U^{\dagger}E U$
Then $P'(E) = \text{Tr}(E' \rho) = \text{Tr}(U^{\dagger} E U \rho)$

We see that
$$\text{Tr}(EU\rho U^{\dagger}) = \text{Tr}(U^{\dagger}E U \rho)$$

This is just like relativity. Schrodinger sees the state evolving, while the observables stay fixed, whereas Heisenberg sees the opposite. It's just a matter of perspective.

Imagine you (the state) are in a moving car:
![[Unitary Operation 2025-11-05 13.54.57.excalidraw|center|800]]
