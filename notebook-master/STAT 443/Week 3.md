### **Random Variables and Distributions**

- Random variable (RV): A real-valued (Borel-measurable) function defined on the sample space: $S \to \Bbb{R}$.
- Random variables (RV): Denoted by capital letters, $X$, $Y$, $N, ...$
- Values of Random Variables: Denoted by lowercase letters, $x$, $y$, $n, ...$
- Distribution of RV $X$: Relative frequencies or probability measurements of various values of $X$.

### **Discrete Random Variables**

- The distribution of a discrete random variable $X$ is described by the *probability mass function (PMF, discrete density function, discrete PDF)*

$$p_X(x_i) = \Bbb{P}(X=x_i), \text{ for all the possible values }x_i \text{ of }X$$

- Distribution of RV $X$: Likelihoods or relative frequencies of various values of $X$.

>**Properties of PMF**
>1. $0 \le p(x) \le 1$
>2. $\sum_{\text{all }x\text{'s}}p(x) = 1$

### **Cumulative Distribution Function - Cumulative Frequency**

>**Cumulative Distribution Function (CDF) of X**
>$$F(x) = \Bbb{P}(X \le x) = \sum\limits_{y:y\le x}p(y)$$

1. $F(x)$ is step-wise, non-decreasing
2. $0 \le F(x) \le 1$
3. $F(x) \to 0$ as $x \to -\infty$
4. $F(x) \to 1$ as $x \to +\infty$
5. $\lim_{h\to 0}F(x+h) = F(x)$

### **PMF vs CDF**

$$\Bbb{P}(a \le X \le b) = \sum\limits_{y:a\le y\le b}P_x(y) = F(b) - F(a-)$$

- In general
$$\Bbb{P}(a \le X \le b) = \sum\limits_{y:a\le y \le b} P_x(y) = F(b) - F(a-)$$
In particular,
$$p_x(x_i) = \Bbb{P}(X = x_i) = F(x_i) - F(x_{i-1})$$
where $X$ has probability masses at $x_1 < x_2 < \;...$

- $F(x) = \sum\limits_{y:y \le x} p_x(y)$

### **Discrete Random Variables**

- Let $X$ be a discrete random variable with *probability mass function (PMF)*
$$p(x_i) = \Bbb{P}(X = x_i), \text{ for all possible values }x_i \text{ of }X$$

- The mean value (expected value) $\mu = E(X) = \sum\limits x_ip(x_i)$, and the variance
$$\sigma^2 = \text{Var}(X) = \sum\limits (x_i - \mu)^2p(x_i) = \sum x_i^2p(x_i) - \mu^2$$

**Example**
Let $N =$ the number of interviews a student has prior to getting a job, having the PMF
$$p(x) = \Bbb{P}(N=x) = \frac{k}{x^2}, x = 1,2,3,...$$
where $k$ is a known constant. Find $E(N)$.

*Solution*:

$$E(N) = \sum\limits_{x=1}^\infty x \frac{k}{x^2} = k \sum\limits_{x=1}^\infty \frac{1}{x} = \infty (\text{harmonic series})$$

This distribution is known as having a "heavy tail" (power law of distribution)

### **Probability Density Function**

> **Probability Density Function (PDF)**
> $f(x)$ describes the probability density of a continuous $RV$ $X$ at $x$.
> 1. $f(x) \ge 0$
> 2. $\int_{-\infty}^\infty f(x)dx = 1$
> 3. $\Bbb{P}(a < x < b) = \int_a^b f(x) dx = \text{ the area under }f(x) \text{ between }a \text{ and }b$


- PDF describes relative frequency of a continuous random variable $X$.
- $\Bbb{P}(X = a) = 0$
- $\Bbb{P}(a \le X \le b) = \Bbb{P}(a < X \le b) = \Bbb{P}(a \le X < b) = \Bbb{P}(a < X < b)$ (The boundary points don't matter in continuous case)

![[Week 3 2025-09-04 13.56.17.excalidraw]]

### **Cumulative Frequency**

>**Cumulative Distribution Function (CDF) of X**
>$$F(x) = \Bbb{P}(X \le x) = \int_{-\infty}^x f(u)du$$

1. $F(x)$ is non-decreasing
2. $0 \le F(x) \le 1$
3. $F(x) \to 0$ as $x \to -\infty$
4. $F(x) \to 1$ as $x \to +\infty$
5. $\lim\limits_{h \to 0} F(x + h) = F(x)$, i.e. $F(x)$ is continuous.

>**Example**
>Consider the PDF of the uniform RV over $[a,b]$
>$$f(x) = \frac{1}{b-a}, a \le x \le b$$
>and zero otherwise. Find the CDF
>- $F(x) = \int_{a}^x \frac{1}{b-a}du = \frac{x-a}{b-a}, a \le x \le b$
>- $F(x) = 0$, $x < a$
>- $F(x) = 1$, $b < x$