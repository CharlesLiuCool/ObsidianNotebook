>**Theorem.** Wigner's Theorem
>Any transformation of quantum states that preserves transition probabilities
>$$|\langle \phi | \psi \rangle |^2$$
>must be either *unitary* or *antiunitary*

Unitary evolution is the *only* kind of linear evolution that
- preserves total probability (so that $\langle \psi | \psi \rangle = 1$ stays true for all time)
- ensures reversibility (quantum mechanics has no built-in dissipation)
- respects superposition and linearity

### **Probability Must Not Change**

A quantum state is normalized:
$$\langle \psi(t) | \psi(t) \rangle = 1$$
If we evolve $|\psi(0)\rangle$ to $|\psi(t)\rangle = T|\psi(0)\rangle$, then normalization demands
$$\langle \psi(0)|T^{\dagger}T|\psi(0)\rangle = 1$$
for every state $|\psi(0)\rangle$

This can only be true if
$$T^\dagger T = \bf{I}$$

That's the definition of a unitary operator!

### **Superposition $\implies$ Linearity**

Quantum mechanics says if a system can be in states $|\psi_i\rangle$ and $|\psi_2\rangle$, it can also be in any superposition:
$$|\psi\rangle = a|\psi_1\rangle + b|\psi_2\rangle$$

To preserve the *superposition principle*, evolution must be *linear*
$$T(a|\psi\rangle + b\psi_2\rangle = aT|\psi_1\rangle + bT|\psi_2\rangle$$

With linearity from above and probability conservation, only *unitary* (or antiunitary) transformations are allowed!

### **What if Evolution Wasn't Unitary**

The following properties would break:
- Normalization $(T^\dagger T = \bf{I}$)
Probabilities wouldn't sum to $1$
- Linearity
Superposition breaks
- Reversibility
No consistent way to "undo" evolution
- Hermitian generator
Observable quantities (like energy) would become complex.

>*Takeaway:*
>Time evolution must be *unitary*, as otherwise various principles of quantum mechanics would break. We need the properties of unitary (preserving lengths (norms) and angles (inner products)).
>
>In closed systems, this is evident. In open systems, it may look non-unitary, but this is just because you're seeing a messy part of a larger unitary process (like Stinespring dilation, see: [[Stinespring (Unitary) Dilation Theorem]])!