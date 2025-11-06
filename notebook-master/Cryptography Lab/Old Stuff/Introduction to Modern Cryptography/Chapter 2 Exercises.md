---
tags: Cryptography
date: 5/28/2025
---

>[!question] 2.1
>Prove the second direction of Lemma 2.2.

>[!check]- Answer
>${\implies}$
>Assume the scheme is perfectly secret. Then by *Definition 2.1*, ${\text{Pr}[M=m|C=c] = \text{Pr}[M=m]}$
>Multiplying both sides by ${\text{Pr}[C=c]/\text{Pr}[M=m]}$, we get
>$${\dfrac{\text{Pr}[M=m|C=c] \cdot \text{Pr}[C=c]}{\text{Pr}[M=m]} = \text{Pr}[C=c]}$$
>Using Bayes' theorem, the left side is equivalent to ${\text{Pr}[C=c|M=m]}$. So we get
>$${\text{Pr}[C=c|M=m] = \text{Pr}[C=c].}$$

___

>[!question] 2.2
>Prove or refute: For every encryption scheme that is perfectly secret
it holds that for every distribution over the message space ${M}$, every ${m, m' \in M}$, and every ${c \in C}$:
$${Pr[M = m | C = c] = Pr[M = m' | C = c].}$$

>[!check]- Answer
>False
>
*Proof:*
Assume an encryption scheme is perfectly secure and ${Pr[M = m | C = c] = Pr[M = m' | C = c]}$.
>
>By *Definition 2.1*, this is equivalent to ${\text{Pr}[M=m|C=c] = \text{Pr}[M=m] \;\forall\;m \in M}$.
>
Take ${m, m' \in M}$, where ${\text{Pr}[M=m] = 0.7}$ and ${\text{Pr}[M=m'] = 0.3}$. Then ${\text{Pr}[M=m|C=c] = 0.7}$ and ${\text{Pr}[M=m'|C=c] = 0.3}$, but ${Pr[M = m | C = c] \neq Pr[M = m' | C = c]}$.

___

>[!question] 2.3
>When using the one-time pad (Vernam’s cipher) with the key ${k = 0^l}$, it follows that ${\text{Enc}_k(m) = k \oplus m = m}$ and the message is effectively sent in the clear! It has therefore been suggested to improve the one-time pad by only encrypting with a key ${k \neq 0^l}$ (i.e., to have Gen choose ${k}$ uniformly at random from the set of non-zero keys of length). Is this an improvement? In particular, is it still perfectly secret? Prove your answer. If your answer is positive, explain why the one-time pad is not described in this way. If your answer is negative, reconcile this fact with the fact that encrypting with ${0}$ doesn’t change the plaintext.

>[!check]- Answer
> Removing ${k=0^l}$ breaks perfect secrecy. Particularly, all keys must have uniform probability of getting chosen from the *full keyspace* ${\{0,1\}^l}$, and taking ${k=0^l}$ breaks this. Although ${k=0^l}$ presents the message totally clear, this is part of the design, the adversary has no way to know if the ciphertext is the intended plaintext because they are uncertain of the key.
___

>[!question] 2.4
>In this exercise, we study conditions under which the shift, mono-alphabetic substitution, and Vigenère ciphers are perfectly secret:
>
>*(a)* Prove that if only a single character is encrypted, then the shift
cipher is perfectly secret.
*(b)* Describe the largest plaintext space ${M}$ for which the mono-alphabetic substitution cipher provides perfect secrecy. (Note: this space does
not need to contain words that “make sense”.)
*(c)* Show how to use the Vigenère cipher to encrypt any word of length
${n}$ so that perfect secrecy is obtained (note: you can choose the length of the key). Prove your answer.
>
>Reconcile the above with the attacks that were shown in the previous chapter.

>[!check]- Answer
>*(a)*
>*Proof:*
>We first define the shift cipher scheme.
>Let ${M}$ be the message space, ${K}$ be the key space, and ${C}$ be the ciphertext space, where ${M=K=C=\{0,1,...,25\}}$ representing the letters A through Z.
>
We can take a message ${m \in M}$ and encrypt it using a key ${k \in K}$.
>
>Let the key ${k}$ be chosen uniformly at random from ${K}$, where ${Pr[K=k] = \frac{1}{26}}$.
>We define ${\text{Enc}_k(m) = c = (m+k) \text{ mod } 26}$.
>We define ${\text{Dec}_k(c) = m = (c-k) \text{ mod } 26}$.
>
>Since ${k}$ is chosen at uniform random from ${26}$ choices and ${c = (m+k) \text{ mod } 26}$, each of the ${26}$ letters represented are equally likely.
>Thus, ${Pr[C=c|M=m] = \frac{1}{26}}$
>
>We know ${Pr[C=c] = \sum\limits_{m \in M} Pr[C=c|M=m]\cdot Pr[M=m]}$. Since ${Pr[C=c|M=m] = \frac{1}{26}}$ and ${Pr[M=m] = \frac{1}{26}}$ (assuming ${M}$ has uniform distribution), we get ${Pr[C=c] = 26 \cdot \frac{1}{26} \cdot \frac{1}{26} = \frac{1}{26}}$
>
>Since ${Pr[C=c|M=m] = Pr[C=c] = \frac{1}{26}}$, the shift cipher scheme is perfectly secret by *Lemma 2.2*.
>
>*(b)*
>The largest plaintext space ${S}$ that is perfectly secret is ${S = \{A,B,C,...Z\}}$, or the set of all singular, distinct letters. Each letter is mapped with a random permutation chosen uniformly from ${26!}$ permutations, so getting any ciphertext of a letter has an equal chance of being mapped from any of the 26 letters of plaintext. If you have more than one letter, than the same substitution is reused and patterns could be exploited.
>
>*(c)*
>**Theorem.** Given a plaintext message of length ${n}$, we can achieve perfect secrecy with a Vigenère cipher.
>*Proof:*
>We can generate a random key ${k \in K}$ where ${k = (k_1k_2 ...k_n)}$, and each ${k_i}$ is chosen at uniform random from the set ${S = \{0,1,...,25\}}$ representing the letters ${A-Z}$.
>Let ${m = (m_1m_2 ...m_n) \in M}$ be the plaintext message.
>We define encryption as
>$${c_i = (m_i + k_i) \text{ mod } 26 \;\forall\; i = 0,1,...,25}$$
> where ${c = (c_1c_2 ...c_n)}$
> We thus can say
> $${k_i = (c_i-m_i) \text{ mod } 26 \;\forall\;i = 0,1,...,25}$$
> 
> We know that ${Pr[M=m |C = c] = Pr[K=c-m]}$, and since the key is uniformly picked, ${Pr[K=c-m] = \frac{1}{26^n}}$.
> We can calculate ${Pr[C=c] = \sum\limits_{m \in M} Pr[C=c|M=m]\cdot Pr[M=m] = \sum\limits_{m \in M}\frac{1}{26}\cdot\frac{1}{26^n} = \frac{1}{26^n}}$.
> Thus, ${Pr[M=m |C=c] = Pr[M=m]}$, and the scheme is perfectly secret by *Lemma 2.2*. 
___

>[!question] 2.5
>Prove or refute: Every encryption scheme for which the size of the key space equals the size of the message space, and for which the key is chosen uniformly from the key space, is perfectly secret.

>[!check]- Answer
>False
>*Proof:*
>Let ${K}$ be a keyspace and let ${M}$ be the message space where ${K,M = \{00,11\}}$, with ${0,1,...25}$ representing the letters ${A}$ through ${Z}$.
>Take the possible ciphertext ${c' = 22}$. The corresponding plaintext ${m' \in M}$ must be ${11}$ (or in other words, ${\text{Pr}[M=m'|C=c'] = 1}$, but ${\text{Pr}[M=m'] = 0.5}$.
>Since ${Pr[M=m'|C=c'] = 1 \neq \text{Pr}[M=m'] = 0.5}$, the encryption scheme can't be secret.
>
___

>[!question] 2.6
>Prove that if an encryption scheme (Gen, Enc, Dec) is perfectly secret for
a message space ${M}$ assuming all messages in ${M}$ are assigned non-zero probability, then it is perfectly secret for any message space ${M' \subset M}$.
Hint: Use Shannon’s theorem.

>[!check]- Answer
>*Proof:*
>Shannon's theorem tells us that if an encryption scheme for ${M}$ is perfectly secret, then ${Pr[M=m|C=c] = Pr[M=m]\;\forall\;m \in M}$. Since ${M' \subset M}$, ${Pr[M=m|C=c] = Pr[M=m]\;\forall\;m \in M' \subset M}$, so the encryption scheme for message space ${M'}$ is also perfectly secret.

___

>[!question] 2.7
Prove the first direction of Proposition 2.5. That is, prove that Definition 2.1 implies Definition 2.4.
Hint: Use Exercise 2.6 to argue that perfect secrecy holds for the uniform
distribution over any two plaintexts (and in particular, the two messages
output by A in the experiment). Then apply Lemma 2.3.

>[!check]- Answer
>Assume ${\text{Pr}[M=m|C=c]  = \text{Pr}[M=m]}$. Then ${\text{Pr}[M=m_0|C=c] = \text{Pr}[M=m_0]}$ and ${\text{Pr}[M=m_1|C=c] = \text{Pr}[M=m_1]}$, where ${c \leftarrow \text{Enc}_k(m_b)}$.

___

>[!question] 2.8
>Prove the second direction of Proposition 2.5. That is, prove that Defi-
nition 2.4 implies Definition 2.1.
Hint: If a scheme Π is not perfectly secret with respect to Definition 2.1,
then Lemma 2.3 shows that there exist messages m0, m1 ∈ M and c ∈ C
for which ${\text{Pr}[C = c | M = m_0]}$ 6 = Pr[C = c | M = m1]. Use these m0
and m1 to construct an A for which Pr[PrivKeav
A,Π = 1] > 1

___

>[!question] 2.9
>Consider the following definition of perfect secrecy for the encryption of *two* messages. An encryption scheme (Gen, Enc, Dec) over a message space ${M}$ is perfectly-secret for two messages if for all distributions over ${M}$, all ${m, m' \in M}$, and all ${c, c' \in C}$ with ${\text{Pr}[C = c \wedge C' = c] > 0}$:
>$${\text{Pr}[M = m \wedge M' = m' | C = c \wedge C' = c'] = \text{Pr}[M = m \wedge M' = m'],}$$
>where ${m}$ and ${m'}$ are sampled independently from the same distribution over M. Prove that no encryption scheme satisfies this definition.
>Hint: Take ${m \neq m'}$ but ${c = c'}$.

>[!check]- Answer
>*Proof:*
>Assume ${m \neq m'}$ and ${c = c'}$. Then ${\text{Pr}[M=m \wedge M' = m' | C = c \wedge C' = c'] = 0}$ since ${c = c'}$, so ${C=c \wedge C'=c'}$ is always equal to ${0}$.
>However, since ${m \neq m'}$, ${\text{Pr}[M=m \wedge M' = m'] > 0}$.
>${\text{Pr}[M=m \wedge M' = m' | C = c \wedge C' = c'] \neq \text{Pr}[M=m \wedge M' = m']}$, a contradiction.

___

>[!question] 2.10
>Consider the following definition of perfect secrecy for the encryption
of two messages. Encryption scheme (Gen, Enc, Dec) over a message
space M is perfectly-secret for two messages if for all distributions over
M, all m, m′ ∈ M with m 6 = m′, and all c, c′ ∈ C with c 6 = c′ and
Pr[C = c ∧ C′ = c] > 0:
Pr[M = m ∧ M ′ = m′ | C = c ∧ C′ = c′]
= Pr[M = m ∧ M ′ = m′ | M 6 = M ′],
where m and m′ are sampled independently from the same distribution over M. Show an encryption scheme that provably satisfies this definition. How long are the keys compared to the length of a message?

>[!question] 2.11
>Say we require only that an encryption scheme (Gen, Enc, Dec) over a
message space M satisfy the following: for all m ∈ M, the probability
that Deck (Enck (m)) = m is at least 2−t. (This probability is taken over
choice of k as well as any randomness that may be used during encryp-
tion or decryption.) Show that perfect secrecy (as in Definition 2.1) can
be achieved with |K| < |M|.

>[!question] 2.12
>Prove an analogue of Theorem 2.7 for the case of “almost perfect” se-
crecy. That is, let ε < 1 be a constant and say we only require that for
any distribution over M, any m ∈ M, and any c ∈ C;
| Pr[M = m | C = c] − Pr[M = m]| < ε.
Prove a lower bound on the size of the key space K relative to M for
any encryption scheme that meets this definition.
Hint: Consider the uniform distribution over M and fix a ciphertext c.
Then show that for a (1 − ε) fraction of the messages m ∈ M, there must
exist a key mapping m to c.