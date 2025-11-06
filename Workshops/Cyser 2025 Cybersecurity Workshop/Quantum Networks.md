*Quantum Computing* - Uses superposition, entanglement, and interference to do calculations

Every computation has three elements:
- *Data*
- *Operations*
- *Results*

In quantum circuits:
- Data: *Qubits*
- Operations: *Quantum Gates*
- Results: *Measurements*

## **Qubits**
*Superposition* - like a spinning coin
Standard:
${| \psi \rangle = \alpha | 0 \rangle + \beta | 1 \rangle}$
Hadamard:
${| \psi \rangle = \alpha | + \rangle + \beta | - \rangle}$

${+}$ is 50-50 zero and one.

## **Quantum Gates**

${|\psi_{\text{out}} = U | \psi_{\text{in}} \rangle}$
${|0\rangle \to X \to | 1 \rangle}$
${X}$ is a bit flip

${|+\rangle \to Z \to | - \rangle}$
${Z}$ is a bit flip in Hadamard

${|0\rangle \to H \to | + \rangle}$
${H}$ is a bit flip that changes to Hadamard basis

## **Measurements**

Projection: project quantum state to classical value ${0}$ and ${1}$. The state collapses.

${p(|v \rangle ) = |\langle v | \psi \rangle |^2}$

${\sum\limits_j p(|v_j \rangle) = 1}$

*No clone theory:* We can't copy a qubit! No quantum gate can do that.

## **The Problem of Key Distribution**

How do we securely share keys?
One protocol: Diffie-Hellman Key Exchange Protocol
*Conditionally secure:* Difficult for someone intercepting to know ${a}$ given ${g, p,}$ and ${A}$.
Quantum computers can break this condition!
*Shor's Algorithm (factorization)*
${O((\log N)^3)}$

${\text{QKD-BB84}}$: Quantum Key Distribution BB84 protocol,

## **Quantum Entanglement**

The act of measuring one determines the result of measuring the other, even when at a distance from each other.

*Bell pairs*
In a general form:
${|B_{xy} \rangle = \dfrac{|0y \rangle + (-1)^x|1\bar{y}}{2}}$

## **Quantum Teleportation**

- Send quantum information
- Alice doesn't know the state, and can't clone it, so she will transfer the state to Bob and at the end Bob will have it, Alice won't
- 3rd party gives Alice and Bob a entangled quantum pair
- Alice uses her part of the quantum pair to "encrypt" her information, sends it over, and Bob uses his part of the pair to "decode" it.

## **Quantum Internet**

- You can distribute these quantum entangled pairs and establish networks