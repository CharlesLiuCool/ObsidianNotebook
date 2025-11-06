> **Conditional Density (Mass) Functions**
> If the pair $(X_1, X_2)$ of random variables has the joint PDF $f(x_1,x_2)$, then the conditional density (mass) function given that $X_1 = x_1$ is defined as
> $$f(x_2|x_1) = \frac{f(x_1,x_2)}{f_1(x_1)}, f_1(x_1) > 0$$
> and zero otherwise.


*Remarks*
- For fixed $x_1$, $f(x_2 | x_1)$ is a density (mass) function of $X_2$ given that $X_1 = x_1$.
- In the continuous case,
$$P(a \le X_2 \le b\;|\;X_1 = x_1) = \int_a^b f(x_2 | x_1) dx_2 = \frac{\int_a^b f(x_1,x_2)dx_2}{f_1(x_1)}$$
- $X_1$ and $X_2$ are independent if and only if
$$f(x_2|x_1) = f_2(x_2) \iff f(x_1, x_2) = f_1(x_1)f_2(x_2)$$
for all values.
- If $f_1(x_1) = 0$ then the conditional density (mass) function can be defined by using the Radon-Nikodym derivative from measure theory.

Let $X_1$ and $X_2$ be continuous random variables with a joint PDF of the form
$$f(x_1, x_2) = 3(x_1 + x_2), 0 \le x_1,x_2\le 1, x_1+x_2 \le 1$$
and zero otherwise.

- The marginal PDF of $X_1$ is given by, for $0 < x_1 < 1$
$$f_1(x_1) = \int_0^{1-x_1} 3(x_1 + x_2)dx_2 = [3x_1x_2 + \frac{3}{2}x_2^2]\bigg|_0^{1-x_1} = \frac{3}{2} (1- x_1^2)$$

- The conditional PDF of $X_2$ given that $X_1 = x_1$, $0 < x_1< 1$ is given by
$$f(x_2 | x_1) = \frac{2(x_1+x_2)}{1-x_1^2}, 0 \le x_1,x_2 \le 1, x_1 + x_2 \le 1$$
and zero otherwise.

>**Expectations**
>If $X = (X_1,...,X_k)$ has a joint PDF $f(x_1, ..., x_k)$ and if $Y = u(X_1, ..., X_k)$ is a function of $X$, then the expectation $E(Y) = E[u(X_1,...,X_k)]$ is defined as
>$$E[u(X_1,...,X_k)] = \int_{-\infty}^\infty ... \int_{-\infty}^\infty u(x_1,...,x_k)\underbrace{ f(x_1,...,x_k) dx_1 ... dx_k}_{\text{probability mass near }x}$$
>If $X$ is continuous, and
>$$E[u(X_1,...,X_k)] = \sum\limits_{-\infty}^\infty ... \sum\limits_{-\infty}^\infty u(x_1, ..., x_k) f(x_1,...,x_k),$$
>if $X$ is discrete.

The function $u$ could be any function such as
$$u(x_1,...,x_k) = \sum\limits_{i=1}^k x_i^2, u(x_1,...,x_k) = \max\{x_1,...x_k\}$$

If $u(x_1,...,x_k) = x_i$, $1 \le i \le k$, then we have the mean value $E(X_i) = E[u(X_1,...,X_k)]$.

If $u(x_1,...,x_k) = (x_i - E(X_i))^2$, then we have the variance $\text{Var}(X_i) = E[u(X_1,...,X_k)]$.

### **Expectation is Linear**

>**Theorem**
>- $E[X_1 + ... + X_k] = E[\sum\limits_{i=1}^k X_i] = \sum\limits_{i=1}^k E(X_i)$
>- $E[\sum\limits_{i=1}^k a_iX_i] = \sum\limits_{i=1}^k a_i E(X_i)$.

*Proof:* Consider the continuous case of $k=2$. Let $(X_1, X_2)$ have the density $f(x_1, x_2)$, and

$$\begin{align} E(X_1 + X_2) &= \int \int (x_1 + x_2) f(x_1,x_2) dx_1 dx_2 \\ &= \int \int x_1f(x_1,x_2) dx_1 dx_2 + \int \int x_2 f(x_1,x_2)dx_1 dx_2 \\ & = \int x_1 \left[\int f(x_1,x_2)dx_2 \right] dx_1 + \int x_2 \left[\int f(x_1,x_2)dx_1 \right]dx_2\\ &= \int x_1 f_1(x_1) dx_1 + \int x_2 f_2(x_2) dx_2 \\ &= E(X_1) + E(X_2)\end{align}$$

### **Independence**

>**Theorem**
>$X_1,...,X_k$ are independent if and only if
>$$E\left[\prod_{i=1}^ku_i(X_i) \right] = \prod_{i=1}^k E[u_iX_i]$$

*Proof:* Consider the continuous case of $k=2$. Let $(X_1, X_2)$ have the density $f(x_1 + x_2)$, and

$$\begin{align}
E[u_1(X_1)u_2(X_2)]
&= \int \int u_1(x_1) u_2(x_2) f(x_1,x_2) dx_1dx_2
\\ &= \int \int u_1(x_2) u_2(x_2) f_1(x_1) f_2(x_2) dx_1 dx_2
\\ &= \int u_1(x_1) f_1(x_1)dx_1 \int u_2(x_2) f_2(x_2)dx_2 = E(u_1(X_1))E(u_2(X_2))
\end{align}$$

*Remarks*
- If $X$ and $Y$ are independent, then
$$E(XY) - E(X)E(Y) = 0$$
- Let $\mu_x = E(X)$ and $\mu_Y = E(Y)$. If $X$ and $Y$ are independent, then
$$\begin{align}
E[(X - \mu_x)(Y - \mu_Y)] &= [E(X - \mu_x)][E(Y - \mu_Y)] \\ &= [E(X) - \mu_x] [E(Y) - \mu_Y] = 0 \end{align}$$

___

### **Covariance**

>**Definition**
>The covariance of two random variables $X$ and $Y$ is defined by
>$$\sigma_{XY} := \text{Cov}(X,Y) = E[(X - \mu_x)(Y - \mu_Y)]$$
>where $\mu_X = E(X)$ and $\mu_Y = E(Y)$

*Remarks:*
- $\begin{align} \text{Cov}(X,Y) &= E[XY - X\mu_Y - \mu_XY + \mu_X\mu_Y] \\ &= E(XY) - E(X){\mu_Y} - \mu_XE(Y) + \mu_X\mu_Y \\ &= E(XY) - E(X)E(Y)\end{align}$
- $\text{Cov}(aX+b, cY+d) = ac \text{Cov}(X,Y)$ for all constants $a,b,c,d$.
- If $X$ and $Y$ are independent, then $\text{Cov}(X,Y) = 0$. The converse is *NOT* true.

___

### **Example**

Let $X$ be uniformly distributed on $[-1,1]$; that is, $f_x(x) = \frac{1}{2}$ if $-1 \le x \le 1$ and zero otherwise. Also let $Y = X^2$. Obviously $X$ and $Y$ are not independent.

However, since $E(X) = 0$ and $E(X^3) = 0$, we have
$$\begin{align}
&\text{Cov}(X,Y) = E(XY) - E(X)E(Y)
\\ E(X&^3) - E(X)E(X^2) = 0 - 0E(X^2) = 0
\end{align}$$

___

### **Second Order Property**

>**Theorem**
>$\text{Var}(a_1X_1 + a_2X_2) = a_1^2 \text{Var}(X_1) + a_2^2 \text{Var}(X_2) + 2a_1a_2\text{Cov}(X_1,X_2)$

>*Proof:* Let $\mu_1 = E(X_1)$ and $\mu_2 = E(X_2)$. Then
>$$\begin{align}
>\text{Var}(a_1X_1 + a_2X_2) &= E[(a_1X_1 + a_2X_2) - E(a_1X_1 + a_2X_2)]^2 \\
>&= E[(a_1X_1 + a_2X_2) - a_1\mu_1 - a_2\mu_2]^2 \\ &= E[a_1(X_1 - \mu_1) + a_2(X_2 - \mu_2)]^2
>\\ &= a_1^2 E[X_1 - \mu_1]^2 + a_2^2 E[X_2-\mu_2]^2 + 2a_1a_2 E[(X_1 - \mu_1)(X_2 - \mu_2)] \\ &= a_1^2 \text{Var}(X_1) + a_2^2 \text{Var}(X_2) + 2a_1a_2 \text{Cov} (X_1, X_2)\end{align}$$

*Remarks*

- $\text{Var}(\sum\limits_{i=1}^k a_iX_i) = \sum\limits_{i=1}^k a_i^2 \text{Var}(X_i) + 2 \sum\limits_{i<j} a_ia_j \text{Cov}(X_i, X_j)$
- If $X_i,...,X_k$ are independent, then
$$\text{Var}\left(\sum\limits_{i=1}^k a_iX_i\right) = \sum\limits_{i=1}^k a_i^2 \text{Var}(X_i)$$

___


### **Binomial Mean $Y \sim \text{Bin}(n,p)$**

- The PMF of $Y$:
$$p(y) = \binom{n}{y} p^y (1-p)^{n-y}, y=  0,1,...,n$$
- $E(Y) = np$
*Proof:*
Write
$$Y = \sum\limits_{i=1}^n Y_i$$
where $Y_i =$ outcome ($0$ or $1$) resulted from the $i$-th Bernoulli trial. We have
$$E(Y) = \sum\limits_{i=1}^n E(Y_i) = nE(Y_i) = np$$


### **Binomial Variance**
- $\text{Var}(Y) = np(1-p)$

*Proof:*
Write
$$Y = \sum\limits_{i=1}^n Y_i$$
where $Y_i =$ outcome ($0$ or $1$) resulted from the $i$-th Bernoulli trial. Noticing that $Y_1,...,Y_n$ are independent, we have
$$\text{Var}(Y) = \sum\limits_{i=1}^n \text{Var}(Y_i) = n\text{Var}(Y_i) = np(1-p)$$