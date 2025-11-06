### **Binomial Experiment (Jacob Bernoulli, 1713)**

*Bernoulli Trial*: A trial with only two possible outcomes, a failure or a success (labeled a $0$ or $1$ respectively)

Bernoulli random variable $X$

$$\Bbb{P}(X = 1) = p,\;\Bbb{P}(X = 0) = 1 - p$$

$E(X) = 0 \times (1-p) + 1 \times p = p$
$\text{Var}(X) = 0^2 \times (1-p) + 1^2 \times p - p^2 = p(1-p)$

>**Binomial Experiment**
>1. The trials are independent
>2. Each trial results in one of two outcomes, labeled a "success (1)" or a "failure (0)"
>3. Each trial has success probability $p$ and failure probability $1-p$

### **Binomial Distribution**

- *Binomial random variable $Y$*: the number of successes during the $n$ trials
- *Binomial coefficient*: $\binom{n}{y} =$ number of ways to select $y$ numbers from $1,...,n$
- $\Bbb{P}(Y = y) = \binom{n}{y}$ $\Bbb{P}(\text{sequence of }y\text{ ones and }n-y\text{ zeroes})$
- The PMF of $Y$ (denoted by $Y\sim \text{Bin}(n,p)$):
$$p(y) = \binom{n}{y} p^y (1-p)^{n-y}, \; y = 0,1,...,n$$
- *MGF*: $M_Y(t) = (pe^t + q)^n, \;q = 1-p$. In fact
$$M_Y(t) = \sum\limits_{x = 0}^n e^{tx}\binom{n}{x}p^xq^{n-x} = \sum\limits_{x=0}^n \binom{n}{x} (e^tp)^xq^{n-x} = (pe^t + q)^n$$
- $E(Y) = M'_Y(0) = np$, $\text{Var}(Y) = M_Y''(0) -(np)^2 = np(1-p)$

### **Negative Binomial Distribution**
- *Negative Binomial random variable $Y$*: the number of Bernoulli trials to obtain $r$ successes ($r \ge 1$ is fixed). Obviously, $Y \ge r$.
- When $r=1$, that is the *geometric distribution*
- The number of ways to select $r-1$ successes from $\{1,...,y-1\}$
$$\binom{y-1}{r-1} = \frac{(y-1)!}{(y-r)!(r-1!)}$$
- Let $p(y) = \Bbb{P}(Y = y), y \ge r$
$$p(y) = \binom{y-1}{r-1}\Bbb{P}((y-r) 0\text{'s and }r 1\text{'s, ended with }1)$$
- The PMF of $Y$ (denoted by $Y \sim NB(r,p)$):
$$p(y) = \binom{y-1}{r-1}p^r(1-p)^{y-r},\;y = r,r+1 ...$$

Suppose $X \sim \text{Bin}(n,p)$ and $Y \sim NB(r,p)$.
$\{X \ge r\} = \{\text{need }r\text{or more }1's\}$
$\Bbb{P}(Y \le n) = \Bbb{P}(X \ge r) = 1 - B(r-1;n,p)$

### **Geometric Distribution**

- *Geometric random variable $Y$*: The number of trials required to obtain success ($r = 1$)
- The PMF of $Y$ denoted by $Y \sim \text{Geo}(p)$
$$p(y) = p(1-p)^{y-1},\;y=1,2,...$$

### **MGF of Geometric Distribution**

- MGF is $\frac{e^tp}{1-e^tq}$

___

### **Poisson Distribution**

A discrete random variable $X$ with PMF $(X \sim Poi(\mu))$
$$f(x) = \frac{e^{-\mu}\mu^x}{x!}, x = 0,1,2$$
is said to have a Poisson distribution with parameter $\mu$.

Observe that $\sum\limits_{x=0}^\infty \frac{e^{-\mu}\mu^x}{x!} = 1 \iff \sum\limits_{x = 0}^\infty \frac{\mu^x}{x!} = e^\mu$


### **MGF of Poisson Distribution**

- Suppose that $X \sim Poi(\mu)$, and then $MGF M_x(t) = e^{\mu(e^t - 1)}$
- In fact,
$$\begin{align}
M_X(t) &= E[e^{tX}] = \sum_{x=0}^\infty e^{tx} \frac{e^{-\mu} \mu^x}{x!} \\
&= e^{-\mu} \sum_{x=0}^\infty \frac{(\mu e^t)^x}{x!} \\
&= e^{-\mu} \, e^{\mu e^t} \\
&= e^{\mu (e^t - 1)}
\end{align}$$

### **Law of Rare Events**

Suppose $n$ is sufficiently large, and $p$ is sufficiently small, and $\mu = np$ is fixed
$\lim\limits_{n\to\infty}\binom{n}{x} p^x(1-p)^{n-x} = \frac{e^{-\mu}\mu^x}{x!}$, for any $x = 0, 1,...,n$

Since $p$ is small, the event of "success" is considered as a rare event (extreme event). The examples includes defects, failures, ..

*Proof:*

Consider under the constraint that $\mu = np$, for any fixed $x$,
$$\begin{align} \binom{n}{x}p^x(1-p)^{n-x} &= \frac{n!}{x!(n-x)!}(\frac{\mu}{n})^x(1-\frac{\mu}{n})^{n-x} \\ \\ &= \frac{n(n-1)...(n-x+1)}{x!} \left(\frac{\mu}{n}\right)^x \left(1-\frac{\mu}{n}\right)^{n-x} \\ &= \frac{\mu^x}{x!}(1-\frac{\mu}{n})^n(1-\frac{\mu}{n})^{-x}(\frac{n}{n})(\frac{n-1}{n})...(\frac{n-x+1}{n})\end{align}$$
Since $\lim_{n \to \infty} (1-\frac{\mu}{n})^n = e^{-\mu}$, we have
$$\lim_{n \to \infty} \binom{n}{x}p^x(1-p)^{n-x} = \frac{\mu^x}{x!}e^{-\mu}$$

___

### **Poisson Counting Process of Random Events**

- The interval $[0,t]$ can be partitioned into $n$ subintervals of small length
- The probability that more than one event in a subinterval is zero
- The probability $p$ of one event in a subinterval is the same for all subintervals.
- The probability of one event in a subinterval is proportional to the length of the subinterval
- The events in different intervals are independent
- The total count $X_t$ of events by time $t$ is called a Poisson process
$$\Bbb{P}(X_t = x) = \frac{e^{-\mu t}(\lambda t)^x}{x!}, x= 0,1,2$$
where $E(X_t) = \lambda t \approx np$
- Let $T$ denote the time length from the starting point the first event. For any $t \ge 0$,
$$\Bbb{P}(T > t) = \Bbb{P}(X_t = 0) = \frac{e^{-\lambda t} (\lambda t)^0}{0!} = e^{-\lambda t}$$
That is, $T$ has the exponential distribution with rate $\lambda$.

___

### **Gamma Distribution**

- A random variable $X$ is said to have a *gamma distribution* (denoted by $X \sim Gam(\lambda, k)$) if its PDF
$$f(x) = \frac{\lambda^kx^{k-1}e^{-\lambda x}}{\Gamma(k)}, x > 0 \text{ where } \Gamma(k) = \int_0^\infty t^{k-1}e^{-t} dt$$
and $\Gamma(k)$ is known as the gamma function of $k$.

If $k$ is a positive integer, then the gamma function $\Gamma(k) = (k-1)!$
$k$ = shape parameter, $\lambda$ = rate parameter

### **MGF of Gamma Distribution**

Let $X \sim Gam(\lambda, k)$, then $MGF$: $M_x(t) = (1-t/\lambda)^{-k}, t < \lambda$

In fact, consider
$$M_x(t) = \int_{0}^\infty e^tx \frac{\lambda^kx^{k-1}e^{-\lambda x}}{\Gamma(k)} = \frac{\lambda^k}{\Gamma(k)} \int_0^\infty x^{k-1}e^{(t-\lambda)x} dx$$

The substitution $u = -(t-\lambda)x$ yields $x = (\lambda - t)^{-1}u$ and $dx = (\lambda - t)^{-1}du$. Therefore, for $t < \lambda$,

$$M_x(t) = \frac{\lambda^k}{\Gamma(k)} \int_{0}^\infty (\lambda - t)^{-(k-1)} u^{k-1} e^{-u} (\lambda - t)^{-1} du$$
$$(\lambda - t)^{-k} \frac{\lambda^k}{\Gamma(k)} \int_0^\infty u^{k-1} e^{-u} du = (\lambda - t)^{-k}\lambda^k = \left(1 - \frac{t}{\lambda}\right)^{-k}$$

$E(X) = \frac{k}{\lambda}$
$\text{Var}(X) = \frac{k}{\lambda}^2$

Let $g(x)$ is a non-negative bounded function on $\Bbb{R}$ such that $G = \int_{-\infty}^\infty g(x)dx < \infty$
$$f(x) = \frac{1}{G}g(x), x \in \Bbb{R}$$
is the PDF of a distribution

The gamma distribution is designed with $g(x) = x^{k-1}e^{-x}, x \ge 0$ by Paul Hoel. Hoel used the name "gamma distributions" because 
$$\int_{0}^\infty x^{k-1}e^{-x}dx$$
is the gamma function

$k$ = shape parameter, $\lambda$ = rate parameter, $\theta = \lambda^{-1}$ = scale parameter

A special case: When $k = n$ (integer), the distribution is called an *Erlang Distribution* 

___

### **Exponential Distribution**

$k = 1$: *Exponential distribution* ($X \sim Exp(\lambda))$. The pdf is given by $f(x) = \lambda e^{-\lambda x}, x\ge 0$

The CDF of the exponential is given by $F(x) = 1 - e^{-\lambda x}$

$E(X) = \frac{1}{\lambda}$, $\text{Var}(X) = \frac{1}{\lambda^2}$.

$X \sim Exp(\lambda)$ if and only if $\Bbb{P}(X > a + t | X > a) = \Bbb{P}(X > t)$

It follows because 

$$\begin{align} \Bbb{P}(X > a + t | X > a) &= \frac{\Bbb{P}(X > a + t \cap X > a)}{X > a} = \frac{\Bbb{P}(X > a + t)}{\Bbb{P}(X > a)} \\ & - \frac{e^{-\lambda(a + t)}}{e^{-\lambda a}} = e^{-\lambda t} = \Bbb{P}(X > t)\end{align}$$


Failure rate $h(x) = \frac{f(x)}{1 - F(x)} = \lambda$, a constant
In fact,
$$h(x) = \frac{f(x)}{1 - F(x)} = \frac{\lambda e^{-\lambda x}}{e^{-\lambda x}} = \lambda$$

___