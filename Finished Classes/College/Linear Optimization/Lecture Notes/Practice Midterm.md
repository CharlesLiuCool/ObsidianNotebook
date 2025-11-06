1. Consider the following optimization problem. Construct an equivalent *linear program*.

$${\begin{align} \min z &= 3x_1 + |x_2 - x_3| \\ \text{s.t. } &|x_1 + x_2 + x_3| \le 8 \\ &(x_1 + x_2)^2 \le 9 \\ &x \in \Bbb{R}^3 \end{align}}$$

Solution:
$${\begin{align} \min z &= 3x_1 + \delta \\ \text{s.t. } & x_2 - x_3 \le 8 \\ -&x_2+x_3 \le 8\\ &x_1 + x_2 + x_3 \le 8 \\& -x_1 - x_2 - x_3 \le 8 \\ &x_1 + x_2 \le 3 \\ &-x_1-x_2 \le 3 \\ &x \in \Bbb{R}^3 \end{align}}$$

1. Show, with justification, that ${f(x) = x^3}$ is a convex function on ${[0, \infty)}$.

**Theorem.** ${f(x) = x^3}$ is a convex function on ${[0, \infty]}$
*Proof:*
By *Definition 1.1*,  the twice differentiable function ${f(x)}$ is convex when its Hessian matrix is positive semidefinite.

We can solve that ${f''(x) = 6x}$. On ${[0,\infty)}$, ${f''(x) \ge 0}$, so the Hessian matrix ${|f''(x)|}$ is positive semidefinite and ${f(x)}$ is convex.

1. Show, with justification, that every standard form linear program has at least as many  
decision variables as equality constraints. That is, if the equality constraints are Ax = b  
then A has at least as many columns as rows.

**Theorem.** In a standard form linear program with equality constraints ${Ax = b}$, ${A}$ has at least as many rows as columns.
*Proof*:
Let ${A}$ be an ${n \times m}$ matrix.
BWOC, assume that ${n \le m}$.
By definition of standard form linear program, all rows  of ${A}$ must be linearly independent. That means any ${m}$ rows in ${A}$ will span ${\mathbb{R}^m}$. However, that means there are ${m-n}$ rows which can be written as linear combinations of the other ${m}$, so ${A}$ has linearly dependent rows, a contradiction.
Thus, ${A}$ has at least as many rows as columns.

