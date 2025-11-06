**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $9/7/2025$

___

1. A game involves rolling a fair six-sided die. Define the random variable X as the square of the number showing on the die.  

*a.* List the sample space for X.  

$\fbox{1,4,9,16,25,36}$

*b.* Find the probability mass function (pmf) of $X$.  

$\boxed{P(X=x) = \begin{cases} \frac{1}{6} & \text{if }x \in \{1,4,9,16,25,36\} \\ 0 & \text{ otherwise}\end{cases}}$

___

2. Suppose that the number of cars passing through a toll booth in one minute is a random variable $Y$ with pmf

| $y$    | $0$   | $1$   | $2$   | $3$   |
| ------ | ----- | ----- | ----- | ----- |
| $p(y)$ | $0.1$ | $0.3$ | $0.4$ | $0.2$ |

*a.* Find $P(Y \le 1)$

$P(Y \le 1) = p(0) + p(1) = 0.1+0.3 = \fbox{0.4}$

*b.* Find the cumulative distribution for $Y$

$\boxed{F_Y(y) = P(Y \le y) = \begin{cases} 0.1 & \text{if }y = 0 \\ 0.4 & \text{if }y = 1 \\ 0.8 & \text{if }y = 2 \\ 1 & \text{if }y = 3\end{cases}}$

*c.* Find $E[Y]$

$E[Y] = \sum\limits_{y = 0}^3 y\cdot p(y) = 0 \times 0.1 + 1 \times 0.3 + 2 \times 0.4 + 3 \times 0.2 = 0.3 + 0.8 + 0.6 = \fbox{1.7}$

*d.* Find $\text{Var}(Y)$.

$\text{Var}(Y) = E[Y^2] - E[Y]^2 = 3.7 - 1.7^2 = \fbox{0.81}$

$E[Y^2] \sum\limits_{y = 0}^3 y^2\cdot p(y) = 0^2 \times 0.1 + 1^2 \times 0.3 + 2^2 \times 0.4 + 3^2 \times 0.2 =0.3 +1.6 + 1.8 =3.7$

___

3. A student takes a $10$-question multiple-choice quiz with $4$ options per question, guessing randomly on each. Let $Z =$ number of correct answers. 

*a.* State the distribution of $Z$.  

$\boxed{Z \sim \text{Binomial}(10, 0.25)}$

*b.* Find $P(Z \ge 3)$.  

$\begin{align} P(Z \ge 3) &= 1 - P(Z = 0) - P(Z = 1) - P(Z = 2) \\ &= 1 - \binom{10}{0}0.75^{10} - \binom{10}{1}0.25\times0.75^9 - \binom{10}{2} 0.25^2\times0.75^8 \\ &= 1 - 0.75^{10} - 10 \times 0.25\times0.75^9  - 45 \times 0.25^2\times0.75^8 \approx \fbox{0.474}\end{align}$

*c.* Find the mean and standard deviation of $Z$

Where $n$ is the number of trials, and $p$ is the probability of success,

Mean:
$E[Z] = np = 10 \times 0.25 = 2.5$

Standard Deviation:
$\sigma = \sqrt{\sigma^2} = \sqrt{np(1-p)} = \sqrt{10 \times 0.25 \times 0.75} \approx 1.369$

___