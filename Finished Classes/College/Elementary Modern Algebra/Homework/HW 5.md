**Charles Liu**
Elementary Modern Algebra - Dr. Ben Clark
March 5th, 2025

___

1. Let ${|a| = 30}$. How many left cosets of ${\langle a^4 \rangle}$ in ${\langle a \rangle}$ are there? List them.  

**Theorem.** There are two left cosets of ${\langle a^4 \rangle}$ in ${\langle a \rangle}$ where ${|a| = 30}$.
*Proof:*
By Lagrange's Theorem, we know that the number of left cosets of ${\langle a^4 \rangle}$ in ${\langle a \rangle}$ is ${\frac{|\langle a^4 \rangle|}{|\langle a \rangle}|}$

We know that ${|\langle a \rangle| = 30}$.
We can solve that ${|\langle a^4 \rangle| = \frac{30}{\text{gcd}(30,4)} = 15}$

Thus, we can find that there are ${\frac{30}{15} = 2}$ left cosets.

The two cosets are:
${\langle a^4 \rangle}$
${a \langle a^4 \rangle}$

___

2. What is the order of the element ${14 + \langle 8 \rangle}$ in the factor group ${\Bbb{Z}_{24}/\langle 8 \rangle }$?  

**Theorem.** The order of the element ${14 + \langle 8 \rangle}$ in the factor group ${\Bbb{Z}_{24}/\langle 8 \rangle }$ is ${4}$
*Proof:*
In the factor group, ${14 + \langle 8 \rangle \equiv 6 + \langle 8 \rangle}$.

We want to solve the smallest number ${n \in \Bbb{N}}$ where ${n (6 + \langle 8 \rangle) = 0 + \langle 8 \rangle}$

We find this number is ${n = \frac{\text{lcm}(6,8)}{6} = \frac{24}{6} = 4}$.

Thus, the order is ${4}$.

___

3. Let ${G}$ be a group with ${|G| = pq}$, where ${p}$ and ${q}$ are prime. Prove that every proper subgroup of ${G}$ is cyclic. 

*Lemma 1.* Every group of prime order is cyclic.
Let ${G}$ be a group with prime order ${p}$.
By Lagrange's Theorem, for ${g \in G}$, ${|g| \,|\, p}$ or ${|g| \,|\, 1}$. 
Take ${a \in G}$ such that ${a \neq e}$. We know that ${|\langle a \rangle| = p}$ since ${a}$ is not the identity element. 
Since ${\langle a \rangle \in G}$ and ${|\langle a \rangle| = |G| = p}$, ${|\langle a \rangle| = G}$, so ${G}$ must be cyclic.

**Theorem.** For a group ${G}$ with ${|G| = pq}$ where ${p}$ and ${q}$ are prime, every proper subgroup of ${G}$ is cyclic.
*Proof:*
By Lagrange's Theorem, for ${H \le G}$, ${|H| \,|\, pq}$. However, ${H \neq G}$ as ${H}$ is a proper subgroup so ${|H| \neq pq}$. This means either ${|H| = 1}$, ${|H| = p}$, or ${|H| = q}$.

*Case 1:* ${|H| = 1}$
If ${|H| = 1}$, ${H = \{e\}}$ and is thus cyclic.

*Case 2:* ${|H| = p}$ or ${|H| = q}$
If ${|H| = p}$ or ${|H| = q}$, is cyclic by *Lemma 1*.

Thus, all proper subgroups of ${G}$ are cyclic.

___

4. The group ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle}$ is isomorphic to one of ${\Bbb{Z}_8}$, ${ \Bbb{Z}_4 + \Bbb{Z}_2}$ or ${\Bbb{Z}_2 + \Bbb{Z}_2 + \Bbb{Z}_2}$. Determine which one by eliminating the other two.  

**Theorem.** ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle \cong \Bbb{Z}_4 + \Bbb{Z}_2}$
*Proof:*
The order of quotient group ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle}$ is ${\frac{|\Bbb{Z}_4 + \Bbb{Z}_{12}|}{|\langle(2, 2)\rangle|} = \frac{48}{6} = 8}$, so by *Fundamental Theorem of Finite Commutative Groups*,  ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle}$ must be isomorphic to to one of ${\Bbb{Z}_8}$, ${ \Bbb{Z}_4 + \Bbb{Z}_2}$ or ${\Bbb{Z}_2 + \Bbb{Z}_2 + \Bbb{Z}_2}$.

*Eliminate:* ${\Bbb{Z}_2+ \Bbb{Z}_2 + \Bbb{Z}_2}$
We notice that the maximum order of elements in ${\Bbb{Z}_2+ \Bbb{Z}_2 + \Bbb{Z}_2}$ is ${\text{lcm}(2,2,2) = 2}$. However, we can take ${(0,3) \in \Bbb{Z}_4 + \Bbb{Z}_{12}}$.

Let ${H = \langle (2,2) \rangle = \{(0,0), (2,2) (0,4), (2,6), (0,8), (2,10)\}}$.
We solve that the order of ${(0,3) + H}$ is ${4}$ by doing the following:
${(0,3) + H \neq H}$
${(0,6) + H \neq H}$
${(0,9) + H \neq H}$
${(0,0) + H = H}$

Since an element of order ${4}$ exists in ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle}$ but there isn't one in ${\Bbb{Z}_2+ \Bbb{Z}_2 + \Bbb{Z}_2}$, the two can't be isomorphic.

*Eliminate:* ${\Bbb{Z}_8}$
We want to show that in ${\Bbb{Z}_8}$ there are only ${2}$ elements of order ${4}$. 

An element of order ${4}$ in ${\Bbb{Z}_8}$ is ${\langle \frac{8}{4} \rangle = \langle 2 \rangle}$

We want to find any other ${m \in \Bbb{Z}_8}$ of order ${4}$. In other words, we want to find ${m}$ where ${\langle m \rangle = \langle 2 \rangle}$.

The only elements that work are elements where ${\gcd(m,8) = 2}$, which can also be expressed as ${\gcd(\frac{m}{2}, 4) = 1}$.

The only numbers coprime with ${4}$ and less than it are ${1}$ and ${3}$, so ${\frac{m}{2} = 1,3}$ and ${m = 2,6}$.

Thus, we find that there are two elements in ${\Bbb{Z}_8}$ with order ${4}$.

However, in ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle}$, the following all have order ${4}$:
${(3,0) + H}$
${(0,3) + H}$
${(1,0) + H}$
${(0,1) + H}$

So, there must be at least ${4}$ elements of order ${4}$ in ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle}$, but there is only ${2}$ in ${\Bbb{Z}_8}$, so the two can't be isomorphic.

*Conclusion:*

Thus, ${(\Bbb{Z}_4 + \Bbb{Z}_{12})/\langle(2, 2)\rangle \cong \Bbb{Z}_4 + \Bbb{Z}_2}$.
___

5. Prove that a quotient group of a commutative group is commutative.

**Theorem.** The quotient group of a commutative group is commutative.
*Proof:*
Let ${G}$ be a commutative group and ${H \le G}$.
For ${a,b \in G}$, the group operation of quotient group is
$${(aH)(bH) = (ab)H}$$

Since ${G}$ is commutative, we can see that
$${(aH)(bH) = (ab)H = (ba)H = (bH)(aH)}$$
so the quotient group ${G / H}$ is commutative.

___