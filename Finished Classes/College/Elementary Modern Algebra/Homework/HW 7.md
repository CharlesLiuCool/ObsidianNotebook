**Charles Liu**
Elementary Modern Algebra - Dr. Ben Clark
April 2nd, 2025

___

1. Let ${R}$ be the ring of real-valued continuous functions on ${[−1, 1]}$. Show that ${R}$ has zero-divisors. Note that in this ring ${f (x) = 0}$ is the additive identity.  

**Theorem.** For a ring ${R}$ of the real-valued continuous functions on ${[-1,1]}$, ${R}$ has zero-divisors.
*Proof:*
Take two functions, ${g(x), h(x)}$.

Let ${g(x) = \begin{cases} 0 & \text{if } x \in [-1,0) \\ x & \text{if } x \in [0,1] \end{cases}}$

and ${h(x) = \begin{cases} x & \text{if } x \in [-1,0] \\ 0 & \text{if } x \in [0,1] \end{cases}}$

Since ${\lim\limits_{x \to 0^-} g(x) = 0 = \lim\limits_{x \to 0^+}g(x)}$ and ${g(x)}$ from ${[-1,0)}$ and ${[0,1]}$ are both continuous, ${g(x)}$ on ${[-1,1]}$ is continuous.

Similarly, ${h(x)}$ is continuous on ${[-1,1]}$.

Thus, ${g(x) \in R}$ and ${h(x) \in R}$.

Although ${g(x) \neq 0}$ and ${h(x) \neq 0}$, ${g(x) \cdot h(x) = 0}$, So, ${g(x)}$ and ${h(x)}$ are both zero-divisors and ${R}$ has zero divisors.

___

2. Show that the intersection of two ideals is an ideal.  

**Theorem.** The intersection of two ideals is an ideal.
*Proof:*
Let ${S_1, S_2}$ be two ideals of ring ${R}$.
Since ${S_1 \subset R}$ and ${S_2 \subset R}$, ${S_1 \cap S_2 \subset R}$.

For any given element ${s \in S_1 \cap S_2}$, it must lie in both ${S_1}$ and ${S_2}$.

Since ${s \in S_1}$, it must satisfy the definition of an ideal, that being ${rs \in S_1}$ and ${sr \in S_1}$ for any ${r \in R}$.

Similarly, since ${s \in S_2}$, it must satisfy ${rs \in S_2}$ and ${sr \in S_1}$.

Since ${rs}$ and ${sr}$ are both in ${S_1}$ and ${S_2}$, ${rs \in S_1 \cap S_2}$ and ${sr \in S_1 \cap S_2}$.

Thus, ${S_1 \cap S_2}$ is an ideal.

___

3. Show, by example, that the intersection of two prime ideals need not be a prime ideal.  

**Theorem.** The intersection of two prime ideals need not be a prime ideal.
*Proof:*
Take prime ideals ${3\Bbb{Z}}$ and ${5\Bbb{Z}}$ of ${\Bbb{Z}}$.

${3\Bbb{Z} \cap 5\Bbb{Z} = 15\Bbb{Z}}$.

We can solve that ${3\cdot 5 = 15 \in 15\Bbb{Z}}$, but ${3 \notin 15\Bbb{Z}}$ and ${5 \notin 15\Bbb{Z}}$.

From this example, we can see that the intersection of prime ideals is not necessarily a prime ideal.

___

4. Let ${I = \langle 2 \rangle}$. Prove that ${I[x]}$ is not a maximal ideal of ${\Bbb{Z}[x]}$ even though ${I}$ is a maximal ideal of ${\Bbb{Z}}$.  

**Theorem.** ${I[x]}$ where ${I = \langle 2 \rangle}$ is not a maximal ideal of ${\Bbb{Z}[x]}$
*Proof:*
Consider ${\langle 2, x \rangle}$. This is the set of all polynomials with integer coefficients where the constant term is even. We know that ${\langle 2,x \rangle \subset \Bbb{Z}[x]}$.

Given any ${a = a_0 + a_1x +...+a_kx^k \in \langle 2,x \rangle}$ and ${r = r_0 + r_1x_1 +...+r_mx^m \in \Bbb{Z}[x]}$ we know that ${a_0 \in 2\Bbb{Z}}$, ${a_0, a_1,...a_k,r_0,r_1,...r_k \in \Bbb{Z}}$ and ${k,m \in \Bbb{N}}$. 
We find that ${ra}$ and ${ar}$ must be in ${\langle 2,x \rangle}$ as ${r_0 \cdot a_0}$ must be even and all other coefficients are linear combinations of integers and must be integers.
Thus, ${\langle 2,x \rangle}$ is an ideal of ${\Bbb{Z}[x]}$.

We also know that ${I[x] \subset \langle 2,x \rangle}$ where ${I = \langle 2 \rangle}$. Given ${a \in \langle 2, x \rangle}$ as defined earlier, we can take ${a_1,a_2,...a_k = 0}$ and produce all elements in ${I[x]}$.

Thus, ${I[x]}$ cannot be a maximal ideal of ${\Bbb{Z}[x]}$.

___

5. Find the characteristic of ${\Bbb{Z}[i]/⟨2 + i⟩}$.  

**Theorem.** The characteristic of ${\Bbb{Z}[i]/⟨2 + i⟩}$ is ${5}$.
*Proof:*
We know that ${\Bbb{Z}[i]/\langle 2 + i \rangle}$ has unity ${1}$.
We want to find ${n \in \Bbb{N}}$ where when ${a+bi \in \Bbb{Z}[i]}$, ${(a+bi)(2+i) = n}$.
This means ${(2a-b + (a+2b)i) = n}$.
Since ${n}$ has no complex component as it is an integer, ${a+2b = 0}$ so ${a = -2b}$. Using substitution, we get that ${-5b = n}$. Taking ${b=-1}$, we get ${n=5}$, the minimal possible value.
Thus, the characteristic of ${\Bbb{Z}[i]/⟨2 + i⟩}$ is ${5}$.

___

6. Let ${S = \{a + bi\,|\,a, b \in \Bbb{Z}, b \text{ is even}\}}$. Show that ${S}$ is a subring of ${\Bbb{Z}[i]}$, but not an ideal of ${\Bbb{Z}[i]}$.

**Theorem.** ${S}$ is a subring of ${\Bbb{Z}[i]}$.
*Proof:*
Take ${a = 0, b = 0}$. Since ${0 \in S}$, ${S}$ is nonempty.
Since ${2\Bbb{Z} \in \Bbb{Z}}$ (the evens are a subset of all integers), ${S \subset \Bbb{Z}[i]}$.

Take ${x = a_1 + b_1i}$ and ${y = a_2 + b_2i}$ where ${a_1,a_2 \in \Bbb{Z}}$ and ${b_1,b_2 \in 2\Bbb{Z}}$. We know that ${x,y \in S}$.

We can solve that 
${\begin{align} xy &= (a_1 + b_1i)(a_2 + b_2i) \\ &= a_1a_2 +a_2b_1i + a_1b_2i - b_1b_2 \\ &= (a_1a_2-b_1b_2) + (a_2b_1+a_1b_2)i \end{align}}$

Note that since both ${b_1}$ and ${b_2}$ are even, ${a_2b_1+a_1b_2}$ is also even.
Since ${a_1a_2-b_1b_2 \in \Bbb{Z}}$ and ${a_2b_1+a_1b_2 \in 2\Bbb{Z}}$, ${xy \in S}$.

We can also solve that
${x+ y = a_1+b_1i + a_2+b_2i = (a_1+a_2) + (b_1+b_2)i}$

Note that since both ${b_1}$ and ${b_2}$ are even, ${b_1+b_2}$ is even.
Since ${a_1+a_2 \in \Bbb{Z}}$ and ${b_1+b_2 \in 2\Bbb{Z}}$, ${x + y \in S}$.

Thus, ${S}$ is a subring of ${\Bbb{Z}[i]}$.

**Theorem.** ${S}$ is not an ideal of ${\Bbb{Z}[i]}$.
*Proof:*
If ${S}$ is an ideal of ${\Bbb{Z}[i]}$, then for arbitrary elements ${s \in S}$ and ${z \in \Bbb{Z}[i]}$, ${sz \in S}$.
By definition, ${s = 1 + 2i}$ and ${z = 1 + i}$.
${sz = (1+2i)(1+i) = 1 + 2i + i -2 = -1 + 3i \notin S}$.
Thus, ${S}$ is not an ideal of ${\Bbb{Z}[i]}$.

___