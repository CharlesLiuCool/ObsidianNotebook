### **Transformation of One Variable**

Suppose that $X$ is a continuous random variable with PDF $f(x)$ and that $Y=r(X)$ is a continuous random variable with PDF $g(y)$.

Assume that $Y = r(X)$ defines a one-to-one transformation $S = \{x|f(x) > 0\}$ on to $T = \{y|g(y) > 0\}$ with inverse transformation $x = r^{-1}(y)$.

- the forward: $y = r(x): S \to T$
- the inverse: $x = r^{-1}(t): T \to S$

*Idea:* Two differentials $g(y)|dy|$ and $f(x)|dx|$ should be "approximately the same":
$$g(y)|dy| \approx f(x)|dx|$$

>**Transformation Theorem: Continuous Case**
>If the derivative $dr^{-1}(y)/dy$ is continuous and nonzero on $T$ then the PDF of $Y$ is
>$$g(y) = f(x) \left|\frac{dx}{dy}\right| = f(r^{-1}(y)) \left|\frac{dr^{-1}(y)}{dy}\right|$$

### **Example**

Consider a random variable $X$ with PDF $f_X(x) = \lambda e^{-\lambda x}$ for $0 < x < \infty$; zero otherwise. Let $Y = e^x = r(X)$, and find the PDF of $Y$.

1. $x = r^{-1}(y) = \log(y)$, and $dr^{-1}(y)/dy = 1/y$
2. The PDF of $Y$:
$$g(y) = f(r^{-1}(y))\left|\dfrac{dr^{-1}(y)}{dy}\right| = \lambda e^{-\lambda \log y} y^{-1} = \lambda y^{-\lambda - 1}$$
where $1 < y < \infty$.

### **Example**

Consider a standard normal  random variable $Z$ with PDF $f_Z(z) = (2\pi)^{-1/2}e^{-z^2/2}$ for $-\infty < z < \infty$. Let $Y = Z^2 = r(Z)$, and find the PDF of $Y$.

Consider two pieces: $Z > 0$ and $Z < 0$
1. For $Z > 0$, $z = r^{-1}(y) = \sqrt{y}$ and
$$\dfrac{dr^{-1}(y)}{dy} = \dfrac{1}{2\sqrt{y}}$$

2. For $Z < 0$, $z = r^{-1}(y) = -\sqrt{y}$

$$\dfrac{dr^{-1}(y)}{dy} = -\dfrac{1}{2\sqrt{y}}$$

Each value $y$ corresponds to two values $z = \sqrt{y}$ and $-z=-\sqrt{y}$. That is,
$$g(y) = f(-\sqrt{y}) \left| \dfrac{dr^{-1}}{dy} \right| + f(\sqrt{y}) \left| \dfrac{dr^{-1}}{dy} \right|$$

$$g(y) = (2\pi)^{-1/2} e^{-y/2}\frac{1}{2\sqrt{y}} + (2\pi)^{-1/2} e^{-y/2} \frac{1}{2\sqrt{y}}$$
for $0 < y < \infty$.
The distribution of $Y$ is known as the $\chi^2$ distribution.

### **Transformation of Multiple Variables**

Suppose that $X = (X_1,X_2,...,X_k)$ is a vector of continuous random variables with joint PDF $f(x_1,x_2,...,x_k) > 0$.

- $Y = (Y_1,Y_2,...,Y_k)$ is defined by the one-to-one transformation

$$\begin{align}Y_1 &= u_1^{-1}(X_1,X_2,...,X_k) \\ &...,\;...,\;... \\ Y_k &= u_k^{-1}(X_1,X_2,...X_k)\end{align}$$


- The inverse transform:
$$\begin{align}X_1 &= u_1^{-1}(Y_1,Y_2,...,y_k) \\ &...,\;...,\;... \\ X_k &= u_k^{-1}(Y_1,Y_2,...Y_k)\end{align}$$

### **Transformation of Multiple Variables**

Define the *Jacobian* as the determinant of the $k \times k$ matrix of the partial derivative for the diverse transform

>*Idea:*
>$$f_Y(y_1,...,y_k)dy \text{ and }f_X(x_1,...,x_k)dx$$
>should be of the same order

>**Transformation Theorem: Continuous Case**
>Suppose that $X = (X_1,X_2,...X_k)$ is a vector of continuous random variable with joint PDF $f(x_1,x_2,...,x_k) > 0$. We have 
>- the forward $Y_i = u_i(X_1,X_2,...,X_k),\;i = 1,2,...,k$
>- the inverse $X_i = u_i^{-1}(Y_1,Y_2,...,Y_k),\;i = 1,2,...,k$
>If the Jacobian of the inverse is continuous and nonzero over the range of the transformation, then the joint PDF of $Y$ is
>$$f_Y(y_1,...,y_k) = f_X(x_1,...,x_k)|J|$$

### **Example**

The vector $(X,Y)$ has the joint PDF
$$f(x,y) = \begin{cases} 2 & \text{if }0 \le x \le 1 \text{ and }x + y \le 1 \\ 0 & \text{otherwise}\end{cases}$$

What about the distribution of $W = X+Y$?
1. Consider the transform: $V = X$, $W = X +Y$
2. The inverse: $X = V, Y = W - V$
3. The Jacobian of the inverse:
$$J = \begin{vmatrix} 1 & 0 \\ -1 & 1 \end{vmatrix} = 1$$
4. The joint PDF of $(V,W)$ is given by
$$f_{(V,W)}(v,w) = f(x,y) \times 1 = 2$$
for $0 < v < w < 1$
5. The PDF of $W$ is the marginal PDF of $W$:
$$f_W(w) = \int_0^w 2dv = 2w$$
for $0 < w < 1$


>**Idea: A Convolution Formula for $X_1 + X_2$**
>- Using the total probability law, we have the CDF of $S$:
>$$\begin{align}\Bbb{P}(X_1 + X_2 \le s) &= \int_{-\infty}^\infty \Bbb{P}(X_1 + X_2 \le s | X_2 = t)f_2(t) dt \\ &= \int_{-\infty}^\infty \Bbb{P}(X_1 \le s-t |X_2 = t) f_2(t)dt \\ &= \int_{-\infty}^\infty \Bbb{P}(X_1 \le s-t)f_2(t)dt \end{align}$$
>- The PDF of $S$:
>$$f_S(s) = \int_{-\infty}^\infty f_1(s-t)f_2(t)dt = \int_{-\infty}^\infty f_1(t)f_2(s-t)dt$$

### **The MGF Method**

>**Theorem**
>If $X_1,...,X_k$ are independent random variables with MGFs $M_{X_i}t$, $i = 1,...,k$, then the MGF of $Y = \sum\limits_{i=1}^kX_i$ is
>$$M_Y(t) = M_{X_i}(t) M_{X_2}(t)...M_{X_k}(t)$$
>In particular, if $X_1,...,X_k$ are independent, identically distributed random variables with MGF $M(t)$, then the MGF of $Y$ is
>$$M_Y(t) = [M(t)]^k$$

*Proof:*
Observe that $e^{tY} = e^{t \sum\limits_{i=1}^kX_i} = e^{\sum\limits_{i=1}^ktX_i} = e^{tX_1}e^{tX_2}...e^{tX_k}$, and thus we have
$$\begin{align} M_Y(t) &= E(e^{tY}) = E[e^{tX_1}e^{tX_2}...e^{tX_k}] \\ &= E[e^{tX_1}]E[e^{tX_2}]...E[e^{tX_k}] \\ &= M_{x_1}(t)M_{x_2}(t).... M_{x_k} (t)\end{align}$$


*Remark*
Assume that random variables are independent.
- $X_i \sim \text{Poisson}(\mu_i), i = 1,...,k$, imply that
$$Y = \sum\limits_{i=1}^k X_i \sim \text{Poisson}\left(\sum\limits_{i=1}^k \mu_i\right)$$
- $X_i \sim N(\mu_i, \sigma^2_i), i = 1, ..., l$, imply that
$$Y = \sum\limits_{i=1}^k X_i \sim N\left(\sum\limits_{i=1}^k \mu_i, \sum\limits_{i=1}^k \sigma_i^2\right)$$
- $X_i \sim \text{Geo}(p), i = 1,...,k$ imply that
$$Y = \sum\limits_{i=1}^k X_i \sim \text{Geo}(kp)$$