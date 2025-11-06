### **Order Statistics**

Consider $n$ independent and identically distributed (a random sample, or iid), continuous random variables, $X_1, ..., X_n$ with common PDF $f(x)$.

Define the increasing order statistic $Y_k, k = 1,...,n$, as
$$Y_k = X_{K:n} = \text{the }k-\text{th smallest value among }X_1,...,X_n$$

The minimal value $Y_1 = \min\{X_1,...,X_k\}$.
The maximal value $Y_n = \max\{X_1,...,X_n\}$

$X_1,X_2,...,X_{n-1},X_n \iff X_{1:n} < X_{2:n} < ... < X_{n-1:n} < X_{n:n}$

$\underbrace{X_{1:n}}_{\text{Extremes}} ..., ..., \underbrace{X_{k:n}, X_{k+1,n}, ..., X_{I-1:n}, X_{I:n}}_{\text{Central Order Statistics}},...,..., \underbrace{X_{n:n}}_{\text{Extremes}}$

The PDF of $(X_1,...,X_n)$ is given by $f(x_1,...,x_n) = f(x_1) ... f(x_n)$.

>**Theorem**
>The joint PDF of $(Y_1, ..., Y_n)$ (the order statistic) is 
>$$g(y_1,...,y_n) = n!f(y_1)...f(y_n)$$
>for $y_1 < y_2 < ... < y_n$

*Proof:*
For any given permutation of $\{X_1, ..., X_n\}$ say $X_1 < X_2 < ... < X_n$ we have
$$\{Y_1 = y_1, ..., Y_n = y_n\} = \{X_1 = y_1, ..., X_n = y_n\}$$

That is, $g(y_1,...,y_n) = f(y_1)...f(y_n)$ for $X_1 < X_2 < ... X_n$
Since there are totally $n!$ permutations,
$$g(y_1,...,y_n) = n!f(y_1)...f(y_n)$$

Suppose that $X_1,...,X_n$ denote a random sample of size $n$ from a continuous PDF, $f(x)$, where $f(x) > 0$, for $a < x < b$ (and correspondingly, CDF $F(x)$)

>**Theorem**
>The PDF of the $k$-th order statistic $Y_k$, is given by
>$$g_k(y_k) = n\begin{pmatrix}n-1 \\ k-1 \end{pmatrix} F(y_k)^{k-1}f(y_k)[1-F(y_k)]^{n-k}$$

___

### **Review of Fundamental Limits**

For any constants $a,b$,
$$\lim_{n \to \infty}(1 + \frac{a}{n})^{bn} = e^{ab}$$

For any constants ${a,b,}$
$$\lim_{n\to\infty} n\log(1 + \frac{a}{n}) = a$$

If $\lim\limits_{n \to \infty} c(n) = 0$
$$\lim_{n \to \infty}\left(1 + \frac{a}{n} + \frac{c(n)}{n}\right)^{bn} = e^{ab}$$

___

### **Convergence in Distributions**

>**Definition**
>Suppose that $Y_n \sim G_n(y), n = 1,2,...$. The sequence $Y_1, Y_2, ...$, is said to converge in distribution to a random variable $Y \sim G(y)$ if
>$$\lim_{n \to \infty} G_n(y) = G(y),$$
>for all values $y$ at which $G(y)$ is continuous.

- The limit notation: $Y_m \xrightarrow{d} Y$, $G_n \to^d G$, etc.
- The CDF $G(y)$ is called the limiting distribution

