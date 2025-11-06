>**Theorem**  Stinespring (Unitary) Dilation, 1955
>Every *completely positive* (CP) linear map
>$$T: \mathcal{B}(\mathcal{H}) \to \mathcal{B}(\mathcal{H}')$$
>can be represented as $T(\rho) = V^{\dagger}(I_{\mathcal{H}'} \otimes \rho) V$
>for some Hilbert Space $\mathcal{K}$ and bounded linear operator $V: \mathcal{H}' \to \mathcal{H} \otimes \mathcal{K}$

>**Lemma** Trace-Preservation in Stinespring Dilation
>When $T$ is also *trace-preserving*, this can be rewritten more physically as a unitary dilation:
>$$T(\rho) = \text{Tr}_{\mathcal{K}}\left[U(\rho \otimes |0\rangle \langle 0 |^{\mathcal{K}})U^{\dagger}\right]$$

### **What are $\mathcal{H}$ and $\mathcal{K}$?**

$\mathcal{H}$: the *system Hilbert Space*
- This is the quantum system that is being studied. 
- A density operator $\rho \in S(\mathcal{H})$ lives here (a Hermitian, positive semidefinite, trace-$1$ operator on $\mathcal{H}$)

$\mathcal{K}$: an *ancillary Hilbert space* (the "environment")
- This represents extra degrees of freedom you can attach to your system, sometimes called an environment, ancilla, or bath.
- It can be any Hilbert space large enough for the theorem to work
- Physically, $\mathcal{K}$ might model a system your main system interacts with and is later "traced out".

### **What is $\mathcal{H} \otimes \mathcal{K}$**

This the *tensor product space* combining your system and the environment.
$$\mathcal{H} \otimes \mathcal{K} = \text{joint Hilbert space of (system + environment)}$$
- Vectors in this space describe *joint states* of both system and environment
- Operators (like $U$) can act on this larger combined space

### **What is a CPTP map?**

Refer to here: [[CPTP and General Evolution]]


### **Breaking Down the Lemma**

We have the following result from earlier:
$$T(\rho) = \text{Tr}_{\mathcal{K}}\left[U(\rho \otimes |0\rangle \langle 0 |^{\mathcal{K}})U^{\dagger}\right]$$

What it means, is any quantum channel $T$ (any physically valid operation on a density matrix $\rho$) can be described as
- Start with your system's state $\rho$
- Attach an auxiliary system ("environment") initially in state $|0\rangle\langle0|$
- Apply a joint unitary $U$ on the combined system
- Trace out ("discard") the environment using the partial trace to get the final system state $T(\rho)$

### **Intuition**

Why the partial trace on $\mathcal{K}$?
Imagine you have two systems $A$ (your qubit) and $B$ (the environment):
1. $A$ and $B$ interact via some reversible, joint $U$.
2. You later look only at $A$

Because you don't know what happened in $B$, you describe $A$'s state by averaging over $B$'s possible outcomes -> that's exactly what the partial trace does.

So *irreversibility* appear purely because you ignore part of the universe, the full evolution is still clean and unitary, we jut see a messy projection of it.

>*Takeaway*
>The Stinespring dilation shows that allow quantum processes, no matter how noisy or irreversible, are just the shadow of a bigger, reversible universe.

### **Also See**

Why is quantum evolution always unitary?
[[Wigner's Theorem - Quantum Evolution is Unitary]]