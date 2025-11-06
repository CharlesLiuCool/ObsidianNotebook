>**Definition** Hermitian Operator
>Let $\mathcal{H}$ be a complex Hilbert space, and let
>$A: \mathcal{H} \to \mathcal{H}$ be a linear operator.
>
>Then $A$ is a Hermitian if
>$$A = A^{\dagger}$$
>where $A^\dagger$ (the *adjoint* of $A$, or the conjugate transpose) is defined by the condition
>$$\langle x,Ay\rangle = \langle A^{\dagger}x, y \rangle \text{ for all }x,y \in \mathcal{H}$$
>So $A$ is Hermitian if
>$$\langle x, Ay \rangle = \langle Ax, y \rangle \; \forall\;x,y \in \mathcal{H}$$


### **Why Need Hermiticity?**

Suppose by Born's Rule we want to solve the expected value of some operator $A$.

$$\langle \psi | A | \psi \rangle$$

This is just an arbitrary inner product, there's no guarantee it will result in a real value!

>*Common Misconception*:
>But in Born's rule (and when motivating real expected values/probability), we showed that the value $\langle \psi | O | \psi \rangle$ had to be real (where $O$ is some observable)!
> 
> $O$ is some projector, $| a \rangle \langle a |$, and is automatically Hermitian! We are dealing with a more general case here.

If we instead say $A$ is Hermitian (so $A = A^{\dagger}$), we see that the complex conjugate of $\langle \psi | A | \psi \rangle$:
$$(\langle \psi | A | \psi \rangle)^* = (\langle A^{\dagger} \psi | \psi \rangle)^* = \langle \psi | A^\dagger | \psi \rangle$$

Since the complex conjugate is equal to itself, $\langle \psi | A | \psi \rangle$ has to be real.

>*Takeaway*:
>Hermiticity implies real expectations for observables.