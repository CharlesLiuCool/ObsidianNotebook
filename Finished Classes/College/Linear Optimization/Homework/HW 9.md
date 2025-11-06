**Charles Liu**
Linear Optimization - Dr. Tom Asaki
March 21st, 2025
___

### **Exercise 4.1**
Consider the linear programming problem:
$${\begin{align} \text{minimize }\;&x_1-x_2 \\ \text{subject to }\;&2x_1 + 3x_2 - x_3 + x_4 \le 0 \\ &3x_1 + x_2 + 4x_3 - 2x_4 \ge 3 \\ &-x_1-x_2+2x_3+x_4 = 6\\ &x_1 \le 0 \\ &x_2,x_3 \ge 0\end{align}}$$

Write down the corresponding dual problem.

First, let's find the important components.

${c^T = \begin{bmatrix} 1 & -1 & 0 & 0\end{bmatrix}}$

${A = \begin{bmatrix} 2 & 3 & -1 & 1 \\ 3 & 1 & 4 & -2 \\ -1 & -1 & 2 & 1 \end{bmatrix}}$

${b = \begin{bmatrix} 0 \\ 3 \\ 6 \end{bmatrix}}$

Dual problem:
$${\begin{align} \text{max }\;&p^Tb \\ \text{subject to }\;&2p_1 + 3p_2 -p_3 \ge 1 \\ &3p_1 + p_2 - p_3 \le -1 \\ &\;-p_1 + 4p_2 + 2p_3 \le 0 \\ &p_1 - 2p_2 + p_3 \le 0 \\ &p_1 \le 0\\&p_2 \ge 0\\&p_3 \text{ urs}
\end{align}}$$

Using software, we find that the primal problem is unbounded and the dual is infeasible, which aligns with *Corollary 4.1* in our textbook. This corollary states that if the optimal cost of the primal is ${-\infty}$, then the dual problem is infeasible.

This also aligns with *Theorem 4.17*, which says if the primal is feasible then the objective function of the dual is greater than or equal to the primal's objective function. As the primal is unbounded, we can't satisfy the dual problem's constraints.
This also satisfies *Theorem 4.18*, which says is if the primal has an optimal solution so does the dual. Since the primal is infeasible, it follows that the the dual has no optimal solution, which is satisfied.

___

### **Exercise 4.4**

Let ${A}$ be a symmetric square matrix. Consider the linear programming problem
$${\begin{align} \text{minimize }\;&c^Tx \\ \text{subject to }\; &Ax \ge c \\ &x \ge 0\end{align}}$$

Prove that if ${x^*}$ satisfies ${Ax^* = c}$ and ${x^* \ge 0}$, then ${x^*}$ is an optimal solution.

*Proof:*
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