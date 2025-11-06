___

*Claim 1.* Let ${f : \Bbb{R}^n → \Bbb{R}}$ be a convex function and ${c ∈ \Bbb{R}}$. The set ${S = \{x \in \Bbb{R}^n \,|\, f (x) \le c\}}$ is convex.  

We want to show that given ${x,y \in S}$, ${\lambda x + (1-\lambda)y \in S}$ for ${\lambda \in [0,1]}$ 

We know that since ${x,y \in S}$, ${f(x) \le c}$ and ${f(y) \le c}$.
Since ${f}$ is convex ${f(\lambda x + (1-\lambda)y) \le \lambda f(x) + (1-\lambda) f(y)}$
We know that since ${\lambda \in [0,1]}$, ${1-\lambda \in [0,1]}$, so ${\lambda, 1-\lambda \ge 0}$.
Thus, we can take ${\lambda f(x) + (1-\lambda) f(y) \le (\lambda + 1 - \lambda)c = c}$.

So,${f(\lambda x + (1-\lambda)y) \le c}$, and ${\lambda x + (1-\lambda y) \in S}$.

Thus, the set ${S}$ convex.

___

*Claim 2.* Suppose that ${S = \{x ∈ \Bbb{R}^n\,|\,a^T_i x ≥ b_i, i = 1, 2, . . . , m\}}$ and ${T = \{x ∈ \Bbb{R}^n\,|\,g^T_k x ≥ h_i, i = 1, 2, . . . , p\}}$ are two representations of the same nonempty polyhedron. If the vectors ${a_1, a_2, ... , a_m \text{ span } \Bbb{R}^n}$, then the vectors ${g_1, g_2, ... , g_p  \text{ span } \Bbb{R}^n}$.

Since ${A}$ spans ${\Bbb{R}^n}$, there must be ${n}$ linearly independent vectors in ${A}$ that also span ${\Bbb{R}^n}$. By **Theorem 3**, this is equivalent to the polyhedra, ${S}$, having an extreme point and not containing a line. 
Since ${S = T}$, ${T}$ must also have an extreme point and not contain a line. By **Theorem 3**, this also means ${G}$ contains ${n}$ linearly independent vectors that span ${\Bbb{R}^n}$. This also implies ${G = g_1, g_2, ... , g_p}$ spans ${\Bbb{R}^n}$.

___

*Claim 3.* Suppose ${P}$ is a nonempty polyhedron for which ${x_i ≥ 0}$ or ${x_i ≤ 0}$ for each variable ${x_i}$. P has as least one basic feasible solution.  

Since ${P}$ is nonempty, we can take an element ${x}$ where ${x \in P}$ and ${x}$ is feasible. Consider a line ${S = \{ y \in \Bbb{R}^n \,|\, y = x+\lambda d\}}$, where  ${\lambda \in \Bbb{R}}$,  ${d \ne 0}$ and ${d \in \Bbb{R}^n}$.
Take some constraint in the polyhedra, where ${i = j}$. Also consider another element in ${d}$ which is non-zero, ${d_j}$.

*Case 1:* ${x_j \ge 0}$ and ${d_j > 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda < -\frac{x_j}{d_j}}$.
*Case 2:* ${x_j \ge 0}$ and ${d_j < 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda > -\frac{x_j}{d_j}}$.
*Case 3:* ${x_j \le 0}$ and ${d_j > 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda < -\frac{x_j}{d_j}}$.
*Case 4:* ${x_j \le 0}$ and ${d_j < 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda > -\frac{x_j}{d_j}}$.

Since there can be no line in ${P}$, by **Theorem 2.6**, ${P}$ has an extreme point which by **Theorem 2.3** is equivalent to ${P}$ having a basic feasible solution.

___

*Claim 4.* Consider standard form polyhedron P and linear program 

$${\begin{align} \text{ min } z &= c^Tx \\ \text{ s.t. } &x ∈ P \end{align}}$$

If there is more than one optimal solution, then there are infinitely many optimal solutions.  

Assume there are two optimal solutions to the linear program, ${x_1^*}$ and ${x_2^*}$. By definition, ${c^Tx_1^* \le c^T x}$ and ${c^T x_2^* \le c^T x}$. Also, ${c^Tx_1^* = c^Tx_2^*}$.

Given ${\lambda \in [0,1]}$, let ${w = \lambda x_1^* + (1-\lambda) x_2^*}$. ${c^T w = c^T \lambda x_1^* + c^T(1 - \lambda)x_2^* = (\lambda + 1 - \lambda)c^T x_1^* = c^T x_1^*}$

Thus, ${w}$ is also optimal. Since there are infinitely many convex combinations of ${x_1*}$ and ${x_2^*}$, and thus infinitely many ${w}$, there are infinite optimal solutions.

___

*Claim 5.* Let x be an element of standard form polyhedron ${P = \{x ∈ \Bbb{R}^n | Ax = b, x ≥ 0\}}$.  

A vector ${d ∈ \Bbb{R}^n}$ is a feasible direction at ${x}$ if and only if ${Ad = 0}$ and ${d_i ≥ 0}$ for every i such that ${x_i = 0}$.  

Since ${x + \lambda d}$ where ${\lambda}$ is some small positive value is feasible, ${A(x + \lambda d) = b}$. Rewriting, we get ${Ax + \lambda Ad = b}$. Since ${Ax = b}$, ${\lambda Ad = 0}$. As ${\lambda > 0}$, ${Ad = 0}$.
___

*Claim 6.* Let A be a symmetric square matrix. Consider the linear programming problem

$${\begin{align} \text{min } &c^Tx  \\ \text{ s.t. } &Ax ≥ c \\ &x ≥ 0.\end{align}}$$

If ${x}$ satisfies ${Ax = c}$ and ${x ≥ 0}$, then ${x}$ is an optimal solution.  

Consider the dual problem
$${\begin{align} \text{max } &c^Tp  \\ \text{ s.t. } &Ap \ge c \\ &p ≥ 0.\end{align}}$$

Take ${x^*}$ where ${Ax^* = c}$ and ${x^* \ge 0}$.
We know that since ${x^*}$ satisfies both constraints of our linear program, it is primal feasible.

We know that ${A = A^T}$ since ${A}$ is a symmetric square matrix.
Let ${p}$ be an appropriately sized matrix for the dual problem. Solving for the dual problem, we get the constraints that ${Ap \ge c}$ and ${p \ge 0}$ where we are trying to maximize ${c^Tp}$. Thus ${p}$ is dual feasible.

By *Theorem 4.17 (Weak duality)*, we know the objective of our dual problem ${c^Tp \le c^Tx^*}$.

This means ${x^*}$ is also an optimal solution of the dual problem.

By *Theorem 4.4 (Strong Duality)*, the optimal costs of the dual and primal problem are equal.
Let ${y^*}$ be an optimal solution in the primal problem corresponding to ${x^*}$ in the dual problem.
This means ${c^Ty^* = c^Tx^*}$ as both the primal and dual have the same objective function.

Thus, ${y^* = x^*}$ and ${x^*}$ is an optimal solution for the primal problem.

___

*Claim 7.* Consider the problem of minimizing ${c^Tx}$ over polyhedron ${P}$. A feasible solution ${x}$ is optimal if and only if ${c^Td ≥ 0}$ for every feasible direction ${d}$ at ${x}$.  

Assume ${x^*}$ is an optimal feasible solution to the program. This means ${c^Tx^* \le c^Tx}$. Let ${x^* = x + \lambda d}$. We know that ${c^Tx + c^T\lambda d \le c^Tx}$, which means ${c^Td \le 0}$.

Assume ${c^Td \ge 0}$ for every feasible direction ${d}$ at ${x}$. Take some point ${x^* = x + \lambda d}$. We can solve that ${c^T x^* = c^Tx + c^T\lambda d}$


___

*Claim 8.* Let ${f_1, f_2, . . . , f_m}$ be convex functions from ${\Bbb{R}^n}$ into ${\Bbb{R}}$ and ${a_1, a_2, . . . , a_m}$ non-negative scalars. Then, ${f(x) = \sum\limits_{k=1}^m\;a_kf_k}$ is convex.

For any given ${i}$ where ${i = 1,2,...,m}$, ${f_i(\lambda x + (1-\lambda)y) \le \lambda f_i(x) + (1-\lambda) f_i(y)}$

We can solve that ${f(\lambda x + (1-\lambda)y)}$
${= a_1f_1(\lambda x + (1-\lambda)y) + a_2f_2(\lambda x + (1-\lambda)y) + ... + a_m (\lambda x + (1-\lambda)y) f_m}$
${\le a_1\lambda f_1(x) + (1-\lambda)f_1(y) + ...}$
${= \lambda f(x) + (1-\lambda)f(y)}$

Thus, this is convex.

___