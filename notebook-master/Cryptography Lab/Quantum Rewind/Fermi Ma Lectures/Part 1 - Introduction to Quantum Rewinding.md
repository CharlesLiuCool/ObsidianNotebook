**Charles Liu**
$10/13/2025$

___

### **How do Cryptographers Prove Security?**

Crypto Security Proof = (Assumed) Hard Problem + Reduction

Efficient $A$ wins security game $\implies$ Efficient $A'$ solves hard problem

>*Key Point:* We need to find a problem difficult for quantum computers!

___

>**Conjecture**
>Classical security reduction + Quantum-hard problem $\implies$ Post-quantum Security?
>*NO!*

*Counterexample to above Conjecture*

### **`[BCMVV18]` Protocol**

- Efficient classical $P$ *cannot* make $V$ accept assuming LWE
- Efficient quantum $P$ *can* convince $V$ to accept

In `[BCMVV18]` this is a "proof of quantumness", but here we can use it to disprove the conjecture.

>*Takeaway*
>Quantum computers can break classically secure crypto *without* solving the underlying hard problem

How is this possible?

**Classical Reduction**
- Efficient classical $A$ wins security game $\implies$ efficient classical $A'$ solves hard problem

**Quantum Reduction**
- Efficient quantum $A$ wins security game $\implies$ efficient quantum $A'$ solves hard problem

The classical security reduction for the `[BCMVV18]` protocol *does not handle quantum attacks*, so no quantum reductions can exist.

>*Takeaway*
>Quantum computers can break classically secure crypto *without* solving the underlying hard problem.

How is this possible?

Classical security of `[BCMVV18]` relies on *rewinding*

![[Part 1 - Introduction to Quantum Rewinding 2025-10-13 21.18.23.excalidraw|center|600]]

Reduction doesn't work for quantum adversaries because measuring the response can disturb the adversary's state, it can't simply "reset" back to its old state.

![[Part 1 - Introduction to Quantum Rewinding 2025-10-13 21.23.31.excalidraw|center|600]]

>*Takeaway*
>Classical rewinding reductions do not capture quantum adversaries. Rewinding, however, is one of the most common techniques in cryptography?

>[!question]
>Is rewinding-based cryptography and their protocols (zero knowledge proofs, proof of knowledge, etc.) quantumly broken?

No! There are many interesting cases where we can extend classical rewinding techniques to quantum rewinding.

___

### **Quantum Rewind**

Fermi focuses on *interactive proof systems*

>*Proof of Knowledge (PoK)*
>If $P^*$ convinces $V$ to accept, then $P^*$ must "know" a witness.

>*Zero Knowledge \[GMR$85$]*
>View of malicious $V^*$ can be efficiently *simulated* without $P$.

**Blum's Protocol for Hamiltonian Cycles**

In this protocol, the prover and verifier agree on some graph.

The prover is trying to prove to the verifier there is a *Hamiltonian Cycle*.

1. Prover samples random permutation $\pi \leftarrow S_v$, commit to the adjacency matrix $\pi(G)$.
2. Verifier samples random challenge bit $r \in \{0,1\}$
3. Prover receives challenge bit.
	1. If $r = 0$, prover opens everything, reveals all commitments, reveals permutation, and verifier checks if the permutation is indeed a permutation of the original graph.
	2. If $r = 1$, prover just opens the edges corresponding the Hamiltonian cycle and the verifier checks if its a Hamiltonian cycle.

>*Proof of Knowledge* (intuition)
>By binding, the first message determines a graph $H$ such that:
>- $H$ is a permutation of $G$
>- $H$ contains a Hamiltonian cycle

>*Zero Knowledge* (intuition)
>First message reveals nothing since commitments are hiding
>Last message also reveals nothing:
>- $(r = 0)$ random permutation of $G$
>- $(r = 1)$ random cycle

___

### **Classical Proof of Knowledge (PoK)**

In our Blum's Protocol, we could 

>*PoK*: If efficient classical $P^*$ convinces $V$ with probability $\frac{1}{2} + \epsilon$, then we can extract a witness from $P^*$.

>*Rewinding:* Query $P^*$ repeatedly on random $R$ until it answers successfully on both $r = 0$ and $1$.

We get two accepting responses after $O(\frac{1}{\epsilon})$ rewinds.

>*Observation:* Two accepting responses$\implies$ Hamiltonian cycle (unless $P^*$ breaks binding)

___

### **How to Define Post-Quantum Security**

>**Binding Against Quantum Attack**
>Classical PoK for Blum relies on the binding property of the commitments. But for quantum attackers, we need to revisit the *definition of binding*.

>*Naive Post-Quantum Binding Definition*
>QPT attacker can't output `com` and valid $(m_0, d_0), (m_1,d_1)$ for $m_0 \neq m_1$.

`[ARU14]` Quantum attacker* might produce `com`, $|\psi \rangle$ such that:
- Can use $| \psi \rangle$ to open `com` to any $m$
- But can only do this once

The naive definition is satisfied, but this is totally insecure!

>\* Caveat: Assuming a quantum oracle
>\*\* Open: Construct example without oracles
>(This would actually imply the existence of quantum currency!)

___

#### **Better Definition: Collapse-Binding `[Unruh16]`**

$\text{Expt}_b$
Run verifier in superposition on $M$, $D$ and measure its output (accept or reject); abort if reject. On accept, state looks like
$\Sigma_{\text{Com}(md)} =_\text{com} |m \rangle_M |d\rangle_D$.

- If $b = 0$: return $M$, $D$.
- If $b = 1$: measure $M$ and return $M$, $D$.

>*Intuition:* If `Com` is perfectly binding, $\text{Expt}_0$ and $\text{Expt}_1$ are perfectly indistinguishable since  there is only one valid $m$ for any `com`.

>*Why this Definition?*
>- Many good reasons: avoid `[ARU14]` attack, implies other proposed definitions, composable, easy to construct (implied by LWE), etc.
>- Most importantly, this definition makes rewinding possible!

`[U12,U16]`: Blum is a post-quantum PoK if the underlying commitments are collapse-binding.\*

\* `[U12,U16]` analyzes a slightly modified version of Blum's protocol, but later on `[LMS22]` showed the original Blum protocol is post-quantum secure.

___

### **How Collapse Binding Helps Rewinding**

*Difficulty:* Recording response disturbs adversary's state.

- But if the response is the opening to a collapse-binding commitment, we can "lazily" measure $m$.

>"Lazy" Measurement:
>($1$) Run adversary's unitary to generate superposition of responses on registers $M,D$.
>($2$) Check if $M,D$ is valid
>($3$) If so, measure $M$

- If the response is the opening to a collapse-binding commitment, we can "lazily" measure $m$.
- Collapse-binding guarantees that step $(3)$ is computationally undetectable

>*Key Point:* With collapse-binding commitments, we just need to consider measuring the $1$-bit decision (accept/reject).

>**$1$-bit Rewinding Lemma** `[Unruh12]`:
>For any state $|\psi \rangle$ and set of projectors $\{\Pi_r\}_r \in R$ if $p = \Bbb{E}_{r \leftarrow R} ||\Pi_R |\psi\rangle||^2$, then $\Bbb{E}_{r \leftarrow R, s \leftarrow R}|| \Pi_S \Pi_R | \psi \rangle ||^2 \ge p^3$

Define $(\Pi_r,\Bbb{I} - \Pi_r)$ to measure whether adversary succeeds on $r$.

If adversary state is $| \psi \rangle$, its success probability is $p = \Bbb{E}_{r \leftarrow R} ||\Pi_r | \psi \rangle||^2$

By `[U12]`, if we run the adversary on two random challenges, it succeeds twice with probability $\ge p^3$

If adversary is opening a collapse-binding commitment, then we record two accepting transcripts with probability $\ge p^3$.

*NOTE:* This is only useful if $r \neq s$. For Blum $(R = \{0,1\})$, we only extract a witness with $\Omega(\epsilon)$ probability when $p \ge 1/\sqrt{2} + \epsilon$

___

### **Quantum Rewind: Putting it Together**

>*Step 1: Collapsing Commitments `[U16]`*
Recording adversary's response $\approx_c$ recording $1-$bit decision.
>**+**
>*Step 2: $1$-bit Rewinding Lemma `[U12]`*
>If we run a $p$-successful adversary on $2$ random challenges (and only measure the $1$-bit decision), then:
>$$\text{Pr}[\text{succeed twice}] \ge p^3$$


>**Theorem.**
>If a quantum $P^*$ convinces $V$ to accept with probability $\ge \frac{1}{\sqrt{2}} + \epsilon$, we can extract a witness with probability $\Omega(\epsilon)$.

For classical $P^*$, we just need $1/\sqrt{2} + \epsilon$ and we can extract with probability $\approx 1$.

This is just a limitation in analysis! It is in fact as secure in classical setting.

___