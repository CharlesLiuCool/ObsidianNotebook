### **Exercise 3.3**
Let ${x}$ be an element of the standard form polyhedron ${P \in \{x \in \Bbb{R}^n \,|\, Ax = b, x \ge 0\}}$. Prove that a vector ${d \in \Bbb{R}^n}$ is a feasible direction at ${x}$ if only if ${Ad = 0}$ and ${d_i \ge 0}$ for every ${i}$ such that ${x_i = 0}$.

*Proof:*
We will first prove the forward direction.

A feasible direction only exists when there is a positive scalar ${\theta}$ where ${x + \theta d \in P}$.

Assume ${d \in \Bbb{R}^n}$ is a feasible direction. We can solve that
$${A(x + \theta d) = Ax + \theta Ad = b + \theta A d}$$
However, since ${x + \theta d \in P}$,
$${A(x+\theta d) = b}$$
So,
${b = b + \theta A d}$
and ${\theta A d = 0}$, which means ${Ad = 0}$.
Since ${x + \theta d \ge 0}$, ${x_i + \theta d_i \ge 0}$. When ${x_i = 0}$, we can see that ${\theta d_i \ge 0}$.

Thus, the forward direction is proved.

We will now prove the converse.
Assume ${Ad = 0}$ and ${d_i \ge 0}$ for every ${i}$ such that ${x_i = 0}$.

We can solve that

$${A(x + \theta d) = Ax + \theta Ad = Ax = b}$$

So ${A(x+\theta d) = b}$.

Since ${x \ge 0}$ and ${d \ge 0}$, we can find ${\theta \ge 0}$ so that ${x + \theta d \ge 0}$. 
So, ${x + \theta d \in P}$, and ${d}$ is feasible.

___

### **Exercise 3.12**

Consider the problem
$${\begin{align} \text{minimize}\;2&x_1-x_2\\ &x_1-x_2 \le 2 \\ &x_1 + x_2 \le 6 \\ &x_1,x_2 \ge 0 \end{align}}$$

*a)* Convert the problem into standard form and construct a basic feasible solution at which ${(x_1,x_2) = (0,0)}$.

$${\begin{align} \min\limits_x z = \;2&x_1-x_2\\ &x_1-x_2 + x_3 = 2 \\ &x_1 + x_2 + x_4 = 6 \\ & x \ge 0, x \in \Bbb{R}^4 \end{align}}$$

*b)* Carry out the full tableau implementation of the simplex method, starting with the basic feasible solution of part ${(a)}$.

Basic feasible solution: ${(x_1,x_2) = (0,0)}$

|           | $x_1$ | $x_2$ | $x_3$ | $x_4$ |
| --------- | ----- | ----- | ----- | ----- |
| $-z  = 0$ | $-2$  | $-1$  | $0$   | $0$   |
| $x_3 = 2$ | $1$   | $-1$  | $1$   | $0$   |
| $x_4 = 6$ | $1$   | $1$   | $0$   | $1$   |

|           | $x_1$ | $x_2$ | $x_3$ | $x_4$ |
| --------- | ----- | ----- | ----- | ----- |
| $-z  = 4$ | $0$  | $-3$  | $2$   | $0$   |
| $x_3 = 2$ | $1$   | $-1$  | $1$   | $0$   |
| $x_4 = 6$ | $1$   | $1$   | $0$   | $1$   |


|           | $x_1$ | $x_2$ | $x_3$ | $x_4$ |
| --------- | ----- | ----- | ----- | ----- |
| $-z  = 4$ | $0$   | $-3$   | $2$   | $0$   |
| $x_3 = 2$ | $1$   | $-1$  | $1$   | $0$   |
| $x_4 = 4$ | $0$   | $2$   | $-1$  | $1$   |

|           | $x_1$ | $x_2$ | $x_3$ | $x_4$ |
| --------- | ----- | ----- | ----- | ----- |
| $-z  = 4$ | $0$   | $-3$   | $2$   | $0$   |
| $x_1 = 2$ | $1$   | $-1$  | $1$   | $0$   |
| $x_4 = 4$ | $0$   | $1$   | $-0.5$  | $0.5$   |

|           | $x_1$ | $x_2$ | $x_3$ | $x_4$ |
| --------- | ----- | ----- | ----- | ----- |
| $-z  = 4$ | $0$  | $-3$  | $2$   | $0$   |
| $x_1 = 2$ | $1$   | $-1$  | $1$   | $0$   |
| $x_4 = 2$ | $0$   | $1$   | $-0.5$   | $0.5$   |

|            | $x_1$ | $x_2$ | $x_3$  | $x_4$ |
| ---------- | ----- | ----- | ------ | ----- |
| $-z  = 10$ | $0$   | $0$   | $0.5$  | $1.5$ |
| $x_1 = 2$  | $1$   | $-1$  | $0.5$  | $0$   |
| $x_4 = 2$  | $0$   | $1$   | $-0.5$ | $0.5$ |

|           | $x_1$ | $x_2$ | $x_3$ | $x_4$ |
| --------- | ----- | ----- | ----- | ----- |
| $-z  = 10$ | $0$  | $0$  | $0.5$   | $1.5$   |
| $x_1 = 4$ | $1$   | $0$  | $0.5$   | $0.5$   |
| $x_4 = 2$ | $0$   | $1$   | $-0.5$   | $0.5$   |


*c)* Draw a graphical representation of the problem in the terms of the original variables ${x_1,x_2}$, and indicate the path taken by the simplex algorithm.
![[HW 7 2025-02-28 22.27.02.excalidraw]]