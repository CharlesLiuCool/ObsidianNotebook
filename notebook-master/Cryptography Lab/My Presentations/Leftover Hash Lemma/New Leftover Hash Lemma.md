### **Introduction to LHL**

>**Theorem** Leftover Hash Lemma
>Given any *pairwise independent* hash family $\mathcal{H} = \{ h: \{0,1\}^n \to \{0,1\}^m \}$ where $m = k-2\log(1/\epsilon)$, then $\text{Ext}(x,h) := h(x)$ is a strong $(k,\epsilon)$-extractor. Equivalently, $\text{Ext}(x,h) = (h,h(x))$ is a standard $(k,\epsilon)$-extractor.

First clarify the terminology:

>*What is strong $(k,\epsilon)$-extractor?*
That is, for every $k$-source $X$ on $\{0,1\}^n$, $(U_d, \text{Ext}(X,U_d))$ is $\epsilon$-close to $(U_d, U_m)$.
Notice that $U_d$, the first part of the tuple, is included. This is because the extractor remains close to uniform EVEN when the seed is revealed.

>*What is a $k$-source?*
A *random variable* $X$ is a $k$-source if $H_\infty(X) \ge k$ (in other words min-entropy $\ge k$). This is equivalent to saying $\Pr[X = x] \le 2^{-k}$.

Recall this is because the definition of *min-entropy* of $X$ is
$$H_\infty(X) = \underset{x}{\min} \left\{\log \frac{1}{\Pr[X=x]}\right\}$$


*Proof of LHL:*
Let $X$ be an arbitrary $k$-source on $\{0,1\}^n$, $\mathcal{H}$ as above, and $H \overset{R}\leftarrow \mathcal{H}$. Let $d$ be the seed length. We show that $(H,H(X))$ is $\epsilon$-close to $U_d \times U_m$ in the following three steps:

1. We show that the collision probability of $(H,H(X))$ is close to that of $U_d \times U_m$.
2. We note that this is equivalent to saying that the $\ell_2$ distance between $(H,H(X))$ and $U_d \times U_m$ is small
3. Then we deduce that the statistical difference is small, by recalling that the statistical difference equals half of the $\ell_1$ distance, which can be (loosely) bounded by the $\ell_2$ distance.

*Proof of (1):*
By definition, $CP(H,H(X)) = \Pr[(H,H(X)) = (H',H'(X'))]$, where $(H', X')$ is independent of and identically distributed to $(H,X)$. Note that $(H,H(X)) = (H',H'(X))$ if and only if

1. $H=H'$
and
2. Either
	1. $X=X'$
	or
	2. $X \neq X'$ but $H(X) = H(X')$

Thus,
$$\begin{align} CP(H,H(X)) &= CP(H) \cdot (CP(X) + \Pr[H(X) = H(X')|X \neq X']) \\ & \le \frac{1}{D}\cdot(\frac{1}{K} + \frac{1}{M}) \le \frac{1 + \epsilon^2}{DM}\end{align}$$

To see the penultimate inequality, note that $CP(H) = \frac{1}{D}$ because there are $D$ hash functions, $CP(X) \le \frac{1}{K}$ because $H_\infty(X) \ge k$, and $\Pr[H(X) = H(X')|X \neq X'] \le 1/M$ by $2$-universality.

*Proof of (2):*
$$\begin{align}||(H,H(X)) - U_d \times U_m||^2 &= CP(H,H(X)) - \frac{1}{DM} \\ \\ &\le \frac{1 + \epsilon^2}{DM} -\frac{1}{DM} = \frac{\epsilon^2}{DM}\end{align}$$

*Proof of (3):*
Recalling that the statistical difference between two random variables $X$ and $Y$ is equal to $\frac{1}{2}|X-Y|_1$, we have:

$$\begin{align}\Delta((H,H(X)), U_d \times U_m) &= \frac{1}{2} \cdot |(H,H(X)) - U_d \times U_m|_1 \\ &\le \frac{\sqrt{DM}}{2} \cdot ||(H,H(X)) - U_d \times U_m || \\ &\le \frac{\sqrt{DM}}{2} \cdot \sqrt{\frac{\epsilon^2}{DM}} \\ &= \frac{\epsilon}{2}\end{align}$$

Thus, we have in fact obtained  a strong $(k, \epsilon/2)$-extractor.
___

### **Discrete Gaussians Modulo Sub-Lattices: New LHLs for Discrete Gaussians**

![[Leftover Hash Lemma 2025-09-07 22.07.45.excalidraw|700 |center]]


#### **Main Questions**

1. Can we derive a leftover hash lemma for the discrete Gaussian over lattices without the dependency of $\sigma \ge \eta_{\epsilon}(\Lambda^\perp(A))$ or $\sigma \ge \eta_{\epsilon}(\Lambda^\perp (a))$? Those bounds are awkward since they depend on matrices specific lattice instance!
2. Can the leftover hash lemma arbitrarily bound leakage?

#### **Contributions**

>**Overview**
>*Old Leftover Hash Lemmas*:
>- $\sigma \ge \eta(\Lambda^{\perp}(A))$, standard deviation must be big enough or Gaussian is too spiky
>
>*New Leftover Hash Lemma*
>- $\sigma < \frac{q}{\sqrt{\log n}}$, standard deviation must not be too big so the cosets don't overlap too much


>**Theorem** Let $\Lambda, \Lambda'$ be $n$-dimensional full-rank lattices such that $\Lambda' \subseteq \Lambda$. Let $\epsilon \in (0,1)$, $\sum \in \Bbb{R}^{n \times n}$ be a positive definite matrix, and $c \in \Bbb{R}^n$ be any center. Let $S_{\Lambda/\Lambda'}$ be a set with size $\frac{\det \Lambda '}{\det \Lambda}$ which comprises any group of coset representatives of the quotient group $\Lambda / \Lambda'$. Define the random variable $S := D_{\Lambda, \sqrt{\sum},c} \mod \Lambda'$
>
>*Approach 1:*
>$$2^{H_\infty(D_{\Lambda,\sqrt{\Sigma},c} \bmod \Lambda')} \ge \begin{cases} \rho_{\sqrt{\Sigma}}(c') \cdot \sum\limits_{x \in S_{\Lambda/\Lambda'}}\rho_\sqrt{\Sigma}(x) & \text{ if  }\sqrt{\Sigma} > 0 \\ \frac{1-\epsilon}{1 + \epsilon} \cdot \sum\limits_{x \in S_{\Lambda/\Lambda'}} \rho_{\sqrt{\Sigma}}(x) & \text{ if } \sqrt{\Sigma} \ge \eta_\epsilon(\Lambda)\end{cases}$$
>where $c ' = c \bmod \Lambda$
>
>*Approach 2:*
>$$H_\infty(S) \ge \begin{cases} \log(\frac{\det \Lambda'}{\det\Lambda}) - \log(\frac{1+\epsilon}{1 - \epsilon}) & \text{ if } \sqrt{\Sigma} \ge \eta_\epsilon(\Lambda ')\\  \log(\frac{\det \Lambda'}{\det \Lambda}) - \eta \log(\eta_\epsilon(\sqrt{\Sigma}^{-1}\Lambda')) & \text{ if } \eta_\epsilon(\Lambda) \le \sqrt{\Sigma} < \eta_\epsilon(\Lambda')\end{cases}$$

First show two smaller theorems

>**Theorem** LHL for Discrete Gaussian over Integer Lattice
Let $q = q_1q_2$ be the product of two primes, $A \overset{\$}{\leftarrow} \Bbb{Z}_q^{n\times m}$ and $x \in D_{\Bbb{Z}^m, \sigma} \bmod q$ with Gaussian parameter $\sigma \le \frac{\sqrt{\pi}}{2} \cdot \frac{\min \{q_1,q_2\}}{\sqrt{\ln (4m)}}$ and $m \log \sigma \ge 2 \log (1/\epsilon) + n\log q$, then 
$$\Delta \left((A,A \cdot x), (U(\Bbb{Z}_q^{n\times m} \times \Bbb{Z}^n))\right) \le \epsilon$$

![[Leftover Hash Lemma 2025-09-08 21.24.56.excalidraw|700|center]]

>**Lemma 1.2** Ideal Lattice
Let $R$ be a ring of integers with degree $N$, $q$ be a prime number and $\mathfrak{q}$ be an ideal factor of $qR$ with norm $\mathcal{N}(q) = q^t$, $S := D_{R,\sigma}^\text{coeff} \bmod q$ be the Gaussian distribution over coefficient lattice of $R$ modulo $q$ and $\sigma \le \frac{\sqrt{\pi}}{2} \cdot \frac{q}{\sqrt{\ln(4t)}}$. Then we have $H_\infty(S) \ge t\log \sigma - 1$

In other words, we can lower bound the min-entropy of a discrete Gaussian over a coefficient lattice of $R$ under modulo prime $q$ with a value related to the upperbound of the standard deviation.

>**Theorem 1.4** LHL for Discrete Gaussian over Ideal Lattices
Let $R$ be $M$-th cyclotomic ring of integers with degree $N = \varphi(M)$, $q$ be a prime number, $qR = \mathfrak{q}_1^e\mathfrak{q}_2^e...\mathfrak{q}_g^e$ be the ideal factorization of $qR$ such that $\mathcal{N}(\mathfrak{q}_i) = q^f$ and $N = efg$. Let $S = (D_{R, \sigma}^\text{coeff})^m$ be the discrete Gaussian over the coefficients with parameter $\sigma \le \frac{\sqrt{\pi}}{2}\cdot\frac{q}{\sqrt{\ln(4m)}}$ and $mf\log\sigma \ge 2\log(1+\epsilon) + nf \log q + \log g + m$. Then we have
$$\Delta((A,A \cdot x), U(R^{n \times m}\times R^n)) \le \epsilon, \text{ where }A \overset{\$}\leftarrow R^{n\times m}_q \text{ and } x \in S$$

___

### **Calculating Min-Entropy of Discrete Gaussian Modulo Sub-Lattice**

Let $\Lambda$ and $\Lambda'$ be full-rank lattices in $\Bbb{R}^n$ such that $\Lambda$' is a sub-lattice of $\Lambda$.

*Goal:* Find explicit lower bound for the min-entropy of the modular distribution $\mathcal{X} = (D_{\Lambda,\Sigma,c} \bmod \Lambda')$ for some specific but commonly used lattices $\Lambda$ and $\Lambda$', such as:
$$\Lambda = \Bbb{Z}^n \text{ and } \Lambda' = q\Bbb{Z}^n$$
for some modulus $q$, or
$$\Lambda = \mathcal{O}_K \text{ and } \Lambda' = q$$
for some number field $K$ and its $\mathcal{O}_K$- ideal $\mathfrak{q}$.

*First Approach*

Start with $\Sigma = \sigma^2I_n$ and $c = 0^n$ for some spherical gaussian with parameter $\sigma > 0$.

![[New Leftover Hash Lemma 2025-09-11 09.34.12.excalidraw|200]]

Let $S_{\Lambda/\Lambda'}$ be any set of coset representatives of the quotient group $\Lambda/\Lambda' = \Lambda \bmod \Lambda'$
. From the definition of min-entropy, we have
$$\begin{align} 2^{H_\infty(D_{\Lambda,\sigma}\bmod\Lambda')} &= \frac{\rho_\sigma(\Lambda)}{\max\limits_{x \in \Lambda} \rho_\sigma (\Lambda' + x)} \ge \frac{\rho_\sigma (\Lambda)}{\rho_\sigma(\Lambda')} \\ & =\sum\limits_{x \in S_{\Lambda/\Lambda'}} \frac{\rho_\sigma (\Lambda' + X)}{\rho_\sigma(\Lambda')} \ge \sum\limits_{x \in S_{\Lambda/\Lambda'}}\rho_\sigma(x)\end{align}$$

This uses $\rho_\sigma(\mathcal{L} + \mathcal{v}) \le \rho_\sigma(\mathcal{L})$ for all full-rank lattice $\mathcal{L}$ and vector $v \in \Bbb{R}^n$.

For a single coset $v + \Lambda' \in \Lambda/\Lambda'$, the representative element $x$ of $v + \Lambda' \in \Lambda/\Lambda'$ is not unique, and we wish its norm to be as small as possible in order to make the Gaussian $\rho_\sigma(x)$ reach its maximum among $x \in v + \Lambda'$ (coset representatives).

Recall $\rho_\sigma(x) := \text{exp}(-\pi\frac{||x||^2}{\sigma^2})$, so as $||x||$ is minimized, $\rho_\sigma(x)$ is maximized

Hence our goal can be reduced to
1. Finding a low-norm representative of each coset in the quotient group $\Lambda/\Lambda'$
2. Estimating a lower bound of $\rho_\sigma(S_{\Lambda/\Lambda'})$.

![[New Leftover Hash Lemma 2025-09-11 10.18.25.excalidraw| center | 400]]

For a simple case $\Lambda = \Bbb{Z}^n$ and $\Lambda' = q\Bbb{Z}^n$, a trivial quotient group is exactly $\Bbb{Z}_q^n$ where $\Bbb{Z}_q = (-q/2, q/2] \cap \Bbb{Z}$, indicating that $\Bbb{Z}_q^n$ can be represented by the intersection of an infinity-norm ball with radius $q/2$ and trivial lattice $\Bbb{Z}^n$

The notation $\Bbb{Z}_q = (-q/2, q/2] \cap \Bbb{Z}$ means all integers lying in that interval, or
$$\Bbb{Z}_q = \{-\lfloor q/2 \rfloor,...,\lfloor(q-1)/2\rfloor\}$$
or just recentering $\Bbb{Z}_q$ around $0$.

From the tail bound by Banaszczyk and Poisson summation formula, if $\sigma < q/\sqrt{\log n}$, we have
$$\rho_\sigma (\Bbb{Z}^n_q) \approx \rho_\sigma(\Bbb{Z}^n) = \sigma^n\cdot\rho_{1/\sigma}(\Bbb{Z}^n) = \sigma^n(1+\rho_{1/\sigma}(\Bbb{Z}^n/\{0\})) > \sigma^n$$

Taking the $\log$, we can see that $$n\log\sigma$$ can be a lower bound for $H_\infty(D_{\Bbb{Z}^n, \sigma} \bmod q)$

Next, consider the case of ideal lattices, i.e. $\Lambda = R$ and $\Lambda' = \mathcal{I}$, where $R = \mathcal{O}_K$ is the ring of integers of a number field $K = \Bbb{Q}[\zeta]$, and $\mathcal{I}$ is an $R$-ideal.
We need to identify a proper structure of $R/\mathcal{I}$ for general $R$ and $\mathcal{I}$. If $\mathcal{I}$ is a prime ideal factor of $qR$ with norm $\mathcal{N}(\mathcal{I}) = q^f$ where $q$ is a prime number, then $\mathcal{I}$ is generated by two elements.
If $\mathcal{I}$ is a prime ideal factor of $qR$ with norm $N(\mathcal{I}) = q^f$ where $q$ is a prime number, then $\mathcal{I}$ is generated by two elements, i.e. $\mathcal{I} = \langle q, F_\mathcal{I}(\zeta) \rangle$ for some $f$-degree polynomial $F_\mathcal{I}$ with integer coefficients, by [[Terminology|Dedekind Theorem]].

>[!question] Can we generalize this to a more general ideal $\mathcal{I}$?

We can! We can extend Dedekind theorem to every ideal factor $\mathcal{I}$ of $qR$ where $q$ is a prime number and $\mathcal{N(\mathcal{I})} = q^t$ for $1 \le t \le N$, such that $\mathcal{I} = \langle q, F_{\mathcal{I}}(\zeta)\rangle$ for some $t$-degree integer-coefficient polynomial $F_\mathcal{I}$.

This shows that each coset of $\mathcal{R}/\mathcal{I}$ has a representative $\sum\limits_{i=0}^{t-1}a_i\zeta^i$ for some $a_i \in \Bbb{Z}_q$, indicating that the quotient ring $\mathcal{R}/\mathcal{I}$ is isomorphic to $\Bbb{Z}_q^t \times \{0\}^{N-t}$ via the coefficient embedding mapping $\phi$.