**Charles Liu**
Linear Optimization - Dr. Tom Asaki
February 21st 2025
___

1. Consider the standard form polyhedron ${P = \{x \in \mathbb{R}^n\,|\,Ax = b, x \ge 0\}}$ , and assume that the rows of matrix ${A}$ are linearly independent.  Prove that if two different bases correspond to the same basic solution, then this basic solution is degenerate.

**Theorem.** For the standard form polyhedron ${P  = \{x \in \Bbb{R}^n \,|\,Ax = b, x\ge 0\}}$ where ${A}$ has linearly independent rows, if two different bases correspond to the same basic solution, then that basic solution is degenerate.

*Proof:*
We want to show that the basic solution is degenerate, which is equivalent to showing that at least one variable in ${x}$ is zero.
Assume that we have two distinct bases ${B_1}$ and ${B_2}$ that produce the same basic solution, ${x}$.
BWOC, assume that ${x}$ has all (${m}$) nonzero variables. This means all ${m}$ variables in ${B_1}$ and ${B_2}$ are nonzero.
As ${B_1}$ and ${B_2}$ are distinct, there's at least one variable in ${B_1}$ that's not in ${B_2}$.
However, this means there is ${m+1}$ nonzero variables in ${x}$, a contradiction, so ${x}$ must be degenerate.

___

2. Consider nonempty polyhedron ${P \subset \mathbb{R}^n}$ and suppose that for each variable ${x_i}$ we have either the constraint ${x_i \ge 0}$ or the constraint ${x_i \le 0}$.  Prove that ${P}$ has at least one basic feasible solution.

**Theorem.** For the nonempty polyhedron ${P \subset \Bbb{R}^n}$, if we have that each variable ${x_i}$ either satisfies the constraint ${x_i \ge 0}$ or ${x_i \le 0}$, then ${P}$ has at least one basic feasible solution.

*Proof:*
Since ${P}$ is nonempty, we can take an element ${x}$ where ${x \in P}$ and ${x}$ is feasible. Consider a line ${S = \{ y \in \Bbb{R}^n \,|\, y = x+\lambda d\}}$, where  ${\lambda \in \Bbb{R}}$,  ${d \ne 0}$ and ${d \in \Bbb{R}^n}$.
Take some constraint in the polyhedra, where ${i = j}$. Also consider another element in ${d}$ which is non-zero, ${d_j}$.

*Case 1:* ${x_j \ge 0}$ and ${d_j > 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda < -\frac{x_j}{d_j}}$.
*Case 2:* ${x_j \ge 0}$ and ${d_j < 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda > -\frac{x_j}{d_j}}$.
*Case 3:* ${x_j \le 0}$ and ${d_j > 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda < -\frac{x_j}{d_j}}$.
*Case 4:* ${x_j \le 0}$ and ${d_j < 0}$, then ${x_j+\lambda d_j  \notin P}$ when ${\lambda > -\frac{x_j}{d_j}}$.

Since there can be no line in ${P}$, by **Theorem 2.6**, ${P}$ has an extreme point which by **Theorem 2.3** is equivalent to ${P}$ having a basic feasible solution.

___