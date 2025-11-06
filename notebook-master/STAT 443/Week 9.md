### **Conditional Expectations**

*Notation:* Let $(X,Y)$ have the joint PDF (PMF) $f(x,y)$ and marginals $f_x(x)$ and $f_y(y)$.
- The conditional random variable $Y|x$ has the PDF (PMF) $f(y|x)$
- $g(Y|x) = g(Y) | x$, for any function $g$.
	- For example, $(Y|x)^2 = Y^2 | x$

>**Definition**
>The conditional expectation of $Y$ given $X=x$ is given by
>$$\begin{align}E(Y|x) &= \sum\limits_{\text{all }y} yf(y|x), \text{if }X,Y\text{ are discrete}, \\ E(Y|x) &= \int_{-\infty}^\infty yf(y|x)dy, \text{ if }X,Y \text{ are continuous.}\end{align}$$


#### **Remarks**

- In general, the conditional expectation is defined as
$$E(g(X,Y)|x) = \sum\limits_{y}g(x,y)f(y|x) \;(\text{discrete})$$
$$E(g(X,Y)|x) = \int_{-\infty}^\infty g(x,y)f(y|x)dy \; (\text{continuous})$$
- The conditional variance of $Y$ given $X=x$ is defined as
$$\begin{align} \text{Var}(Y|x) &= E[(Y|x) - E(Y|x)]^2 = E\{[|Y-E(Y|x)]^2|x\} \\ &= E(Y|x)^2 - [E(Y|x)]^2 = E(Y^2|x)-[E(Y|x)]^2\end{align}$$
- If $X$ and $Y$ are independent random variables, then $f(y|x) = f_y(y)$ and $f(x|y) = f_x(x)$, and thus
$$E(Y|x) = E(Y), E(X|y) = E(X)$$
- Note that $h(x) := E(Y|x)$ is a function of $x$, and thus $h(X) = E(Y|X)$ is also a random variable (a function of random variable $X$)
- That is, one can compute expectations successively
$$E_X[E(Y|X)], \text{Var}_X[E(Y|X)]$$
etc.

___

### **Law of Total Expectation**

It is also known as the law of iterated expectations, the tower rule, the smoothing theorem, Adam's laws; etc.

>**Theorem**
>If $X$ and $Y$ are jointly distributed random variables, then
>1. $E(Y) = E_X[E(Y|X)]$
>2. $\text{Var}(Y) = E_X[\text{Var}(Y|X)] + \text{Var}_X[E(Y|X)]$

The second law is known as the *law of total variance*.

___

### **Properties of Conditional Expectations**

In general, let $h(x,y)$, and $g(x)$ be any (Borel-measurable) functions.

>**Theorem**
>If $X$ and $Y$ are jointly distributed random variables, then
>1. (the tower rule) $E(h(X,Y)) = E_x\{E[h(X,Y)|X]\}$;
>2. $E[g(X)Y|X] = g(X)E(Y|X)$. That is, $g(X)$ is known given the information on $X$.


*Proof:*
Only the continuous case is discussed
($1$) Consider
$$E[h(X,Y)|X=x] = E[h(x,Y)|X=x] = \int_yh(x,y)f(y|x)dy$$
Take another expectation (w.r.t $X$), we have
$$\begin{align}E_X\{E[h(X,Y)|X]\} &= \int_x\left(\int_y h(x,y)f(y|x)dy\right) f_x(x) dx \\ &= \int_x\int_y h(x,y) f(x,y) dy dx = E[h(X,Y)]\end{align}$$

($2$) Since
$$E[g(X)Y|X=x] = E[g(x)Y|X = x] = g(x) E[Y|X=x]$$
for all fixed value $x$, we then have
$$E[g(X)Y|X] = g(X)E(Y|X)$$

___

### **Binomial Distribution with Random Parameter**

*Randomization* for $Y \sim \text{BIN}(n,p)$: the parameter $p$ is a random variable.

- The PMF of $Y$:
$$p(y) = \binom{n}{y}p^y(1-p)^{n-y}, y = 0,1,...,n$$
- But the parameter $p$ is random with the following density function:
$$f(p) = 2p, 0 \le p \le 1$$
with 
$$E(p) = \int_0^1 pf(p)dp = \int_0^1 2p^2dp = \frac{2}{3}$$
- Observe that $E(Y|p) = np$
- $E(Y) = E_p[E(Y|p)] = E(np) = nE(p) = \frac{2n}{3}$

___

### **A Motivating Example**

>**Probability Integral Transformation**
>If $X$ is continuous with increasing CDF $F(x)$, then $U := F(X)$ has the standard uniform distribution on $(0,1)$.

___

### **The CDF Method**

Idea: The CDF involves inequalities, which are often "easier"

>**Theorem**
>Suppose that $X$ is a random variable with PDF $f_x(x)$ and $Y = u(X)$ for some real function $u(x)$.
>- The CDF $F_Y(y) = \Bbb{P}[u(X) \le y] = \Bbb{P}[X \in \{x|u(x) \le y\}]$,
>where
>$$\Bbb{P}(X \in A) = \Bbb{P}[X \in \{x|u(x) \le y\}] = \int_{\{x|u(x) \le y\}}f_X(x)dx$$
>- In the continuous case, the PDF $f_y(y)$ is given by
>$$f_Y(y) = \frac{d}{dy} F_Y(y)$$