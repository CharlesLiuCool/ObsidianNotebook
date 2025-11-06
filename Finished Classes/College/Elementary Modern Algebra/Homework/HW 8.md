**Charles Liu**
Elementary Modern Algebra - Dr. Ben Clark
April 8th, 2025

___

1. Is the mapping from ${\Bbb{Z}_{10}}$ to ${\Bbb{Z}_{10}}$ given by ${x → 2x}$ a ring homomorphism?  

**Theorem.** ${\Bbb{Z}_{10}}$ to ${\Bbb{Z}_{10}}$ given by ${x → 2x}$ is not a ring homomorphism.
*Proof:*

${\phi: \Bbb{Z}_{10} \to \Bbb{Z}_{10}}$
${\phi(x) = 2x}$

Consider ${3, 4 \in \Bbb{Z}_{10}}$
${\phi(3 \cdot 4) = \phi(12) = 2 \neq \phi(3)\phi(4) = 6 \cdot 8 \text{ mod } 10 = 48 \text{ mod } 10 = 8}$
___

2. Let  

${\Bbb{Z}[\sqrt{2}] = \{a + b\sqrt{2}\,|\,a, b \in \Bbb{Z}\}}$ and ${H =  \left\{ \begin{bmatrix} a & 2b \\ b & a  \end{bmatrix} \,|\, a, b ∈ \Bbb{Z} \right\}}$  

Show that ${\Bbb{Z}[\sqrt{2}]}$ and ${H}$ are isomorphic as rings.

**Theorem.** ${\Bbb{Z}[\sqrt{2}]}$ and ${H}$ are isomorphic as rings.
*Proof:*
Consider the mapping ${\phi: \Bbb{Z}[\sqrt{2}] \to H}$ defined as ${\phi(a+b\sqrt{2}) = \begin{bmatrix} a & 2b \\ b & a  \end{bmatrix}}$ where ${a,b \in \Bbb{Z}}$.

*Ring Homomorphism*

Consider ${x,y \in \Bbb{Z}[\sqrt{2}]}$, where ${x = a_1+b_1\sqrt{2}}$ and ${y = a_2 + b_2\sqrt{2}}$.

${\phi(x+y) = \begin{bmatrix} a_1 + a_2 & 2(b_1+ b_2) \\ b_1+b_2 & a_1+a_2  \end{bmatrix} = \begin{bmatrix} a_1 & 2b_1 \\ b_1 & a_1  \end{bmatrix} + \begin{bmatrix} a_2 & 2b_2 \\ b_2 & a_2  \end{bmatrix} = \phi(x) + \phi(y)}$

${\phi(x \times y) = \phi((a_1+b_1\sqrt{2})\times(a_2+b_2\sqrt{2})) = \phi(a_1a_2+b_1b_2 + (a_1b_2+a_2b_1)\sqrt{2})}$

${= \begin{bmatrix} a_1a_2+b_1b_2 & 2(a_1b_2+a_2b_1) \\ a_1b_2+a_2b_1 & a_1a_2+b_1b_2  \end{bmatrix} = \begin{bmatrix} a_1 & 2b_1 \\ b_1 & a_1  \end{bmatrix}\begin{bmatrix} a_2 & 2b_2 \\ b_2 & a_2  \end{bmatrix} = \phi(x) \phi(y)}$

*Bijective*

Assume ${\phi(x) = \phi(y)}$. This means ${\begin{bmatrix} a_1 & 2b_1 \\ b_1 & a_1  \end{bmatrix} = \begin{bmatrix} a_2 & 2b_2 \\ b_2 & a_2  \end{bmatrix}}$, so ${a_1 = a_2}$ and ${b_1 = b_2}$. This also implies that ${a_1 + b_1\sqrt{2} = a_2+b_2\sqrt{2}}$, so ${x=y}$ and ${\phi}$ is one-to-one.

Consider ${h = \begin{bmatrix} a_h & 2b_h \\ b_h & a_h  \end{bmatrix} \in H}$. We can find ${x \in \Bbb{Z}[\sqrt{2}]}$ where ${\phi(x) = y}$ is ${a_h+b_h\sqrt{2}}$, so ${h}$ is onto.

Since there exists a mapping ${\phi}$ between ${\Bbb{Z}[\sqrt{2}]}$ and ${H}$ that is both bijective and ring homomorphic, and thus isomorphic, the two rings ${\Bbb{Z}[\sqrt{2}]}$ and ${H}$ are isomorphic as rings.

___

3. Determine all the ring isomorphisms from ${\Bbb{Z}_n}$ to itself.  

**Theorem.** ${\phi(x)=x}$ represents all ring isomorphisms from ${\Bbb{Z}_n}$ to itself.
*Proof:*
We first find all the generators of the group ${\Bbb{Z}_n}$. ${1}$ is the standard generator.
Any number ${a}$ where ${\gcd(a,n) = 1}$ is also a generator.
Any ring isomorphism on cyclic groups has the property that generators map to generators. So, ${\phi(1) = a}$.
We then produce a mapping, ${\phi(x) = ax}$.

To make an isomorphism, we need to prove ring homomorphism and bijectiveness.
*Ring Homomorphism:*
${\phi(x + y) = a(x+y) = ax + ay = \phi(x) + \phi(y)}$
${\phi(x y) = a(xy) = \phi(x)\phi(y) = axay = a^2xy}$
From preserving homomorphism with multiplication, we see that we need ${a^2 \text{ mod } n = a \text{ mod } n}$. The only element that works for this is ${a = 1}$
*Bijectiveness*
*1-1*
Assume ${\phi(x) = \phi(y)}$. This means ${ax = ay}$, and ${x=y}$. So ${\phi}$ is one-to-one.
*Onto*
Take ${y \in \Bbb{Z}_n}$. Since the generator ${a}$ produces all elements in ${\Bbb{Z}_n}$, we can always find some ${k \in \Bbb{Z}_n}$ where ${ka = y}$. So ${\phi}$ is onto.

So,  ${\phi(x) = x}$ represents all ring isomorphisms of ${\Bbb{Z}_n}$ to itself.
___

4. Let ${n}$ be a positive integer. Show that there is a ring isomorphism from ${\Bbb{Z}_2}$ to a subring of ${\Bbb{Z}_{2n}}$ if and only if ${n}$ is odd.  

**Theorem.** There is a ring isomorphism from ${\Bbb{Z}_2}$ to a subring of ${\Bbb{Z}_{2n}}$ if and only if ${n}$ is odd.
*Proof:*
"${\Rightarrow}$"
Assume ${n}$ is odd.
We can take the subring ${\Bbb{Z_2} \to \Bbb{Z_2}}$
Take ${\phi: \Bbb{Z}_2 \to \Bbb{Z}_{2}}$, where ${\phi(x) = x}$.
${\phi}$ is a *ring homomorphism*.
Consider ${x,y \in \Bbb{Z}_2}$
${\phi(x+y) = x + y = \phi(x) + \phi(y)}$
${\phi(xy) = x y = \phi(x) \phi(y)}$
${\phi}$ is *bijective*.
Assume ${\phi(x) = \phi(y)}$. This means ${x=y}$, so ${\phi}$ is one-to-one.
Take ${y\in\Bbb{Z}_2}$. We can always find ${x = y\in \Bbb{Z}_2}$ where ${\phi(x) = y}$. So ${\phi}$ is onto.
Thus, ${\phi}$ is a *ring isomorphism* when ${n}$ is odd, and there doest exist a ring isomorphism from ${\Bbb{Z}_2}$ to ${\Bbb{Z}_{2n}}$.

"${\Leftarrow}$"
Assume there exists an isomorphism from ${\Bbb{Z}_2}$ to a subring of ${\Bbb{Z}_{2n}}$
By way of contradiction, assume ${n}$ is even. Lets denote ${n = 2k}$.
Then we would need a ring isomorphism from ${\Bbb{Z}_2}$ to ${\Bbb{Z}_{4k}}$.
However, we can't take a subring from ${\Bbb{Z}_{4k}}$ of order ${2}$, so we can never establish a ring isomorphism from ${\Bbb{Z}_2}$ to ${\Bbb{Z}_{4k}}$ as it would never be bijective.
Thus, ${n}$ must be odd.

___

5. Give that ${f}$ is a polynomial of degree ${n}$ in ${P_n}$ (vector space of polynomials of degree at most ${n}$ with real coefficients), show that ${\{f, f', f'', . . . , f^{(n)}\}}$ is a basis for ${P_n}$.  

**Theorem.**${\{f, f', f'', . . . , f^{(n)}\}}$ is a basis for ${P_n}$.
*Proof:*
Consider the polynomial ${f}$ which is order ${n}$.
By definition ${f'}$ is an order ${n-1}$ polynomial, ${f''}$ is order ${n-2}$, and ${f^{(k)}}$ is an order ${n-k}$ polynomial. 

Consider any polynomial ${g \in P^n = a_0 + a_1x + a_2x^2 + ... a_nx^n}$.
We can write ${g = c_1f + c_2f' + c_3f'' ... c_nf^{(n)}}$, as each component (${k}$th derivative of ${f}$) has a unique order spanning ${0}$ to ${n}$, so the polynomial can always be generated.

___

6. Prove that for a vector space ${V}$ over a field that does not have characteristic ${2}$, the hypothesis that ${V}$ is commutative under addition is redundant (we can prove it from the other properties).

**Theorem.** For a vector space ${V}$, commutativity under addition is redundant if 
*Proof:*
Consider ${v,w \in V}$. We know that ${v+w + v + w = 2 \times (v+w) = 2v + 2w = v+v + w + w}$, as ${2(v+w) \neq 0}$, ${2v \neq 0}$, and ${2w \neq 0}$ (their is no characteristic of ${2}$).
So, ${v+w + v +w = v + v + w + w}$ and ${w + v = v + w}$.
Thus, commutative is redundant.

___