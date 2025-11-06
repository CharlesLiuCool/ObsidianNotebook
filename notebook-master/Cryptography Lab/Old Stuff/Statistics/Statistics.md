___

### **Strong/Weak Law of Large Numbers**

**Theorem.** (Weak Law of Large Numbers)
$$ \lim_{n \to \infty}\Bbb{P}(|\overline{X_n} = \mu| < \epsilon) = 1$$
Notice that this *converges in probability*

**Theorem.** (Strong Law of Large Numbers)
$$ \Bbb{P}(\lim_{n \to \infty} \overline{X_n} = \mu) = 1$$

___

### **Geometric Distribution**

Let $Y$ be a random variable, where $Y$ denotes the number of independent trials until the first success where each binary trial has success probability $q$.

**Theorem.** $\Bbb{E}[Y] = \frac{1}{q}$
*Proof:*
Using the definition of expected value,
$$\Bbb{E}[Y] = \sum\limits_{i=1}^\infty q(1-q)^{i-1} i = q\sum\limits_{i=1}^\infty (1-q)^{i-1}i$$
Notice that if we find $\sum\limits_{i=1}^\infty(1-q)^{i-1}i$, we are done.
Denote $x = (1-q)$
$\sum\limits_{i=1}^\infty x^{i-1}i = \sum\limits_{i=1}^\infty \frac{d}{dx}(x^i) = \frac{d}{dx}(\sum\limits_{i=1}^\infty x^i) = \frac{d}{dx}(\sum\limits_{i=0}^\infty x^i - 1) =\frac{d}{dx}(\frac{1}{1-x}-1) =\frac{1}{(1-x)^2}$
Substitute $x=(1-q)$
$$\frac{1}{(1-x)^2} = \frac{1}{q^2}$$
Thus,
$$\Bbb{E}[Y] = q\sum\limits_{i=1}^\infty (1-q)^{i-1}i = \frac{q}{q^2} = \frac{1}{q}$$

___

### **PDFs, CDFs, and Moment Generating Functions**

>**Definition** of PDF, CDFs, and Moment Generating Functions over discrete and continuous random variables.

|         | **Discrete Random Variable**      | **Continuous Random Variable**         |
| ------- | --------------------------------- | -------------------------------------- |
| **PDF** | $f(x) = P(X = x)$                 | $f(x) = F'(x)$                         |
| **CDF** | $P(X \le x) =\sum_{y:y\le x}f(y)$ | $P(X \le x) = \int_{-\infty}^x f(u)du$ |
| **MGF** | $E[e^{tx}] =\sum_{x\in X}e^{tx}f(x)$                       | $E[e^{tx}] =\int_{-\infty}^\infty e^{tx}f(x)$                                       |

Note we only define the *PDF* for the continuous random variable case this way when the *CDF* ($F(x)$) is absolutely continuous.

>**Definition** Absolutely Continuous
>A real valued function $f$ on $[a,b]$ is absolutely continuous on that interval if $\forall$ $\epsilon > 0$, $\exists\;\delta > 0$ such that if $|b_k-a_k| < \delta$
>$$\sum\limits_{k = 1}^n|f(b_k)-f(a_k)| < \epsilon$$
>for every $n$ disjoint subintervals $(a_k,b_k)$ of $[a,b], k = 1,...,n$ such that $\sum\limits_{k=1}^n|b_k-a_k| < \delta$.

*Remark*
When $n=1$, we achieve *uniform continuous*.

>**Definition** Uniform Continuous
>A real valued function $f$ is uniform continuous on $[a,b]$ if $\forall \epsilon > 0$, $\exists \; \delta > 0$ such that $\forall x,y \in [a,b]$, if $|y-x| \le \delta$, then
>$$|f(y) - f(x)| \le \epsilon$$

![[Statistics 2025-09-04 22.06.14.excalidraw|500]]

**Cantor Functions**
Cantor functions are an example of a function that is continuous, but not differentiable at uncountable points.

![[Statistics 2025-09-04 22.15.49.excalidraw|700]]

Notice that if switch from decimal to base $3$, we're flattening the slope of every base $3$ value that can be represented with $1$. Note that there are uncountable such points in the Cantor set.

This is continuous, but *NOT* absolutely continuous, which means we can't differentiate on many points.

___