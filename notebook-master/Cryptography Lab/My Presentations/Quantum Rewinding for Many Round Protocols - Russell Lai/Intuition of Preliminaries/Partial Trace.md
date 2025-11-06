>**Definition** Partial Trace
>Let $\rho_{AB}$ be a density operator on $\mathcal{H}_A \otimes \mathcal{H}_B$.
>The partial trace over $B$ is the unique map
>$$\text{Tr}_B: S(\mathcal{H}_A \otimes \mathcal{H}_B) \to S(\mathcal{H}_A)$$
>such that for product states:
>$$\text{Tr}_B(\rho_A \otimes \rho_B) = (\text{Tr}\rho_B) \rho_A$$
>*Note:* Since $\text{Tr}(\rho_B) = 1$ for a normalized state, this just gives back $\rho_A$

Pick an orthonormal basis $\{|b_i \rangle\}$ for subsystem $B$.
Then the *partial trace* is defined as:
$$\text{Tr}_B(\rho_{AB}) = \sum\limits_i (\Bbb{I}_A \otimes \langle b_i |) \rho_{AB} (\Bbb{I}_A \otimes |b_i \rangle)$$

This is like the ordinary trace, except you only trace over the $B$ indices.

The partial trace mathematically represents "throwing away information" about one subsystem. It gives you the *effective state* of what remains. If the total system is entangled, the subsystem's state becomes *mixed* (not a pure vector).

Think of it as
$$\rho_A = \text{average of }\rho_{AB}\text{ over all possible states of B}$$

### **Why It's a CPTP Map**

We call the partial trace a *CPTP map* because it satisfies:
- *Completely Positive (CP)*: it sends positive operators to positive ones, even if you extend it with identities on other spaces.
- *Trace Preserving (TP)*: it doesn't change totally probability
$$\text{Tr}[\text{Tr}_B (\rho_{AB})] = \text{Tr}(\rho_{AB}) = 1$$