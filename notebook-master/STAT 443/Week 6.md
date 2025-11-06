### **Normal (or Gaussian) Distribution**

- *Normal density function* $X \sim N(\mu, \sigma)^2$:
$$\varphi_{\mu,\sigma^2}(x) = \frac{1}{\sqrt{2\pi} \sigma}e^{\frac{-(x-\mu)^2}{2\sigma^2}},-\infty < x < \infty$$

- *Normal random variable*: $X$ has a normal density function $N(\mu, \sigma^2)$. $\mu =$ location parameter, $\sigma =$ scale parameter

### **Properties of Normal Distributions**

1. Normal density curve is symmetric about $\mu$
2. The curve reaches the maximum at $\mu$.
3. $E(X) = \mu$
4. $V(X) = \sigma^2$
5. $\Bbb{P}(\mu - \sigma, X < \mu + \sigma) \approx 0.68$

### **Normal Approximation**

- Many histograms of large samples have similar shapes as that of normal distributions (Marquis de Laplace, $1810$)
- Carl Gauss discovered the normal distribution in $1809$ as a way to specify errors in the method of least squares.

### **Standard Normal Random Variables**

- Standard Normal $Z \sim N(0,1), \mu = 0, \sigma^2 = 1$
$$\varphi(z) = \frac{1}{\sqrt{2\pi}} e^{-\frac{z^2}{2}}, -\infty < z < \infty$$

$\varphi(z) = \varphi(-z)$ and $\varphi'(z) = -z \varphi(z)$. In fact
$$\varphi'(z) = \frac{1}{\sqrt{2\pi}} e^{-\frac{z^2}{2}}(\frac{-z^2}{2})' = \frac{1}{\sqrt{2\pi}} e^{\frac{-z^2}{2}}(-z) = -z \varphi(z)$$

In general, $\varphi^(n)(z) = (-1)^n H_n(z)\varphi(z)$ Where $H_n(z)$ is the $n$-th Hermite polynmial.

CDF of $N(0,1)$: $\phi(z) = \Bbb{P}(Z \le z)$

>**Theorem** (Standardizing Normal Random Variables)
>If $X$ has $N(\mu, \sigma^2)$, then
>$$Z = \frac{X - \mu}{\sigma}, (\text{called the standardization!})$$
>has the standard normal $N(0,1)$

*Proof:* Consider

$F_z(z) = \Bbb{P}(\frac{X - \mu}{\sigma} \le z) = \Bbb{P}(X \le \mu + \sigma z) = \int_{-\infty}^{\mu + \sigma z} \frac{1}{\sqrt{2\pi}}e^{-\frac{(x-\mu)^2}{2\sigma^2}}dx$

Thus the PDF of $Z$ becomes

$$f_Z(z) = F_Z('z) = \frac{1}{\sqrt{2\pi}\sigma}e^{-z^2}(\mu + \sigma z)' = \frac{1}{\sqrt{2\pi}}e^{-z^2}$$

and $Z \sim N(0,1)$

### **The Standardization**

In fact, $X \sim N(\mu, \sigma^2) \iff Z = \frac{X - \mu}{2} \sim N(0,1)$, $(X = \mu + \sigma Z)$

- The standardization leads to 
$$\begin{align} \Bbb{P}(a < X < b) &= \Bbb{P}\left(\frac{a - \mu}{\sigma} < \frac{X - \mu}{\sigma} < \frac{b - \mu}{\sigma} \right) \\ &= \Bbb{P}\left(\frac{a - \mu}{\sigma} < Z < \frac{b- \mu}{\sigma}\right) \\ &= \upphi\left(\frac{b - \mu}{\sigma}\right) - \upphi\left(\frac{a - \mu}{\sigma}\right)\end{align}$$

### **The Moment Generating Function $M_x(t)$**

If $X \sim N(\mu, \sigma^2)$, then
$$M_x(t) = e^{\mu t + \sigma^2 t^2 /2}$$

$\begin{align} M_z(t) &= \int_{-\infty}^\infty e^{tz} \frac{1}{2\pi}e^{-z^2/2}dz \\ &= \int_{-\infty}^\infty \frac{1}{\sqrt{2 \pi}} e^{(z-t)^2/2} e^{\frac{t^2}{2}}dz = e^{t^2/2} \int_{-\infty}^\infty \frac{1}{\sqrt{2\pi}} e^{-(z-t)^2/2}dz = e^{t^2/2} \end{align}$

In general,
$M_X(t) = M_{\mu + \sigma Z} (t) = e^{t\mu}M_z(\sigma t) = e^{t \mu} e^{\frac{\sigma^2 t^2}{2}} = e^{\mu t + \sigma^2t^2/2}$

The odd-ordered central moment $E(X - \mu)^{2k - 1} = 0$, $k = 1,2,...,$

___

### **Discrete Random Vectors**

>**Joint Probability Mass Functions**
>The joint probability mass or discrete density function (join PMF) of the $k$-dimensional discrete random variable $X = (X_1, X_2, ..., X_k)$ is defined as
>$$f(x_1,x_2,...,x_k) = \Bbb{P}(X_1 = x_1, X_2 = x_2, ..., X_k = x_k)$$
>for all possible values $x_1,...,x_k$

___

### **The Distribution of $X = (X_1,...,X_k)$**

- $0 \le f(x_1,...,x_k) \le 1$
- $\sum ... \sum_{\text{all values}} f(x_1, ..., x_k) = 1$
- For $A \subseteq \Bbb{R}^k$
$$\Bbb{P}(X \in A) = \sum ...\sum_{(x_1,...,x_k) \in A}f(x_1,...,x_k)$$
- The joint cumulative distribution function (Joint CDF):
$$F(x_1,...,x_k) = \Bbb{P}(X_1 \le x_1,...,X_k \le x_k)$$

>**Univariate Marginal Distributions**
>If the pair $(X_1, X_2)$ of discrete random variable has the joint PMF $f(x_1,x_2)$, then the marginal PMF's of $X_1$ and $X_2$ are
>$$f_1(x_1) = \sum\limits_{\text{all }x_2}f(x_1,x_2), f_2(x_2) = \sum\limits_{\text{all }x_1}f(x_1, x_2)$$

### **Example: Hypergeometric Distribution**

Suppose that a collection consists of a finite number of $N$ items and that there are $k$ different types;
$$M_1 \text{ of type }1, M_2 \text{ of type }2,..., M_k \text{ of type k}$$

e.g. categories: items that are good, items with major defects, items with minor defects.

Select $n \le N$ items at random *without replacement*, and let $X_i$ be the number of items of type $i$ that are selected. The vector $X = (X_1, X_2,...,X_k)$ has a joint PMF of the form
$$f(x_1,...,x_k) = \dfrac{\binom{M_1}{x_1} \binom{M_2}{x_2} ... \binom{M_k}{x_k}}{\binom{N}{n}}$$
for all $x_1 + x_2 + ... + x_k = n$, $M_1 + ... + M_k = N$

### **Example: Tri-nomial Distribution**

Suppose that there are three mutually exclusive and exhaustive events, say $E_1, E_2, E_3$ which can occur on any trial of an experiment, and let $p_i = \Bbb{P}(E_i)$ for $i = 1,2,3$.

On $n$ independent trials of the experiment let $X_i$ be the number of occurrences of the event $E_i$. The total number of all arrangements that exactly $r_i$ occurrences are $E_i$, $i= 1,2,3$ is
$$Total \# = \frac{n!}{r_1!r_2r_3!}, r_1 + r_2 + r_3 = n$$

The vector $X = (X_1, X_2)$ is said to have the trinomial distribution which has a joint PMF of the form
$$\begin{align} f(r_1, r_2) &= \Bbb{P}(X_1 = r_1,X_2 = r_2) = (\text{ Total \#})p_1^{r_1}p_2^{r_2}p_3^{r_3} \\& = \frac{n!}{r_1!r_2!r_3!}p_1^{r_1}p_2^{r_2}p_3^{r_3} \end{align}$$

### **Continuous Random Vectors**

The joint probability density function (joint PDF) of the $k$-dimensional continuous random variable $X = (X_1,X_2,...,X_k)$ is a non-negative, integrable function $f(x_1, ..., x_k)$ such that the cumulative distribution function (joint CDF) can be written as
$$\begin{align} F(x_1, x_2, ..., x_k) &= \Bbb{P}(X_1 \le x_1, ..., X_k \le x_k) \\ &= \int_{-\infty}^{x_1} ... \int_{-\infty}^{x_k} f(t_1,...,t_k)dt_1...dt_k\end{align}$$

for all possible values $x_1, ..., x_k$
Equivalently
$$f(x_1,...,x_k) = \dfrac{\partial^k F(x_1, x_2,...,x_k)}{\partial x_1, ..., x_k}$$

> **Univariate Marginal Distributions**
>If the pair $(X_1, X_2)$ of continuous random variables has the joint PDF $f(x_1, x_2)$, then the marginal pdf's of $X_1$ and $X_2$ are
>$$f_1(x_1) = \int_{\text{all }x_2} f(x_1,x_2), f_2(x_2) = \int_{\text{all }x_1 f(x_1,x_2)dx_1}$$

### **The Distribution of $X$**

- $f(x_1, ...x_k) \ge 0$
- $\int ... \int_{\text{all values}} f(t_1, ..., t_k)dt_1...dt_k = 1$
- For any subset $A \subseteq \Bbb{R}^k$,
$$P(X \in A) = \int ... \int_A f(t_1,...,t_k)dt_1...dt_k$$

Let $X = (X_1, X_2,...,X_k)$ have the CDF $F(x_1, ..., x_k)$ Then the $i$-th marginal CDF and PDF of $X_1$ are given by
$$F_i(x_i) = \lim_{x_j \to \infty\;\forall j \neq i} F(x_1, ..., x_{i-1}, x_i, x_{i+1},...,x_k)$$
$$f_i(x_i) = F'_i(x_i)$$

### **Independence**

>**Definition**
>Random variables $X_1, ..., X_k$ are said to be independent if for any events $A_i,...,A_k$,
>$$\Bbb{P}(X_1 \in A_1, ..., X_k \in A_k) = \prod_{i=1}^k P(X_i \in A_i)$$

- Random variable $X_1,...,X_k$
$$\begin{align} F(x_1,...,x_k) &= P(X_1\le x_1,...,X_k \le x_k) \\ &= \prod_{i=1}^k P(X_i \le x_i) = \prod_{i=1}^k F_i(x_i) \end{align}$$

- Random variables $X_1,...,X_k$ are independent if and only if
$$f(x_1,...,x_k) = \prod_{i=1}^k f_i(x_i)$$