**Charles Liu**
Dr. Haijun Li
$10/28/2025$

___

31. Let $X \sim \text{UNIF}(a,b)$. Derive the MGF of $X$.

First, note that

$$f_X(x) = \begin{cases} \frac{1}{b-a} & a \le x \le b \\ 0 & \text{otherwise}\end{cases}$$

Recall, for the continuous case, $$M_x(t) = E[e^{xt}] = \int_{-\infty}^\infty e^{tx}f(x)dx$$

We get $$\begin{align}M_x(t) &= \int_a^b e^{tx} \frac{1}{b-a}dx = \frac{1}{b-a}\int_a^b e^{tx}dx = \frac{1}{b-a} \frac{e^{tx}}{t}\bigg|_{x=a}^b = \frac{e^{tb}}{t(b-a)} - \frac{e^{ta}}{t(b-a)} \\ \\  &=\dfrac{e^{tb}-e^{ta}}{t(b-a)} \end{align}$$

___

34. Suppose a value $x$ is chosen "at random" in the interval $[0,10]$. In other words, $x$ is an observed value of a random variable $X \sim \text{UNIF}(0,10)$. The value $x$ divides the interval $[0,10]$ into two subintervals.

*a)* Find the CDF of the length of the shorter subinterval.

Length of the shortest subinterval, $S = \min(X, 10-X)$.

So $S \in [0,5]$

We find
$$\{S \le s\} = \{X \le s\} \cup \{X \ge 10 - s\}$$

When $s \in [0,5]$, $P(S \le s)$ is the sum of the probability of the two disjoint events $\{X \le s\}$  and $\{X \ge 10 - s\}$ occurring, or $s/5$.

Thus,


$$F_S(s) = \begin{cases} 0, & s < 0, \\ \frac{s}{5}, & 0 \le s \le 5, \\ 1, & s \ge 5 \end{cases}$$

*b)* What is the probability that the ratio of lengths of the shorter to the longer subinterval is less than $1/4$?

$P\left(\dfrac{S}{10-S} \le \dfrac{1}{4}\right) = P\left(S \le \dfrac{10-S}{4}\right) = P\left(\dfrac{5}{4}S \le \dfrac{5}{2}\right) = P(S \le 2) =\frac{2}{5} = 0.4$ 

___

35. Prove that $\Gamma(1/2) = \sqrt{\pi}$


We first find
$$\Gamma(1/2) = \int_{0}^\infty t^{-1/2}e^{-t}dt$$
We can first solve a double integral
$$\left[\Gamma\left(\frac{1}{2}\right)\right]^2 = \int_0^\infty \int_0^\infty 4 e^{-(x^2+y^2)}dxdy$$
Then do a polar substitution
$$x = r\cos\theta, y = r\sin\theta, dx\;dy = r\;dr\;d\theta$$
where $0 \le \theta \le \pi/2$, so we can solve
$$\begin{align}\left[\Gamma\left(\frac{1}{2}\right)\right]^2 &= 4\int_0^{\pi/2} \int_0^\infty e^{-r^2}rdrd\theta \\ &= \int_0^{\pi/2} -2e^{-r^2}\bigg|_{r=0}^\infty d\theta \\\\ &= \int_{0}^{\pi/2}2 d\theta \\ &=\pi\end{align}$$

Since $\left[\Gamma\left(\frac{1}{2}\right)\right]^2 = \pi$, we get
$$\Gamma\left(\frac{1}{2}\right) = \sqrt{\pi}$$

___

51. Suppose that $Z \sim N(0,1)$. Find the following probabilities:

*b)* $P(Z > -0.49)$
$$P(Z > -0.49) = 1 - P(Z < -0.49) = 0.6879$$
*c)* $P(0.35 < Z < 2.01)$
$$P(0.35 < Z < 2.01) = P(Z < 2.01) - P(Z < 0.35) = 0.9778 - 0.6368 = 0.341$$

Find the value $b$ such that
*f)* $P(|Z| < b) = 0.95$
$$P(|Z| < b) = P(Z < b) - P(Z < -b) = 0.95$$
since the normal distribution is symmetric,
$$P(Z < b) = P(Z < -b) = 0.025$$
so $b = 1.96$

___

52. Suppose that $X \sim N(3,0.16)$

*a)* $P(X > 3)$
Since $3$ is the mean of the normal distribution $X$,
$$P(X > 3) = 0.5$$

*c)* $P(2.8 \le X \le 3.1)$

$\sigma^2 = 0.16$
$\implies \sigma = 0.04$

We find that $\frac{3.1-3}{0.4} = 0.25$ and $\frac{2.8-3}{0.4} = -0.5$
$$\begin{align}P(2.8 \le X \le 3.1) &= P(-0.5 < Z < 0.25) \\ &= P(Z < 0.25) - P(Z < -0.5) \\ &= 0.5987 - 0.30854 = 0.29 \end{align}$$

*e)* Find the value $c$ such that $P(3-c < X < 3+c) = 0.9$

$\frac{(3+c)-3}{0.4} = \frac{c}{0.4}$
$\frac{(3-c)-3}{0.4} = -\frac{c}{0.4}$

$$P\left(-\frac{c}{0.4} < Z < \frac{c}{0.4}\right) = 0.9$$
Because $$P\left(Z > \frac{c}{0.4}\right) = P\left(Z < -\frac{c}{0.4}\right)$$ and 
$$P\left(Z > \frac{c}{0.4}\right) + P\left(Z > \frac{c}{0.4}\right) = 1 - 0.9 = 0.1$$
we find that $$P\left(Z > \frac{c}{0.4}\right) = P\left(Z < -\frac{c}{0.4}\right) = 0.05$$
Thus, we get that
$$\frac{c}{0.4} = 1.645$$
and
$$c = 0.658$$

___

14. Suppose the joint pdf of lifetimes of a certain part and a spare is given by
$$f(x,y) = e^{-(x+y)}\;0 < x < \infty, 0 < y < \infty$$
and zero otherwise. Find each of the following:

*a)* The marginal pdf's $f_1(x)$ and $f_2(y)$.

$$\begin{align}f_1(x) &= \int_{0}^\infty f(x,y)dy \\ &= \int_0^\infty e^{-(x+y)}dy  \\ &=-e^{-(x+y)}\bigg|_0^\infty \\ &=e^{-x},\;x > 0\end{align}$$

$$\begin{align}f_2(y) &= \int_{0}^\infty f(x,y)dx \\ &= \int_0^\infty e^{-(x+y)}dx  \\ &=-e^{-(x+y)}\bigg|_0^\infty \\ &=e^{-y},\;y > 0\end{align}$$

*b)* The joint CDF, $F(x,y)$

$$\begin{align}F(x,y) &= \int_0^x \int_0^y f(u,v)dvdu \\ &= \int_0^x \int_0^ye^{-(u+v)}dvdu \\ &=\int_0^x -e^{-(u+v)}\bigg|_{v=0}^ydu \\ &=\int_0^x\left(-e^{-(u+y)} + e^{-u}\right)du \\ &=\left(e^{-(u+y)}-e^{-u}\right)\bigg|_{u=0}^x \\ &=e^{-(x+y)} - e^{-x} -e^{-y}+1\end{align}$$

*c)* $P[X > 2]$

We find the marginal CDF of $X$, and input $2$:
$$P[X < 2] = F_X(2) = \int_0^2 e^{-x}dx = 1 - e^{-2}$$
So we get
$$P[X > 2] = 1 - F_X(2) = e^{-2}$$


___

18. Consider a pair of continuous random variables $X$ and $Y$ with a joint CDF of the form
$$F(x,y) = \begin{cases} 0.5xy(x+y) & \text{if } 0 < x < 1, 0 < y < 1 \\ 0.5x(x+1) & \text{if }0 < x < 1, 1 \le y \\ 0.5y(y+1) & \text{if }1 \le x, 0 < y < 1 \\ 1 & \text{if }1 \le x, 1 \le y \end{cases}$$

*a)* The joint pdf, $f(x,y)$

$$\frac{\partial}{\partial x}\frac{\partial}{\partial y} 0.5xy(x+y) = \frac{\partial}{\partial x}\frac{\partial }{\partial y} 0.5x^2y + 0.5xy^2 = \frac{\partial}{\partial x} 0.5x^2 + xy =x + y$$

$$\frac{\partial}{\partial x}\frac{\partial }{\partial y}(0.5x(x+1)) = 0$$

$$\frac{\partial}{\partial x}\frac{\partial }{\partial y}(0.5y(y+1)) = 0$$

$$\frac{\partial}{\partial x}\frac{\partial }{\partial y} 1 = 0$$

We then find the joint pdf
$$\begin{align}f(x,y) = \frac{\partial}{\partial x}\frac{\partial }{\partial y} \left( F(x,y)\right) &= \begin{cases} x + y & \text{if } 0 < x < 1, 0 < y < 1 \\ 0 & \text{if }0 < x < 1, 1 \le y \\ 0 & \text{if }1 \le x, 0 < y < 1 \\ 0 & \text{if }1 \le x, 1 \le y \end{cases} \\ \\ &= \begin{cases} x + y & \text{if } 0 < x < 1, 0 < y < 1 \\  0 & \text{ otherwise}\end{cases}\end{align}$$

*b)* $P[X \le 0.5, Y \le 0.5]$


$$P[X \le 0.5, Y \le 0.5] = F(0.5,0.5) = 0.5(0.5\cdot0.5)(0.5 + 0.5) = \frac{1}{8}$$

*c)* $P[X < Y]$

$$\begin{align} P[X < Y] &= \int_0^\infty \int_0^y f(x,y) \;dxdy \\ \\ &= \int_0^1 \int_0^y x+y  \;dxdy, 0 < y < 1 \\ \\ &= \int_0^1 \frac{x^2}{2} + xy \bigg|_{x = y} \;dy  \\ \\ &= \int_0^1 \frac{3y^2}{2} \;dy \\ \\ &= \frac{y^3}{2} \bigg|_0^1  = \frac{1}{2} \end{align}$$

___

20. Suppose that $X$ and $Y$ have the joint pdf
$$f(x,y) = 8xy, \; 0 \le x \le y \le 1$$
and zero otherwise. Find each of the following:

*a)* The joint CDF $F(x,y)$

$$\begin{align}F(x,y) &= \int_0^x\int_u^y8uv\;dvdu \\ &=\int_0^x 4uv^2\bigg|_{v=u}^ydu \\ &=\int_0^x 4uy^2 - 4u^3\;du \\ &=2u^2y^2 -u^4 \bigg|_{u=0}^x \\ &=2x^2y^2 - x^4, 0 \le x \le y \le 1\end{align}$$

*b)* $f(y|x)$
We first find $$f_x(x) = \int_0^x 8xy\;dy = 4xy^2\bigg|_{y=x}^1 = 4x - 4x^3$$
So we get
$$f(y|x) = \frac{f(x,y)}{f_x(x)} = \frac{8xy}{4x-4x^3} = \frac{2y}{1-x^2}$$

*c)* $f(x | y)$
We first find
$$f_y(y) = \int_0^y 8xy\;dx = 4x^2y\bigg|_{x=0}^y = 4y^3$$

So we get
$$f(x|y) = \frac{f(x,y)}{f_y(y)} = \frac{8xy}{4y^3} = \frac{2x}{y^2}$$


*d)*$P[X \le 0.5 | y = 0.75]$

We find that
$f(x\,|\,0.75) = \frac{2x}{9/16} = \frac{32}{9}x$

$$\begin{align}P[X \le 0.5\,|\,y - 0.75] &= \int_0^{0.5}\frac{32}{9}x\;dx \\ &= \frac{16}{9}x^2\bigg|_0^{0.5} \\ &=\frac{4}{9} \end{align}$$

*e)* $P[X \le 0.5 | Y \le 0.75]$

We first find
$$\begin{align} P[X \le 0.5, Y \le 0.75] &= F(x,y)\bigg|_{x=0.5,y=0.75} \\ &=2x^2y^2-x^4\bigg|_{x=0.5,y=0.75} \\ &= \frac{9}{32} - \frac{2}{32}  \\ \\ &= \frac{7}{32}\end{align}$$
then
$$P(Y\le0.75) = \int_0^{0.75} 4y^3\;dy = y^4\bigg|_0^{0.75} = \frac{81}{256}$$

Together,
$$\begin{align}P[X \le 0.5 \,|\, 0.75] &= \frac{P[X \le 0.5, Y \le 0.75]}{P(Y\le0.75)} \\ &= \frac{7/32}{81/256} \\ \\ &= 0.691\end{align}$$

___

28. Suppose $X$ and $Y$ are continuous random variables with joint pdf $f(x,y) = 4(x-xy)$ if $0 < x < 1$ and $0 < y < 1$ and zero otherwise.

*a)* Are $X$ and $Y$ independent? Why or why not?

First, we find
$$f_X(x) = \int_0^14(x-xy)\;dy =4xy -2xy^2\bigg|_{y=0}^1 = 4x -2x = 2x$$
then
$$f_Y(y) = \int_0^1 4(x-xy)\;dx = 2x^2(1-y)\bigg|_{x=0}^1 =2(1-y)$$

We can solve that
$$f_X(x)f_Y(y) = 2x\cdot2(1-y) = 4x(1-y) = 4(x-xy) = f(x,y)$$
so $X$ and $Y$ are independent.

*b)* Find $P[X < Y]$

$$\begin{align}P[X<Y]&=\int_0^1\int_0^yf(x,y)\;dxdy \\ &= \int_0^1 \int_0^y 4x(1-y)\;dxdy \\ &= \int_0^1 2x^2(1-y)\bigg|_{x=0}^y \;dy \\ &= \int_0^12y^2(1-y)\;dy \\ &=\left(\frac{2}{3}y^3-\frac{y^4}{2}\right) \bigg|_{y=0}^1 \\ &=\frac{2}{3}-\frac{1}{2} = \frac{1}{6}\end{align}$$

___

29. Suppose $X$ and $Y$ are continuous random variables with joint pdf given by $f(x,y) = 24xy$ if $0 < x, 0 < y, x + y < 1$, and zero otherwise.

*a)* Are $X$ and $Y$ independent? Why or why not?

From a quick examination, we can see that the triangular region where the joint pdf is defined forces a contradiction on independence, it must be rectangular. We can prove this more concretely by solving the marginals however.

$$f_X(x) = \int_0^{1-x} 24xy \;dy = 12xy^2\bigg|_{y=0}^{1-x} =12x(1-x)^2, 0 < x < 1$$

$$f_Y(y) = \int_0^{1-y} 24xy \; dx = 2xy^2\bigg|_{x=0}^{1-y} =12y(1-y)^2, 0 < y < 1$$

We see that
$$f_X(x)f_Y(y) = 144x(1-x)^2(1-y)^2 \neq f(x,y) = 24xy$$
a contradiction to independence of $X$ and $Y$.

*b)* Find $P[Y > 2X]$
First note
$$2x < y < 1-x$$
so,
$$3x < 1, \text{ and }x < \frac{1}{3}$$
We thus get,
$$\begin{align}P[Y > 2X] &= \int_0^{\frac{1}{3}}\int_{2x}^{1-x} f(x,y)\;dydx \\ &= \int_0^{\frac{1}{3}}\int_{2x}^{1-x} 24xy\;dydx \\ &= \int_0^{\frac{1}{3}} 12xy^2\bigg|_{y=2x}^{1-x} \\ &= \int_0^{\frac{1}{3}}12x(1-x)^2 - 48x^3\;dx\\&=\int_0^{\frac{1}{3}}12x(x^2 -2x + 1) - 48x^3\;dx \\ &= \int_0^{\frac{1}{3}}12x^3 -24x^2 + 12x - 48x^3\;dx \\ &= \int_0^{\frac{1}{3}}-24x^2 + 12x - 36x^3\;dx \\ &= \left(-8x^3+6x^2-9x^4\right)\bigg|_0^{\frac{1}{3}} \\ &=-\frac{8}{27}+\frac{2}{3}-\frac{1}{9} \\ &=\frac{7}{27}\end{align}$$

*c)* Find the marginal pdf of $X$.

$$f_X(x) = \int_0^{1-x} 24xy \;dy = 12xy^2\bigg|_{y=0}^{1-x} =12x(1-x)^2, 0 < x < 1$$

___