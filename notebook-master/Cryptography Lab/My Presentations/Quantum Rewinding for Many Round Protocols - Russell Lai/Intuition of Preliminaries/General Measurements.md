>**Definition** General Measurement
>A *general measurement* is a CPTP map $M: S(\mathcal{H}) \to S(\mathcal{H} \otimes \mathcal{O})$ where $\mathcal{O}$ is an ancilla register holding a classical outcome. Specifically, given measurement operators $\{M_i\}_{i=1}^N$ such that $\sum\limits_{i=1}^n M_i^\dagger M_i = \bf{I}$ and a basis $\{|i\rangle\}_{i=1}^N$ for $\mathcal{O}$, $$M(\rho) = \sum\limits_{i=1}^N(M_i\rho M_i^\dagger \otimes |i\rangle\langle i|^\mathcal{O})$$

### **What We Need From a Measurement**

We need:

1. What outcome you get (the classical information you record)
2. What state remains (the quantum state that remains)

We first start with a naive approach:
1. Take a quantum state $\rho$ on Hilbert Space $\mathcal{H}$
2. Produce an outcome $i$ with probability
$$p_i = \text{Tr}(M_i \rho M_i^\dagger)$$

3. Leave the post-measurement state (if we got outcome $i$) as
$$\rho_i' = \frac{M_i \rho M_i^{\dagger}}{p_i}$$


But this only gives us probabilities and conditional states. To describe the whole thing as *quantum channel*, we need an object that carries both the post-measurement state and the outcome information.

### **Outcome Register $\mathcal{O}$**

To fix, we attach an "outcome register" so we can model the larger quantum process while measuring both the quantum system and classical outcome.

We add an *ancillary system* register ($\mathcal{O}$) with an orthonormal basis $\{|i\rangle\}^{\mathcal{O}}$ representing the classical measurement outcomes.

Now we define a single density matrix that encodes everything:
$$M(\rho) = \sum\limits_{i=1}^N(M_i\rho M_i^\dagger \otimes |i\rangle\langle i|^\mathcal{O})$$

This is *completely positive* since its a Kraus-type sum.

This is *trace preserving* since $\sum\limits_i M_i^{\dagger}M_i = \bf{I}$

### **Solving for Probability**

Suppose we have some outcome in the ancillary, $i$.
$$\Pr[i] = \text{Tr}(|i\rangle\langle i |^{\mathcal{O}}M(\rho))$$

the only term that survives in the trace is the $i$-th one:
$$\Pr[i] = \text{Tr}(M_i\rho M_i^{\dagger})$$
This is Born's rule in Kraus operator form!

So we see why we define $M(\rho)$ as such, it represents a *classical mixture* of your quantum system with classical outcomes. Classical labels $|i\rangle$ are encoded in an ancillary space, and when you read that ancilla, it collapses accordingly.