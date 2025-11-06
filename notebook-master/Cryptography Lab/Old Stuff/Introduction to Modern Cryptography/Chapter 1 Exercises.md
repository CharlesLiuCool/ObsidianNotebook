---
tags: Cryptography
date: 5/25/2025
---

___

>[!question] 1.1
>Decrypt the ciphertext provided at the end of the section on mono-alphabetic substitution.
>
>
>JGRMQOYGHMVBJWRWQFPWHGFFDQGFPFZRKBEEBJIZQQOCIBZKLFAFGQVFZFWWEOGWOPFGFHWOLPHLRLOLFDMFGQWBLWBWQOLKFWBYLBLYLFSFLJGRMQBOLWJVFPFWQVHQWFFPQOQVFPQOCFPOGFWFJIGFQVHLHLROQVFGWJVFPFOLFHGQVQVFILEOGQILHQFQGIQVVOSFAFGBWQVHQWIJVWJVFPFWHGFIWIHZZRQGBABHZQOCGFHX

>[!check]- Answer
>CRYPTOGRAPHICSYSTEMSAREEXTREMELYDIFFICULTTOBUILDNEVERTHELESSF
ORSOMEREASONMANYNONEXPERTSINSISTONDESIGNINGNEWENCRYPTIONSCHEMESTHATSEEMTOTHEMTOBEMORESECURETHANANYOTHERSCHEMEONEARTHTHEUNFORTUNATETRUTHHOWEVERISTHATSUCHSCHEMESAREUSUALLYTRIVIALTOBREAK

___

>[!question] 1.2
>Provide a formal definition of the Gen, Enc, and Dec algorithms for both the mono-alphabetic substitution and Vigenère ciphers.

>[!check]- Answers
>*Mono-alphabetic Substitution:*
>`Gen`
>Let ${\pi: \Bbb{Z}_{26} \to \Bbb{Z}_{26}}$ where ${\pi}$ is bijective, and let the letters in the alphabet follow the following correspondence
>$${\{A=0,B=1,C=2,...,Z=25\}}$$
>For encryption, we can take arbitrary ${k \in \pi}$ as our key.
>`Enc`
>Let ${m = m_1m_2 ...m_l}$ be our plaintext message.
>Let ${c}$ be our ciphertext, with ${c_i}$ denoting the ${i}$th letter in the ciphertext.
>${c = \text{Enc}_k(m) := k(m_1)k(m_2)...k(m_l)}$
>`Dec`
>As ${k}$ is bijective, we can find its inverse map, ${k^{-1}}$, which is also bijective.
>${m = \text{Dec}_k(c) = k^{-1}(c_1)k^{-1}(c_2)...k^{-1}(c_l)}$
>
>*Vigenère Ciphers:*
>`Gen`
>We define the following correspondence
>$${\{A=0,B=1,C=2,...,Z=25\}}$$
>Choose an arbitrary key/period length, ${t}$, based on some valid probability distribution (e.g. ${\text{Pr}(t = 5+i) =2^{-i}}$). For each ${i = 0}$ to ${t-1}$, choose arbitrary ${k_i \in \{0, 1, ...,25\}}$.
>${\text{Gen}() := k_1k_2 ...k_{t-1}}$
>`Enc`
>Let ${m=m_1m_2 ...m_l}$ be our plaintext message.
>${c_i := (m_i + k_{i \text{ mod } t}) \text{ mod } 26}$
>`Dec`
>${m_i := (c_i - k_{i \text{ mod } t}) \text{ mod } 26}$

___

>[!question] 1.3
>Consider an improved version of the Vigenère cipher, where instead of using multiple shift ciphers, multiple mono-alphabetic substitution ciphers are used. That is, the key consists of ${t}$ random permutations of the alphabet, and the plaintext characters in positions ${i}$, ${t + i}$, ${2t + i}$, and so on are encrypted using the ${i}$th permutation. Show how to break this version of the cipher.

>[!check]- Answer
>Use index of coincidence with various ${t}$, if its closer to ${0.065}$ then its probably right, and if its closer to ${0.038}$ its probably not.
>
>After obtaining ${t}$, run frequency analysis on the characters in position ${nt + i}$, ${n \in \Bbb{N}, nt + i < l}$.

___

>[!question] 1.4
>In an attempt to prevent Kasiski’s attack on the Vigenère cipher, the following modification has been proposed. Given the period t of the cipher, the plaintext is broken up into blocks of size ${t}$. Recall that within each block, the Vigenère cipher works by encrypting the ith character with the ${i}$th key (using a basic cipher). Letting the key be ${k_1, . . . , k_t}$, this means the ith character in each block is encrypted by adding ${k_i}$ to it, modulo ${26}$. The proposed modification is to encrypt the ${i}$th character in the ${j}$th block by adding ${k_i + j}$ modulo 26.
(a) Show that decryption can be carried out.
(b) Describe the effect of the above modification on Kasiski’s attack.
(c) Devise an alternate attack that works better than Kasiski’s attack.

>[!check]- Answer
>a) ${m_i := (c_i - k_i-j) \text{ mod }26}$
>b) This means Kasiski's method is way less effective, or needs an extremely large keyspace. Repeat sequences become a lot less likely as each block has the same ${j}$ shift only when they are ${25}$  blocks away from each other.
>c) If the period ${t}$ is known (or some close value is known), subtract predicted ${j}$ from ${j}$th block and run Kasiski's. You could also consider using index of coincidence on various ${t}$ after subtracting the ${j}$ shift.
___

>[!question] 1.5
>Show that the shift, substitution, and Vigenère ciphers are all trivial to
break using a known-plaintext attack. (Assuming normal English text
is being encrypted in each case). How much known plaintext is needed
to completely recover the key for each of the ciphers (without resorting
to any statistics)?

>[!check]- Answer
>*Caesar's/Shift Cipher*
>One character is sufficient to find the shift for Caesar's or shift cipher and recover the key. This is trivial, as you simply subtract the plaintext from the ciphertext.
>*Substitution Cipher*
>Each distinct letter in the alphabet (total of 25, last letter can be implied) is required to recover the full key (a bijective map from ${\Bbb{Z}_{26} \to \Bbb{Z}_{26}}$). This is trivial to find given the plaintext, as you simply record the mapping from the letter in the plaintext to the letter in the ciphertext, and imply the final one if its not present based on the last missing map.
>*Vigenère Cipher*
>The amount of letters of the key is required in the known-plaintext attack to recover the full key (a string of letters). For each letter in the plaintext, subtract it from the matching letter in the ciphertext and repeat until you have the whole key.

___

>[!question] 1.6
>Show that the shift, substitution, and Vigenère ciphers are all trivial
to break using a chosen-plaintext attack. How much plaintext must
be encrypted in order for the adversary to completely recover the key?
Compare to the previous question.

>[!check]- Answer
>*Shift Cipher*
>Only one character is needed to be encrypted to recover the key.
>*Substitution Cipher*
>${25}$ distinct letters are required.
>*Vigenère Cipher*
>The amount of letters in the key at a minimum is required, 2 times the amount for verification of periodicity.
>*Compare*
>Chosen-plaintext is more powerful than known-plaintext attack because you can craft a message that exposes the structure of a cipher. For instance, for substitution cipher, ${25}$ distinct letters are required which may be difficult in known-plaintext, but is easy to construct in chosen-plaintext.

___