---
tags: Cryptography
date: 7/5/2025
---

### **Notes**
- Need to read 9+ pages a day to finish before summer ends
- Schedule meeting with professor and ask about fully homomorphic encryption

Began log on July 5th (although started earlier)

___

**July 5th**
- Page 76 (90 in PDF)
- 3.4.3 Stream Ciphers

>*What I learned today:*
>- Semantic security is the idea that even if an attacker had external information, they couldn't learn any more than they already know.
>- They key point of pseudorandomness is that in exchange of the relaxation to computation security (i.e. security against efficient attacks), we gain the ability to secure encrypted messages of arbitrary length with short keys with the help of pseudorandom generators
>- We can reduce security of constructions to primitive assumptions
___

**July 6th**
- [x] Read to page 85 (3.6 Constructing CPA-secure encryption schemes)
- Page 85 (99 in PDF)

>*What I learned today:*
>- The purpose of setting up PrivK experiments is to rigorously/mathematical define what constitutes a break or security for things like CPA and multiple messages
>- CPA-secure <=> CPA-secure under multiple encryptions
>- Most encryption schemes must be probabilistic or else they are automatically not CPA-secure/multiple encryption secure
>- Stream cipher create arbitrary length pseudorandom streams, can use synchronized (use chunks of pseudorandom stream, extra parameters to not reuse parts) or unsynchronized (introduce random initial vector IV, usually use this) mode for security against multiple encryptions

___

**July 7th**
- [ ] Read to page 102  (End of Chapter 3)
- Page 88 (102 in PDF)

>*What I learned today:*
>- We can consider pseudorandom functions, where PPT adversaries can't distinguish between it and uniform random function.
>- Deterministic but looks probabilistic

___

**July 9th**
- [ ] Read to page 102  (End of Chapter 3)
- Page 95 (109 in PDF)

>*What I learned today:*
>- Pseudorandom permutation is an efficient keyed permutation (bijective).
>- All pseudorandom permutations are pseudorandom functions
>- Why pseudorandom permutations? Efficient inverse

___

**July 10th - 26th**

> *What I learned*
> - MACs, fixed-length, variable length, replay attacks (use something outside to prevent like time factor or tracking indices)
> - Merkle-Damgard $z_B = h_s(z_{B-1}||x_B)$, $z_i = h_s(z_{i-1}|x_i)$, $z_0 = IV$
> - HMACs, practical one: $t :=h(k_2\oplus opad || h(k_1 \oplus ipad || m))$
> - Variant HMAC used for proofs in textbook $t := H^s(k_2\oplus opad || H^s(k_1 \oplus ipad || m))$