### **Mean and Variance**

- *Mean* of a continuous random variable $X$
$$E(X) = \mu = \int_{-\infty}^\infty xf(x)dx = \int_{-\infty}^\infty x \underbrace{f(x) dx}_{\text{prob. mass at }x}$$

- *Variance* of a continuous random variable $X$
$$\text{Var}(X) = \sigma^2 = \int_{-\infty}^\infty (x - \mu)^2 \underbrace{f(x)dx}_{\text{prob. mass at }x}$$

- *Standard Deviation* of $X$: $\sigma = \sqrt{V(X)}$
$$\sigma^2 = \int_{-\infty}^\infty x^2f(x)dx - \mu^2$$


### **The 100$p$-th Percentile**

Let $0 < p < 1$ be given
- The *100$p$-th percentile* of a continuous random variable $X$ is the threshold $t_p$ such that
$$\Bbb{P}(X \le t_p) = \int_{-\infty}^{t_p} f(u)du = p$$
- *Median* of a continuous random variable $X$ is the $50$-th percentile

### **Expectations**

>**Definition** Expected Value
>If $X$ is a random variable and $u(x)$ is a real-valued function
>- $E(u(X)) = \sum u(x_i)p(x_i)$, if $X$ is discrete
>- $E(u(X)) = \int_{-\infty}^\infty u(x)f(x) dx$, if $X$ is continuous

>**Theorem** A Linear Property
>If $X$ is a random variable, and $g(x), h(x)$ are real-valuedfunctions, then
>$$E(ag(X)+bh(X)) = aE(g(X)) + bE(h(X))$$
>for any two constants $a, b$

Take $u(x) = x$, we have the mean value $\mu = E(X)$
Take $u(x) = (x - \mu)^2$, we have the variance $\sigma^2 = \text{Var}(X) = E(X - \mu)^2$
Take $u(x) = (x - \mu)^k$, we have the $k$-th *central moment* $\mu_k = E[(X - \mu)^k]$
Take $u(x) = x^k$, we have the $k$-th *moment* $\mu_k' = E(X^k)$



1. $E(aX + b) = aE(X) + b$
2. $\text{Var}(aX + b) = a^2\text{Var}(X)$
3. $E(X^2)$ = $\sigma^2$ + $\mu^2$
4. If $X$ is symmetric about the mean $\mu$, then $\mu_3 = 0$

### **Bounds on Tail Properties**

>**Theorem** A Concentration Inequality
>If $X$ is a random variable and $u(x)$ is a non-negative real-valued function, then for any constant $a > 0$,
>$$\Bbb{P}(u(X) \ge a \le \frac{E(u(X))}{a}$$

*Proof:*
Let $A = \{x \,|\, u(x) \ge a\}$ be a subset with $A \cup A' = \Bbb{R}$. Then for a continuous random variable $X$ with PDF $f(x)$,

$$\begin{align} E(u(X))  &= \int_{\infty}^\infty u(x)f(x) dx \\ &= \int_A u(x)f(x)dx + \int_{A'} u(x)f(x)dx \\ &\ge \int_{\{x\,|\,u(x) \ge a\}}u(x)f(x)dx \ge \underbrace{a\int_{\{x\,|\,u(x) \ge a\}}f(x)}_{\Bbb{P}(A)} \\ &= a \Bbb{P}(u(X) \ge a)\end{align}$$

### **Special Cases**

- *Markov's Inequality*: Take $u(x) = |x|^k$ and $a = c^k$ for any $k > 0$, then we have
$$\Bbb{P}(|X| \ge c) = \Bbb{P}(|X|^k \ge c^k) \le \frac{E|X|^k}{c^k}, \;c > 0$$

![[Week 4 2025-09-11 13.33.21.excalidraw]]

- *Chebyshev's Inequality*: Take $u(x) = (x - \mu)^2$ and $a = k^2\sigma^2 = k^2E(X - \mu)^2$, then we have
$$\Bbb{P}(|X - \mu| \ge k\sigma) = \Bbb{P}(|X - \mu|^2 \ge k^2\sigma^2)$$

![[Week 4 2025-09-11 13.34.46.excalidraw]]

Set $\epsilon := k\sigma$. Note that $k = \epsilon/\sigma$.
Chebyshev's Inequality is often written as
$$\Bbb{P}(|X - \mu| \ge \epsilon) \le \frac{\sigma^2}{\epsilon^2}, \epsilon > 0$$


Let $X$ be a random variable with mean $\mu$ and variance $\sigma^2$. If $\sigma^2 = 0$, then $\Bbb{P}(X = \mu) = 1$

In fact, consider,
$$\{X \neq \mu\} = \bigcup\limits_{i=1}^\infty \left\{|X - \mu| \ge \frac{1}{i}\right\}$$

It follows from Boole's inequality and Chebychev's inequality that
$$\Bbb{P}(X \neq \mu) \le \sum\limits_{i = 1}^\infty \Bbb{P}(|X - \mu| \ge 1/i) \le \sum\limits_{i=1}^\infty i^2 \sigma^2 = 0$$

which implies that $\Bbb{P}(X = \mu) = 1$

### **Moment Generating Functions**

>**Definition**
>The moment generating function (MGF) of a random variable is defined as
>$$M_x(t) = E(e^{tX}),$$
>if this expected value exists for all values of $t$ in some interval of the form $-h < t < h$ for some $h > 0$

If you change the value of $t$ to negative, you get the *Laplace transform*

**Theorem** Generating all the moments
If the moment generating function of $X$ exists, then
$$E(X^k) = M_X^{(k)}(0), k = 1,2,...$$

*Proof:*

Let $X$ be continuous with PDF $f(x)$. Consider
$$M_x(t) = \int_{-\infty}^\infty e^{tx}f(x)dx$$

Take the derivative with respect to $t$, and we have
$$M_x'(t) = \int_{-\infty}^\infty xe^{tx}f(x) dx$$


Take the derivative again, and up to the $k$th order, and we have
$$M_x^{(k)} = \int_{-\infty}^\infty x^ke^{tx} f(x) dx,\;k = 1,2,...$$

That is $$M_x^{(k)}(0) = \int_{-\infty}^\infty x^ke^0f(x) dx = E(X^k)$$

___

*Remark*

Using Taylor series expansions, we have
$$e^{tx} = \sum\limits_{k = 0}^\infty \frac{x^kt^k}{k!}, x \in \Bbb{R}$$

Therefore,
$$\begin{align} M_x(t) &= \int_{-\infty}^\infty e^{tx}f(x)dx \\ &= \int_{-\infty}^\infty \sum\limits_{k=0}^\infty \frac{x^kt^k}{k!}f(x)dx \\ &= \sum\limits_{k=0}^\infty \int_{-\infty}^\infty \frac{x^kt^k}{k!}f(x) dx \\ &= \sum\limits_{k=0}^\infty \frac{t^k}{k!} \int_{-\infty}^\infty x^kf(x)dx \\ &= \sum\limits_{k=0}^\infty \frac{t^k}{k!}E(X^k)\end{align}$$

### **Poisson MGF**

A discrete random variable $X$ is said to have Poisson distribution with parameter $\mu > 0$ if it has discrete PDF
$$f(x) = \frac{e^{-\mu}\mu^x}{x!}, x = 0,1,2,...$$
So $\sum\limits_{x=0}^\infty \frac{e^{-\mu}\mu^x}{x!} = 1 \iff \sum\limits_{x=0}^\infty \frac{\mu^x}{x!} = e^\mu$ for any $\mu > 0$

Its MGF is given by
$$M_x(t) = \sum\limits_{x = 0}^\infty e^{tx}\frac{e^{-\mu}\mu^x}{x!} = e^{-\mu}\sum\limits_{x = 0}^\infty \frac{e^{tx}\mu^x}{x!} = e^{-\mu} \sum\limits_{x = 0}^\infty \frac{(e^t\mu)^x}{x!} = e^{-\mu}e^{e^t\mu} = e^{\mu(e^t - 1)}$$

Therefore, $E(X) = M_x'(0) = \mu$

### **Properties of MGF**

1. If $Y = aX + b$, then $M_y(t) = e^{bt}M_x(at)$
2. If $X_1$ and $X_2$ have respective CDFs $F_1(x)$ and $F_2(x)$ and MGFs $M_1(t)$ and $M_2(t)$, then
$$F_1(x) = F_2(x)\;\text{for all real }x \iff M_1(t) = M_2(t)$$
for all $t$ in some interval $-h < t < h$ for some $h > 0$

*Proof*
1. We can find
$$M_Y(t) = E(e^{tY}) = E(e^{t(aX+b)}) = E(e^{taX}e^{tb}) = e^{tb}M_x(ta) $$
2. For any MGF $M(t) = E(e^{tX})$, $M(-t) = E(e^{-tX})$ is known as the Laplace transform of $X$. The result follows immediately by using the inverse Laplace transform

Consider a continuous random variable $X$ with PDF $g(x) = e^{-x}$ for $x \ge 0$ and zero otherwise. The MGF is 
$$M_x(t) = \frac{1}{1-t}, t < 1$$

Consider $Y = X/\lambda$. Since
$$M_x(t) = \frac{1}{1-t}$$
$$M_y(t) = M_x(t/\lambda) = \frac{1}{1 - t/\lambda} = \frac{\lambda}{\lambda - t}, \; t/\lambda < 1$$
resulting that
$$M_y(t) = \frac{\lambda}{\lambda - t}, t < \lambda$$
The random variable $Y$ is known to have the exponential distribution with parameter $\lambda$.


