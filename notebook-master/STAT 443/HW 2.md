**Charles Liu**
Dr. Haijun Li
$9/27/2025$

___

3. A bag contains three coins, one of which has a head on both sides, while the other two coins are normal. A coin is chosen at random from the bag and tossed three times. The number of heads is a random variable, say $X$.

*a)* Find the discrete pdf of $X$. (*Hint:* Use the Law of Total Probability with $B_1 =$ a normal coin and $B_2 =$ two-headed coin)

Let $B_1 =$ the event a normal coin is chosen from the bag
Let $B_2 =$ the event a two-headed coin is chosen from the bag

We can find that the probability $0$ heads and the normal coin is chosen is $P(0\text{ heads} \cap B_1) = (\frac{1}{2})^3 \cdot \frac{2}{3} =\frac{1}{12}$

We can find that the probability $1$ heads and the normal coin is chosen is  $P(1\text{ heads} \cap B_1) = \binom{3}{1}(\frac{1}{2})^3 \cdot \frac{2}{3} =\frac{1}{4}$

We can find that the probability $2$ heads and the normal coin is chosen is  $P(2\text{ heads} \cap B_1) = \binom{3}{2}(\frac{1}{2})^3 \cdot \frac{2}{3} = \frac{1}{4}$

We can find that the probability $3$ heads and the normal coin is chosen is  $P(3\text{ heads} \cap B_1) = \binom{3}{3}(\frac{1}{2})^3 \cdot \frac{2}{3} =\frac{1}{12}$

We find that the probability of $3$ heads on the two-headed coin is $1$, as each toss must result in a heads. Thus, 
$$P(3\text{ heads} \cap B_2) = 1 \cdot \frac{1}{3} = \frac{1}{3}$$ and 
$$P(2\text{ heads} \cap B_2) = P(1 \text{ heads} \cap B_2) = P(0 \text{ heads} \cap B_2) = 0$$

Using law of total probability, we know $P(i \text{ heads}) = P(i\text{ heads} \cap B_1) + P(i\text{ heads} \cap B_2)\;\forall\;i=0,1,2,3$
as $B_1$ and $B_2$ are mutually exclusive.

Thus,
$P(0 \text{ heads}) = \frac{1}{12} + 0 = \frac{1}{12}$
$P(1 \text{ heads}) = \frac{1}{4} + 0 = \frac{1}{4}$
$P(2 \text{ heads}) = \frac{1}{4} + 0 = \frac{1}{4}$
$P(0 \text{ heads}) = \frac{1}{12} + \frac{1}{3} = \frac{5}{12}$

and the discrete PDF of $X$ is:

|        | $0$ heads      | $1$ head      | $2$ heads     | $3$ heads      |
| ------ | -------------- | ------------- | ------------- | -------------- |
| $p(x)$ | $\frac{1}{12}$ | $\frac{1}{4}$ | $\frac{1}{4}$ | $\frac{5}{12}$ |

we can also write

$p(x) = \begin{cases} \frac{1}{12} & \text{ if }0\text{ heads} \\ \frac{1}{4} & \text{ if }1\text{ heads} \\ \frac{1}{4} & \text{ if }2\text{ heads} \\ \frac{5}{12} & \text{ if }3\text{ heads}\end{cases}$

*b)* Sketch the discrete pdf and the CDF of $X$.


![[HW 2 2025-09-17 14.51.41.excalidraw]]

![[HW 2 2025-09-17 14.57.40.excalidraw]]

___

5. A discrete random variable has pdf $f(x)$.

*a)* If $f(x) = k(1/2)^x$ for $x = 1,2,3,$ and zero otherwise, find $k$

The sum of the probability mass on $x$ over all possible outcomes in discrete random variable $X$ (where $x$ is taken from) must be $1$.

 $\sum_{x=1}^3 k(1/2)^x =k(1/2) + k(1/4) + k(1/8) = \frac{7}{8}k = 1$
 
$k = \frac{8}{7}$

*b)* Is a function of the form $f(x) = k[(1/2)^x - 1/2]$ for $x =0,1,2$ a pdf for any $k$?

If it is a pdf, $f(x) \ge 0$ for all $x$ on the domain. Notice that $f(0) = k[1 - 1/2] = \frac{1}{2}k$, and $f(2) = k[1/4-1/2] = -\frac{1}{4}k$

Notice that the sign of $f(0)$ must always differ from the sign of $f(2)$ for any value of $k\in(-\infty, \infty)$ except at $k = 0$.

However, if $k=0$, $f(x) = 0$, which cannot be, since the sum of the probability mass across all elements in the domain must equal $1$.

Thus, no value of $k$ results in a pdf.

___

8. A nonnegative integer-valued random variable $X$ has a CDF of the form $F(x) = 1-(1/2)^{x+1}$ for $x = 0,1,2,...$ and zero if $x < 0$

*a)* Find the pdf of $X$.

Let $f(x)$ be the PDF of $X$.

The pdf for a value $x = k$ (e.g. $f(k)$) is the difference between consecutive CDF values (e.g. $F(k) - F(k-1)$)

So
$\begin{align} f(x) &= 1 - (1/2)^{x+1} - (1 - (1/2)^{x}) = ((1/2)^{x} - (1/2)^{x+1}) \\ &= ((1/2)^{x} - (1/2)(1/2)^{x}) = (1/2)^{x}(1 - 1/2) = (1/2)^{x+1} \end{align}$

*b)* Find $P[10 < X \le 20]$

We can take the difference between the CDF value at $20$ (which is $F(20)$) with the CDF value at $10$ (which is $F(10)$).

We can solve this to be
$$F(20) - F(10) = 1-(1/2)^{21} - (1-(1/2)^{11}) = (1/2)^{11} - (1/2)^{21}$$

*c)* Find $P[X \text{ is even}]$

$\sum\limits_{k=0}^{\infty}f(2k) = \sum\limits_{k=0}^{\infty} (1/2)^{2k+2} = (1/2)^{2} + (1/2)^4 + ... = \frac{1/2}{1-(1/4)} = \frac{1/2}{3/4} = \frac{2}{3}$

___

13. A function $f(x)$ has the following form:

$$f(x) = kx^{-(k+1)},\;1<x<\infty$$
and zero otherwise

*a)* For what values of $k$ is $f(x)$ a pdf?

In order for $f(x)$ to be a pdf,
$$\int_{1}^{\infty} f(x) dx = 1$$

and $f(x) > 0$ (which means $k > 0$)

We can find that
$$\int_{1}^{\infty} kx^{-(k+1)} dx = -x^{-k}\bigg|_{x = 1}^{\infty}$$
We need $-k < 0$, so all values of $k > 0$ in a pdf.

*b)* Find the CDF based on (a).

$$\int_{1}^x f(t)dt = \int_1^x kt^{-(k+1)}dt = -t^{-k} \bigg|_{t=1}^x = -x^{-k} + 1 = 1 - x^{-k}$$

Thus, the CDF is
$$F(x) = \begin{cases} 1 - x^{-k} & \text{ if } 1 < x < \infty \\ 0 & \text{ otherwise}\end{cases}$$

*c)* For what values of $k$ does $E(X)$ exist?

We can find
$$E(X) = \int_1^\infty f(x)x dx = \int_1^\infty kx^{-k} = \frac{k}{-k+1}x^{-k+1}\bigg|_{1}^\infty$$

Notice that if $k \le 1$, the integral diverges. When $k > 1$, it evaluates to  $\frac{k}{k-1}$ and exists.

Thus, $E(X)$ exists for all values $k > 1$.

___

19. A random variable $X$ has the pdf
$$f(x) = \begin{cases} x^2 & \text{ if }0 < x \le 1 \\ 2/3 & \text{ if }1 < x \le 2 \\ 0 & \text{ otherwise} \end{cases}$$

*a)* Find the median of $X$.

We want to solve the median $x$ where $\int_0^{x} f(t) dt = 0.5$

First note $\int_{0}^1 f(t)dt = \int_{0}^1 t^2 = \frac{t^3}{3}\bigg|_0^1 = \frac{1}{3} < 0.5$

Thus, $x > 1$

We find
$$\begin{align} \int_{0}^x f(t)dt &= \int_{0}^1 f(t)dt + \int_{1}^x f(t)dt \\ &= \frac{1}{3} + \int_{1}^x \frac{2}{3} dt = \frac{1}{3} + \frac{2}{3}x\bigg|_1^x \\ &= \frac{1}{3} + \frac{2}{3}(x-1) = \frac{2}{3}x - \frac{2}{3} + \frac{1}{3} \\ &= \frac{2}{3}x - \frac{1}{3} = 0.5\end{align}$$

Which means
$$\frac{2}{3}x = \frac{5}{6}$$

So the median is
$$x = \frac{5}{4}$$

*b)* Sketch the graph of the CDF and show the position of the median on the graph.

![[HW 2 2025-09-24 22.17.56.excalidraw]]

___

20. A continuous random variable $X$ has CDF given by

$$F(x) = \begin{cases} 0 & \text{ if }x < 1 \\ 2(x-2 + \frac{1}{x}) & \text{if }1 \le x \le 2 \\ 1 & \text{if }2 < x \end{cases}$$

*a)* Find the $100 \times p$th percentile of the distribution with $p = 1/3$

We want to find $x$ where $F(x) = \frac{1}{3}$

Since when $x < 1$, $F(x)$ is $0$, we know $x \ge 1$.

Likewise, when $x > 2$, $F(x)$ is $1$, so $x \le 1$

Thus we solve $2(x-2 + \frac{1}{x}) = \frac{1}{3}$ where $1 \le x \le 2$

We find
$$x-2 + \frac{1}{x} = \frac{1}{6}$$

so

$$x+\frac{1}{x} = \frac{13}{6}$$

Multiply $x$ by both sides (doesn't change domain of $x$, as current domain does not contain $0$), we get
$$x^2 + 1 = \frac{13}{6}x$$

so

$$x^2 -\frac{13}{6}x + 1 = 0$$

Using the quadratic formula, we get
$$x = \dfrac{\frac{13}{6} \pm \sqrt{\frac{169}{36} - 4}}{2} = \dfrac{\frac{13}{6} \pm \sqrt{\frac{25}{36}}}{2} = \dfrac{\frac{13}{6} \pm \frac{5}{6}}{2} = \frac{13 \pm 5}{12}$$

which comes out to $\frac{3}{2}$ or $\frac{2}{3}$

Since $1 \le x \le 2$, we get the $100 \times p$th percentile of $X$ where $p = \frac{1}{3}$ is
$$x = \frac{3}{2}$$

*b)* Find the pdf of $X$.

Let $f(x)$ be the pdf. We simply take the derivative, $f(x) = F'(x)$

$f(x) = \begin{cases} 0 & \text{if }x < 1 \\ 2 - 2x^{-2} & \text{if } 1 \le x \le 2 \\0 & \text{if }x > 2 \end{cases}$

___

24. Let $X$ be continuous with pdf $f(x) = 3x^2$ if $0 < x < 1$, and zero otherwise. Find:

*a)* $E(X)$.

$$E(X) = \int_{0}^1 f(x) x \;dx = \int_{0}^1 3x^2x\;dx = \int_{0}^1 3x^3\;dx = \frac{3}{4}x^3\bigg|_{0}^1= \frac{3}{4}$$

*b)* $\text{Var}(X)$.

We solve
$$E[X^2] = \int_{0}^1 (3x^2)x^2\;dx=\int_{0}^1 3x^4\;dx = \frac{3}{5}x^5\bigg|_0^1 = \frac{3}{5}$$

Thus,
$$\begin{align} \text{Var}(X) &=  E[(X- E[X])^2] = E[X^2] - E[X]^2 \\ &= \frac{3}{5} - \left(\frac{3}{4}\right)^2 = \frac{3}{5} - \frac{9}{16} = \frac{3}{80}\end{align}$$

*c)* $E(X^r)$.

Assuming $r \neq -3$
$$\begin{align}E(X^r) &= \int_0^1 f(x) x^r\;dx = \int_0^1 3x^{2+r}\;dx \\ &= \frac{3}{2+r+1}x^{2+r+1}\bigg|_{x=0}^1 = \frac{3}{2+r+1} = \frac{3}{r+3}\end{align}$$

*d)* Find $E(3X - 5X^2 + 1)$

By linearity of expectations,
$$\begin{align}E(3X - 5X^2 + 1) &= 3E[X] - 5E[X^2] + 1 \\ &= \frac{9}{4} - 5\times\frac{3}{5} + 1 \\ &= 1/4 \end{align}$$

___

30. Let $X$ be a nonnegative continuous random variable with CDF $F(x)$ and $E(X) < \infty$. Use integration by parts to show that
$$E(X) = \int_{0}^\infty [1-F(x)]dx$$

Note: For any continuous random variable with $E(|X|) < \infty$, this result extends to
$$E(X) = -\int_{-\infty}^0 F(x) dx + \int_{0}^\infty [1-F(x)]dx$$

We can first start on finite interval $[0,A]$
$$\begin{align} \int_{0}^A xF'(x)\;dx &= xF(x)\bigg|_0^A - \int_0^A F(x)\;dx \\ &= AF(A) - \int_0^A F(x)\;dx \\ &= A - A(1 - F(A)) - \int_0^A F(x)\;dx \\ &= x\bigg|_0^A- A(1 - F(A)) - \int_0^A F(x) \; dx \\ &= \int_0^A 1 \; dx - A(1 - F(A)) - \int_0^A F(x) \; dx \\ &= \int_0^A (1 - F(x)) \; dx - A(1 - F(A)) \end{align}$$

We know
$$\begin{align}E(X) &= \lim_{A \to \infty} \int_{0}^A xF'(x)\;dx \\ &= \lim_{A \to \infty}\left(\int_0^A (1 - F(x)) \; dx - A(1 - F(A))\right) \\ &= \int_0^\infty (1 - F(x)) \; dx \end{align}$$

Notice that $\lim\limits_{A \to \infty} A(1-F(A)) = 0$ Since $F(A)$ as $A$ approaches $\infty$ approaches $1$.

31. 
*a)* Use Chebyshev's inequality to obtain a lower bound on $P[5/8 < X < 7/8]$ in Exercise $24$. Is this a useful bound?

As calculated in Exercise $24$, the mean $\mu = \frac{3}{4}$ and variance $\text{Var}(X) = \frac{3}{80}$.

We can find that the fixed deviation $m = |\mu - 5/8| = |\mu - 7/8| = 1/8$

Recall Chebyshev's inequality:
$$E(|X - \mu| \ge m) \le \frac{\text{Var}(X)}{m^2}$$

We find
$$E(|X - 3/4| \ge 1/8) \le \frac{3/80}{1/64} = \frac{12}{5} > 1$$

The inequality results in the trivial bound
$$E|X - 3/4| \ge 1/8) \le 1$$

which tells us
$$P[5/8 < X < 7/8] \ge 0$$

This is *not* a useful bound, probabilities can't exceed $1$ and can't be lower than $0$. Chebyshev didn't tell us anything about the tail (trivially saying the probability in the tail is less than $1$), and thus didn't tell us anything about the range we hoped to lower bound (except it can't be lower than $0$, which is trivial).

*b)* Rework (a) for the probability $P[1/2 < X < 1]$

We can find that the fixed deviation $m = |\mu - \frac{1}{2}| = |\mu - 1| = \frac{1}{4}$

Applying Chebyshev's inequality,
$$E(|X - 3/4| \ge 1/4) \le \frac{3/80}{1/16} = \frac{3}{5}$$

This means we can lower bound $P[1/2 < X < 1]$ by calculating
$$P[1/2 < X < 1] \ge 1 - \frac{3}{5} = \frac{2}{5}$$

*c)* Compare this bound to the exact probability.
We can find the actual probability by solving
$$\int_{1/2}^1 3x^2\;dx = x^3\bigg|_{1/2}^1 = 1 - \frac{1}{8} = \frac{7}{8}$$

The difference between our lower bound and the actual probability is
$$\left|\frac{7}{8} - \frac{2}{5}\right| = \frac{19}{40}$$
which is nearly $0.5$. This means our estimate with Chebyshev's inequality, although better than part a), still isn't great.

___

36. Assume that $X$ is a continuous random variable with pdf
$$f(x) = \text{exp}[-(x+2)] \text{ if }-2 < x < \infty \text{ and zero otherwise}$$

*a)* Find the moment generating function of $X$.

$$\begin{align}M_X(t) &= E[e^{Xt}] = \int_{-2}^\infty e^{xt}e^{-(x+2)}\;dx = e^{-2}\int_{-2}^\infty e^{x(t-1)}\;dx \\ &= e^{-2}\left(\frac{e^{x(t-1)}}{t-1}\bigg|_{x = -2}^\infty\right) = -e^{-2} \frac{e^{-2(t-1)}}{t-1} = -\frac{e^{-2t}}{t-1}\end{align}$$

*b)* Use the MGF of (a) to find $E(X)$ and $E(X^2)$

$E(X) = M_X'(0) = -\left(\frac{-2e^{-2t}(t-1) - e^{-2t}}{(t-1)^2}\right) \bigg|_{t=0} = -\left(\frac{e^{-2t}(-2t+1)}{(t-1)^2}\right) \bigg|_{t=0}  = -1$

$E(X^2) = M_X''(0) = -\left(\frac{(-2e^{-2t}(-2t + 1) -2e^{-2t})(t-1)^2 - e^{-2t}(-2t+1)2(t-1)}{(t-1)^4}\right)\bigg|_{t=0} = \frac{-4+2}{1} = 2$

___