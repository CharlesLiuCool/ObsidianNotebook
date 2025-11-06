___

### **6.1.1 Deterministic Extractors**

>**Motivation**
>In many of our earlier designs, we assumed access to sources of *perfect randomness*, but this is infeasible in real life. Instead, we want to be able to take any of our earlier algorithms which took in perfectly random bits $U_m$, and create a new algorithm relying on a "weak" random source that also works.

![[Chapter 6 Randomness Extractors 2025-09-02 15.33.05.excalidraw|600]]

We can design a *randomness extractor* $\text{Ext}: \{0,1\}^n\to\{0,1\}^m$ such that $\text{Ext(X)}$ is distributed uniformly in $\{0,1\}^m$

___

>**Definition** Sources
>To be precise, we first define a source. A *source* on $\{0,1\}^n$ is a random variable $X$ taking values in $\{0,1\}^n$.

**IID-Bit Sources**
Consider if you had $n$ Bernoulli random variables
$$X_1,X_2,...,X_n \in \{0,1\}$$
that are independent but biased. this means for every $i$, $P(X_i = 1) = \delta$ for some unknown $\delta$.

>[!question] How can we convert this source into a source of independent, *unbiased* bits?

*Algorithm*
Von Neumann proposed the following extractor:
1. Group all variables into pairs.
2. For each pair:
	1. Output $0$ if the outcome was $01$
	2. Output $1$ if the outcome was $10$
	3. If the outcome was $00$ or $11$, give up.

*Analysis*
Consider the outcome $01$. This event has $(1-\delta)\delta$ of occurring.
Consider the outcome $10$. This event has $\delta(1-\delta)$ of occurring.

Notice that these are the same.
However, the other two cases $00$ and $11$ have worsened bias, so we give up on those outcomes.

Since we only succeed on the two outcomes $01$ and $10$, the probability of success is $2(1-\delta)\delta$.

Considering the properties of [[Statistics#**Geometric Distribution**|Geometric Distributions]], we can see that on average the number of pairs we need is the reciprocal of the probability, or
$$E[\text{\# of pairs}] = \frac{1}{2(1-\delta)\delta}$$

___

**Independent Bit Sources**

>[!question] What if each variable is still independent, but has differing bias?
>In other words, for every $i$, $$P(X_i = 1) = \delta_i$$
>where $0 < \delta \le \delta_i \le 1 - \delta$ for some constant $\delta$.
>(Note that we bound $\delta_i$ like this so every bit has some amount of entropy!)

*Algorithm*
We can design an extractor that takes the parity of $l$ bits!
In other words, for some bits $X_1, X_2, ..., X_l \in \{0,1\}$, we take the XOR
$$\bigoplus_{i=1}^l X_i = X_1 \oplus X_2 \oplus ... \oplus X_l$$

*Analysis*
Consider each $X_i$ which is an independent biased coin.
$$P(X_i = 1) = p = \frac{1}{2} + \delta,\;P[X_i = 0] = \frac{1}{2} - \delta$$

The parity of $l$ bits has bias
$$\left|P\left[\bigoplus_{i=1}^l X_i = 1 \right] - \frac{1}{2} \right| = |\delta|^l$$

Therefore, we get
$$\left|P\left[\bigoplus_{i=1}^l X_i = 1 \right] - \frac{1}{2} \right| = 2^{-\Omega(l)}$$
___

>**Definition** Deterministic Extractors
> Let $C$ be a class of sources on $\{0,1\}^n$. An $\epsilon$-extractor for $C$ is a function Ext: $\{0,1\}^n \to \{0,1\}^m$ such that for every $X \in C$, Ext($X$) is "$\epsilon$-close" to $U_m$.

>**Definition** Statistical Difference
>For random variables $X$ and $Y$ taking values in $U$, their *statistical difference* (also known as *variation distance*) is $\delta(X,Y) = \max_{T \subset U} |\Pr[X \in T] - \Pr[Y \in T]|$. We say that $X$ and $Y$ are $\epsilon$-close if $\delta(X,Y) \le \epsilon$.

>**Lemma** Properties of Statistical Difference
>Let $X,Y,Z,X_1,X_2,Y_1,Y_2$ be random variables taking values in a universe $U$. Then,
>1) $\Delta(X,Y) \ge 0$, with equality $\iff$ $X$ and $Y$ are identically distributed
>2) $\Delta(X,Y) \le 1$, with equality $\iff$ $X$ and $Y$ have disjoint supports
>3) $\Delta(X,Y) = \Delta(Y,X)$
>4) $\Delta(X,Z) \le \Delta(X,Y) + \Delta(Y,Z)$
>5) For every function $f$, we have $\Delta(f(X),f(Y)) \le \Delta(X,Y)$
>6) $\Delta((X_1,X_2),(Y_1,Y_2)) \le \Delta(X_1,Y_1) + \Delta(X_2,Y_2)$ if $X_1$ and $X_2$, as well as $Y_1$ and $Y_2$ are independent
>7) $\Delta(X,Y) = \frac{1}{2}\cdot|X-Y|_1$, where $|\cdot|_1$ is the $\ell_1$ distance. (Thus, $X$ is $\epsilon$-close to $Y$ if we transform $X$ into $Y$ by "shifting" at most an $\epsilon$-fraction of probability mass)

>**Proposition** (Switching out true random bits with a randomness extractor's bits on a weak source only adds $\epsilon$ to the error probability)
>
> Let $A(\omega;r)$ be a randomized algorithm such that $A(\omega;U_m)$ has error probability at most $\gamma$, and let $\text{Ext}: \{0,1\}^n \to \{0,1\}^m$ be an $\epsilon$-extractor for a class $C$ of sources on $\{0,1\}^n$. Define $A'(\omega;x) = A(\omega;\text{Ext}(x))$. Then for every source $X \in C$, $A'(\omega;X)$ has error probability at most $\gamma + \epsilon$.


> **Proposition** (We can efficiently extract nearly uniform randomness from independent-bit sources)
> For every constant $\delta > 0$, every $n,m \in \Bbb{N}$, there is a polynomial-time computable function $\text{Ext}:\{0,1\}^n \to \{0,1\}^m$ that is an $\epsilon$-extractor for IndBits$_{n,\delta}$ with $\epsilon = m \cdot 2^{-\Omega(n/m)}$

___

**Unpredictable-Bit Sources (Santha-Vazirani Sources)**

The sources where for every $i$, every $x_1,...,x_n \in \{0,1\}$ and some constant $\delta > 0$, satisfy
$$\delta \le \Pr[X_i = 1 | X_1 = x_1, X_2 = x_2, ..., X_{i-1} = x_{i-1}] \le 1-\delta$$
is called *unpredictable bit sources*, or $\text{UnpredBits}_{n,\delta}$

>**Proposition**
>For every $n \in \Bbb{N}$, $\delta > 0$, and fixed extraction function $\text{Ext}: \{0,1\}^n \to \{0,1\}$ there exists a source $X \in \text{UnpredBits}_{n,\delta}$ such that either $\Pr[\text{Ext}(X) = 1] \le \delta$ or $\Pr[\text{Ext}(X) = 1] \ge 1 - \delta$. That is, there is no $\epsilon$-extractor for $\text{UnpredBits}_{n,\delta}$ for $\epsilon < 1/2 - \delta$

No matter what extractor function you try, and adversary can pick a unpredictable bit source that causes your output to be super biased (almost constant). Suppose we know which way a conditional sways, we can keep pushing the bits to generate towards a specific constant outcome $0$ or $1$. 

This means there is no nontrivial extractor for such sources. The best error we can hope for is $\epsilon < 1/2-\delta$ (the distance from uniform to the bit).

___

### **6.1.2 Entropy Measures and General Weak Sources**

We need to measure how much randomness is in a variable.

> **Definition (entropy measures).** Let $X$ be a random variable.
> Then
> - the *Shannon entropy* of $X$ is:
> $$H_{\text{Sh}}(X) = \underset{x \xleftarrow{R} X}{E} \left[\log \frac{1}{\Pr[X=x]}\right]$$
> - the *Rényi entropy* of $X$ is:
> $$H_2(X) = \log\left(\frac{1}{\underset{x \xleftarrow{R} X}{E}[\Pr[X=x]]}\right) = \log \frac{1}{\text{CP}(X)}$$
> - the *min-entropy* of $X$ is:
> $$H_\infty(X) = \min\limits_x \left\{\log \frac{1}{\Pr[X=x]}\right\}$$
> where all logs are base $2$

*Min-entropy* is the worst case, calculating the worst possible unpredictability of X.

*Rényi Entropy* measures how likely two independent samples will collide, defining collision resistance.

*Shannon entropy* measures average uncertainty

>**Lemma (properties of entropy)** For each of the entropy measures $H \in \{H_{Sh}, H_2, H_\infty\}$ and random variables $X$, $Y$, we have:
>- $H(X) \ge 0$ with equality $\iff$ $X$ is supported on a single element
>- $H(X) \le \log|\text{Supp}(X)|$, with equality $\iff$ $X$ is uniform on $\text{Supp}(X)$
>- if $X,Y$ are independent, then $H((X,Y)) = H(X) + H(Y)$
>- for every deterministic function $f$, we have $H(f(X)) \le H(X)$,
>- for every $X$, we have $H_\infty(X) \le H_2(X) \le H_{\text{Sh}}(X)$

Note that

>**Definition** Support
>The support of random variable $X$, denoted $\text{Supp}(X)$, is the set of all outcomes with nonzero probability
>$$\text{Supp}(X) = \{x \in X: \Pr[X=x] > 0\}$$

>**Definition** $k$-source
>A random variable $X$ is a *k-source* if $H_\infty(X) \ge k$ i.e. if
>$$\Pr[X=x] \le 2^{-k}$$

*Examples of $k$-sources*
- $k$ random and independent bits, together with $n-k$ fixed bits (in arbitrary order). These are called *oblivious bit-fixing* sources
- $k$ random and independent bits, and $n-k$ bits that depend arbitrarily on the first $k$ bits. These are called *adaptive bit-fixing sources*
- Unpredictable-bit sources with bias parameter $\delta$. These are $k$-sources with $k = \log(1/(1-\delta)^n = \Theta(\delta n)$
- Uniform distribution on a set $S \subset \{0,1\}^n$ with $|S| = 2^K$. These are called *flat k-sources*

>**Lemma**
>Every $k$-source is a convex combination of flat $k$-sources (provided that $2^k \in \Bbb{N}$), i.e., $X = \sum\limits p_iX_i$ with $0 \le p_i \le 1, \sum p_i = 1$ and all the $X_i$ are flat $k$-sources.

*Proof* 
Let $X$ be a $k$-source on $[N]$. We can view $X$ as a partitioning a circle of unit circumference into $N$ (half-open) intervals, where the $t$th interval has length exactly $\Pr[X = t]$

![[Chapter 6 Randomness Extractors 2025-09-04 10.23.14.excalidraw]]

Now consider a set $S$ of $K$ points spaced evenly on the circle. As each interval is half-open and has length at most $1/K$, each interval contains at most one point from $S$, so the uniform distribution on the set $T(S) = \{t: S \cap I_t \neq \emptyset\}$ is a flat $k$-source.

If we perform a uniformly random rotation of $S$ on the circle to obtain a rotated set $R$ and then choose a uniformly random element of $T(R)$, the probability that we output any value $t \in [N]$ is exactly the length of $I_t$, which equals $\Pr[X=t]$.

In other words, the probability we pick an element that lands up in that hit set if the length of the part of the circumference, or $\Pr[X=t]$

Then we realize
$$X = \sum\limits_Tp_TU_T$$
where $T \subseteq [N]$ of size $K$, and $p_T = \Pr_R[T(R) = T]$

In other words, we have broken the $k$-source $X$ into the uniform distribution over every hit set (a flat $k$-source) multiplied by a weight (the probability any element lands on that part of the circumference) which is a convex combination.

___

### **6.1.3 Seeded Extractors**

>**Proposition** For any $\text{Ext}: \{0,1\}^n \to \{0,1\}^n$, there exists an $(n-1)$ source $X$ so that $\text{Ext}(X)$ is constant.

*Proof*
There exists $b \in \{0,1\}$ so that $|\text{Ext}^{-1}(b)| \ge \frac{2^n}{2} = 2^{n-1}$. Then let $X$ be the uniform distribution on $\text{Ext}^{-1}(b)$.

>**Defining Notation**
>Note that we will use capital letters such as $K$ and $M$ to denote the corresponding power of the lowercase letter, so $$K=2^k \text{ and } M=2^m$$

>**Proposition** For every $n,k,m \in \Bbb{N}$, every $\epsilon > 0$ and every flat $k$-source $X$, if we choose a random function $\text{Ext}: \{0,1\}^n \to \{0,1\}^m$ with $m = k - 2\log(\frac{1}{\epsilon}) - O(1)$, then $\text{Ext(X)}$ will be $\epsilon$-close to $U_m$ with probability $1-2^{-\Omega(K\epsilon^2)}$, where $K=2^k$.

*Proof*
Choose our extractor randomly. We want it to have following property: for all $T \subset [M]$, $|\Pr[\text{Ext}(X) \in T] - \Pr[U_m \in T]| \le \epsilon$.
Equivalently, $|\{x \in \text{Supp}(X): \text{Ext}(x) \in T\}|/K$ differs from the density $\mu(T)$ by at most $\epsilon$. For each point $x \in \text{Supp}(X)$, the probability that $\text{Ext}(x) \in T$ is $\mu(T)$, and these events are independent. By the Chernoff Bound for each fixed $T$ this condition holds with probability at least $1 - 2^{-\Omega(K\epsilon^2)}$. Then the probability that the condition is  violated for at least one $T$ is at most $2^M2^{-\Omega(K\epsilon^2)}$, which is less than $1$ for $m = k-2\log(1/\epsilon) - O(1)$.

___

>**Theorem** (Leftover Hash Lemma)
If $\mathcal{H} = \{h: \{0,1\}^n \to \{0,1\}^m\}$ is a pairwise independent (or even $2$-universal) family of hash functions where $m = k - 2 \log(1/\epsilon)$, then $\text{Ext}(x,h) = h(x)$ is a strong $(k, \epsilon)$-extractor. Equivalently, $\text{Ext}(x,h) = (h,h(x))$ is a standard $(k,\epsilon)$-extractor.

*Proof*
Let
- $X$ be an arbitrary $k$-source on $\{0,1\}^n$
- $\mathcal{H}$ as above
- $H \xleftarrow{R} \mathcal{H}$.
- $d$ be the seed length.

>We show that $(H,H(X))$ is $\epsilon$-close to $U_d \times U_m$ in the following three steps:

1) We show that the collision probability of $(H,H(X))$ is close to that of $U_d \times U_m$
2) We note that this is equivalent to saying that the $l_2$ distance between $(H,H(X))$ and $U_d \times U_m$ is small
3) Then we deduce that the statistical difference is small, by recalling that the statistical difference equals half of the $\ell_1$ distance, which can be loosely bounded by the $\ell_2$ distance

*Proof of 1)*
By definition, $CP(H,H(X)) = \Pr|(H,H(X)) = (H', H'(X'))|$, where $(H', X')$ is independent of and identically distributed to $(H,X)$.
(Recall $CP$ means collision probability)

Note that $(H,H(X) = (H',H'(X))$ if and only if $H=H'$ and either $X=X'$ or $X \neq X'$ but $H(X) = H(X')$. Thus
$$\begin{align} CP(H,H(X)) &= CP(H) \cdot (CP(X) + \Pr[H(X) = H(X') | X \neq X']) \\ &\le \frac{1}{D}\left(\frac{1}{K} + \frac{1}{M} \right) \\ &\le \frac{1 + \epsilon^2}{DM}  \end{align}$$

Note that $CP(H) = \frac{1}{D}$ because there are $D$ hash functions, $CP(X) \le 1/K$ because $H_\infty(X) \ge k$, and $\Pr[H(X) = H(X') | X \neq X'] \le \frac{1}{M}$ by $2$-universality (also called pairwise independence).

The last part of the inequality comes from the fact that $m=k-2\log(1/\epsilon)$, which means
$$K = 2^k = 2^{m+2\log(1/\epsilon)} = \frac{M}{\epsilon^2}$$
(recall $M = 2^m$)

*Proof of 2)*

$$\begin{align}||(H,H(X) - U_d \times U_m)||^2 &= CP(H,H(X)) - \frac{1}{DM} \\ &\le \frac{1+\epsilon^2}{DM} - \frac{1}{DM} = \frac{\epsilon^2}{DM}\end{align}$$

*Proof of 3)*

Recall the statistical difference between two random variables $X$ and $Y$ is $\frac{1}{2}|X-Y|_1$, we have:

$$\begin{align} \Delta((H,H(X)), U_d \times U_m) &= \frac{1}{2} \cdot |(H,H(X)) - U_d \times U_m|_1 \\ &\le \frac{\sqrt{DM}}{2} \cdot ||(H,H(X)) - U_d \times U_m|| \\ &\le \frac{\sqrt{DM}}{2} \cdot \sqrt{\frac{\epsilon^2}{DM}} \\ &= \frac{\epsilon}{2} \end{align}$$

Note the $\frac{\sqrt{DM}}{2}$ is introduced as a result of Cauchy-Schwartz inequality. Specifically the inequality
$$|p-u|_1 \le \sqrt{D} ||p-u||_2$$
where:
- $p$ = probability vector of $(H,H(X))$
- $u$ = uniform vector over all $D=2^{d+m}$ elements

See attached [[Chapter 6 Randomness Extractors#**Extra Lemma**]]

Thus, we obtain a strong $(k, \epsilon/2)$-extractor

 ##### **Extra Lemma**
>Note
> - $\ell_1$ norm is $|v|_1 = \sum\limits_{i=1}^D |v_i|$
> - $\ell_2$ norm is $||v||_2 = \sqrt{\sum\limits_{i=1}^D |v_i|^2}$
> 
> We can use Cauchy-Schwartz
> $$\sum\limits_{i=1}^D |a_ib_i| \le \sqrt{\sum\limits_i a^2} \sqrt{\sum\limits_i b_i^2}$$
> 
> where in our case, $a_i = v_i$ and $b_i = 1$ for all $i$.
> 
> We get,
> $$\sum_{i=1}^{D} |v_i| = \sum_{i=1}^{D} |v_i| \cdot 1 \le \sqrt{\sum_{i=1}^{D} |v_i|^2} \cdot \sqrt{\sum_{i=1}^{D} 1^2} = \sqrt{D} \, \|v\|_2$$
> 
> So,
> $$|p-u|_1 \le \sqrt{D} ||p-u||_2$$
> where:
> - $p$ = probability vector of $(H,H(X))$
> - $u$ = uniform vector over all $D=2^{d+m}$ elements

___

### **6.2.2 Extractors versus Expanders**

