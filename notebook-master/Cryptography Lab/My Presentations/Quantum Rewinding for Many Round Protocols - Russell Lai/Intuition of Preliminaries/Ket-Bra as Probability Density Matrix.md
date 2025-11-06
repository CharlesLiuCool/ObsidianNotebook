### **Physical Quantities must give Real Numbers**

In quantum mechanics, measurable quantities like *probabilities*, *expectation values*, and *energies* must always be *real numbers* that can be observed in experiments.

However, the state $|\psi\rangle$ is a vector in a complex vector space, so it contains complex amplitudes. $|\psi\rangle$ itself is just an abstract vector.

To get real, measurable numbers, we need to pair with something that "extracts" a scalar.

This is where the *bra* $\langle \psi|$ comes in.

![[Ket-Bra - The Projection Operator 2025-09-22 21.30.15.excalidraw]]


___

### **Inner Products**

Inner products turns vectors into real numbers with bilinearity (linear in each argument separately)

In linear algebra, to extract a scalar from a vector, you take an *inner product*:
$$\langle \phi | \psi \rangle$$
This is a sesquilinear form, it takes two vectors and returns a number.
In matrix notation:
$$\langle \phi | \psi \rangle = \phi^{\dagger} \psi$$

*Sesquilinear* means one-and-a-half linear. Here, the ket is *linear* whereas the bra is *conjugate linear*.
- $\langle \phi | (a \psi_1 + b\psi_2) \rangle = a\langle\phi|\psi_1\rangle + b\langle\phi|\psi_2\rangle,$
- $\langle a\phi_1 + b\phi_2, \psi \rangle = a^*\langle\phi_1|\psi\rangle + b^*\langle \phi_2 | \psi \rangle$

The conjugates are what ends up ensuring real, positive probabilities.

Sesquilinearity guarantees that $\langle \psi | \psi \rangle$ is real and positive, even though the components of $| \psi \rangle$ is complex.

___

### **Probabilities are Quadratic since Amplitudes are Complex**

Quantum mechanics assigns *complex amplitudes* to outcomes, not probabilities directly.

If an outcome $a$ corresponds to the state $|a \rangle$, then the *amplitude* for outcome $a$ is
$$\langle a | \psi \rangle$$

>[!book]- Proof
This is because each state $|\psi\rangle$ can always be written as a superposition of basis states (that are orthogonal)
$$|\psi\rangle = \sum\limits_i c_i | a_i \rangle$$
>
If we take the inner product on both sides,
$$\langle a_i|\psi\rangle = c_i$$
since all the elements in the summation where $|a_i\rangle$ is orthogonal go to zero, leaving $\langle a_i | a_i \rangle = 1$.

The *probability* must be real and nonnegative, so we take:
$$P(a) = |\langle a | \psi \rangle |^2 = (\langle a | \psi \rangle)^* (\langle a | \psi \rangle) = \langle\psi |(|a \rangle \langle a |) |\psi \rangle$$

(because $|z|^2 = z^*z$ for complex $z$)

So we can interpret this, probability is in the form $\langle \psi | O | \psi \rangle$ where $O$ is a ket-bra projector, and creates an expectation value. This is called the *Born rule*.

This has one copy of the *state vector* and one of the *conjugate*, so its bilinear.

This is why every *measurable prediction* in quantum mechanics looks something like
$$\text{bra} \times \text{operator} \times \text{ket}$$

___

### **Representing with Purely Operators**

We now use the secret ingredient to understand how the expectation value of an observable $O$ in a pure state $|\psi\rangle$ ($\langle \psi| O | \psi \rangle$), can be written as the summation of projection operators $\text{Tr}(|\psi\rangle\langle\psi|O)$.

>**Key Identity**
>$\langle \psi | O | \psi \rangle = \text{Tr}(|\psi\rangle\langle\psi|O)$

*Proof:*
First, we need to understand, what is a *trace*?
The *trace* of an operator (or matrix) $A$ is the sum of its diagonal elements in any orthonormal basis
$$\text{Tr}(A) = \sum\limits_i \langle i | A | i \rangle$$
($\langle i |$ is really just the $i$th row matrix of the identity matrix, and $| i \rangle$ the $i$th column. Notice this extracts the $i$th diagonal element of $A$)

It's *basis independent*, so it gives the same number no matter what orthonormal basis you choose.

Take $A = |\psi\rangle\langle\psi| O$
$$\begin{align} \text{Tr}(|\psi\rangle\langle\psi|O) &= \sum\limits_i \langle i|(|\psi\rangle\langle\psi|O)|i\rangle \\ &= \sum\limits_i \langle i | \psi \rangle \langle \psi | O | i \rangle \\ &= \sum\limits_{i} \langle \psi | O | i \rangle\langle i | \psi \rangle \\ &= \langle\psi|O|\psi\rangle\end{align}$$

This is called resolution of the identity.

___

### **Putting It Together**

Notice the operator we created, $|\psi \rangle\langle \psi |$. It lives in the *same operator space* as observables $O$.

Both the state and the observable are now operators acting on the Hilbert space.

Since we have
$$\langle \psi | O | \psi \rangle = \text{Tr}(|\psi\rangle\langle\psi|O)$$
we can compute expectations of observables with just a trace operation
$$\langle O \rangle = \text{Tr}(\rho O)$$

This solves a bunch of problems. It generalizes and simplifies things. Below are all the things that work with density matrices.
- Only pure states (also works with kets)
- Mixed/uncertain states ($\rho = \sum_i p_i |\psi_i \rangle \langle \psi_i |$)
- Computing expectation values ($\langle \psi | O | \psi \rangle$ turns into $\text{Tr}(\rho O)$ )
- Evolving open systems $(\rho' = UpU^{\dagger})$
- Measuring subsystems (partial trace)

___

### **Takeaway**

>Quantum mechanics is built on *complex amplitudes*, but we can only have *real probabilities*.
>
>To create real, physical predictions, we always have to pair the state with its conjugate. That's why everything becomes *bilinear*, and why $|\psi\rangle\langle\psi|$, the ket-bra, naturally emerges as the **density matrix**.
>
>Its a *state operator* that lets us compute all observable quantities universally, in contrast to the ket $|\psi\rangle$ which describes a *state vector*.

___