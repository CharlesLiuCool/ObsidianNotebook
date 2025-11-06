**Definition.** A polyhedron ${P \subset \mathbb{R}^n}$ *contains a line* if ${\exists x \in P}$ and nonzero ${d \in \mathbb{R}^n x + \lambda d \in P}$ for all ${\lambda \in \mathbb{R}}$

A polyhedron contains a line if the entire line is in the polyhedron.

For a polyhedron to contain a line it must be unbounded. This means we typically won't run into polyhedra that contain a line

Standard form polyhedra ${P = \{x \in \mathbb{R}^n\,|\,Ax = b, x \ge 0\}}$

>**Theorem 2.6** Suppose that polyhedron ${P = \{x \in \mathbb{R}^n \,|\, a_i^Tx \ge b_i, i = 1, ... , m\}}$ is nonempty.
Then the following statements are equivalent:
${a)}$ ${P}$ has at least one extreme point.
${b)}$ does not contain a line.
${c)}$ There exists ${n}$ vectors from ${\{a_1,...a_m\}}$ which form a linearly independent set.
${d)}$ ${\text{span}\{a_1,...a_m\} = \Bbb{R}^n}$

**Corollary 2.2** Every nonempty bounded polyhedron and every nonempty standard form polyhedron has at least one basic feasible solution.

>**Theorem 2.7** Consider LP: ${ \min z = c^Tx}$ s.t. ${x \in P}$ where ${P}$ is a polyhedron with at least one extreme point. LP has an optimal solution, then there exists an optimal solution which is an extreme point of ${P}$.

>**Theorem 2.8** Consider LP: ${\min z = c^Tx}$ s.t. ${x \in P}$ where polyhedron ${P}$ has at least one extreme point. Then either the optimal cost is ${-\infty}$ (LP is unbounded) or there exists an extreme point which is optimal

>**Corollary 2.3** Consider LP: ${\min z = c^Tx}$ s.t. ${x \in P \neq \phi}$. Then either LP is unbounded or an optimal solution exists.

*Key ideas:* 
We can reduce an infinite number of points in a non-trivial polyhedron to a finite amount of vertices.

We only need to check *basic feasible solutions* to determine optimal points or whether its unbounded or not.

Standard form ${\implies}$ unbounded or optimal vertex

___

### **The Simplex Method**

An improved point iterative method that finds a sequence of feasible points ${\{x_k\}_{k=1}^P}$ satisfying

${a)}$ ${c^T x_{k+1} \le c_T x_k}$ (min problem)
${b) c^Tx_p = z^*}$

**Definition.** Let ${x \in P \subset \mathbb{R}^n}$ (a polyhedron ${P}$) vector ${d \in \Bbb{R}^n}$ is a *feasible direction* at ${x}$ if ${\exists \theta \ge 0 \ni x + \theta d \in P}$.

*Idea*: If I step not too far in a "feasible direction", I remain in the polyhedron.

![[Lesson 9 Simplex Method 2025-02-20 11.03.46.excalidraw|800]]

___

Consider standard form linear program
>${\begin{align} \min &z = c^Tx \\ \text{s.t. } &Ax = b \\ &x \ge 0 \\ &x \in \Bbb{R}^n \end{align}}$

${A}$ is ${m \times n}$ with rank ${m}$.

Suppose ${x}$ is a basic feasible solution (bfs) with basis ${\beta = \{B(1), B(2), ... B(m)\}}$ and basis matrix ${B = \begin{bmatrix} A_{B(1)} & A_{B(2)} & ... & A_{B(m)} \end{bmatrix}}$.

*Recall:* ${B}$ is a basis if ${B}$ is invertible.

Then ${x_i = 0}$ for all ${i \notin B}$ (all nonbasic variables are set to ${0}$)

${\implies b = Ax = Bx_b + Nx_n}$
(We broke ${Ax}$ up into the basic and nonbasic sections)

>[!example]
>${\beta = \{1,3,4\},\;\;n = 5, m = 3}$

>[!check] Answer:
We can take:
>
${x = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \end{bmatrix}}$
>
${x_B = \begin{bmatrix} x_1 \\ x_3 \\ x_4 \end{bmatrix}}$
>
${x_N = \begin{bmatrix} x_2 \\ x_5 \end{bmatrix}}$

___

No suppose we "move" from ${x}$ by selecting a nonbasic variable ${x_j}$ and increase its value from zero to ${\theta > 0}$.

(We're taking this because it looks like a feasible direction: recall n-D polyhedron representation on 2-D in degeneracy lecture)

*Nonbasic variables:* 
${x + \theta d \implies d_j =1 , d_i = 0}$

*Basic variables:*
feasibility ${\implies A(x + \theta d) = b}$
Since ${Ax = b}$, ${\theta A(d) = 0}$ and ${A(d) = 0}$.
${d}$ is a subset of the nullspace.
${0 = Ad = Bd_B + Nd_N = Bd_B + A_j}$

${\implies d_B = -B^{-1}A_j}$ (as ${B}$ is invertible.)
${d}$ (given by ${d_N}$ and ${d_B}$) is called the ${j\text{th}}$ basic direction.

${x + \theta d}$ also must satisfy the non-negativity constraints to remain feasible.

*Case 1:* ${x}$ is a nondegenerate basic feasible solution.
${x_B > 0}$
If ${\theta > 0}$ is sufficiently small then ${x_B + \theta d_B}$ is also feasible.

*Case 2:* ${x}$ is degenerate basic feasible solution.
${d}$ may not be a feasible direction.
(If ${x_B(i) = 0}$ and ${d_{B(i)} < 0}$ then no ${\theta > 0}$ keeps ${x + \theta d > 0}$).

What about the objective value change in direction ${d}$?
${\begin{align} c^T d &= c_B^Td_B + c_N^Td_N \\& = c^T_Bd_B + c_j \\ &= c_B^T(-B^{-1}A_j) + c_j \\ &= c_j - c_B^TB^{-1}A_j\end{align}}$

${\bar{c_j} \equiv c_j - c_B^TB^{-1}A_j}$ is called the *reduced cost* (of ${x_j})$
We want this to be negative, as this is a minimization problem.
If ${\bar{c_j}}$ is positive, it seems like a bad direction to go to. It's getting a larger value for the objective function, which doesn't make sense.

>**Theorem 3.1** Consider basic feasible solution ${x}$ and ${\bar{c}}$ the vector of reduced costs.
${a)}$ If ${\bar{c} \ge 0}$ then ${x}$ is optimal
${b)}$ If ${x}$ is optimal and nondegenerate, then ${\bar{c} \ge 0}$

${b)}$ is concerning. If we are at an optimal point, we *may not know!*

*Theorem 3.1 a)* insight
How would one prove this?
Steps:
${1)}$ Assume ${\bar{c} \ge 0}$
${2)}$ Let ${d  = y-x}$ for some ${y \in P}$
${3)}$ ${Ad = 0 \implies d_B = -B^{-1}Nd_N}$
${4)}$ Show ${c^Td \ge 0}$

${\begin{align} c^Td &= c^T_Bd_B + c_N^Td_N \\ &= c_B^{T} (-B^{-1}Nd_N) + c_N^Td_N \\ &= (c_N^T - c_B^TB^{-1}N)d_N \\ &= \bar{c}^Td_N \ge 0\end{align}}$

(As ${\bar{c}^T \ge 0}$ and ${d_N \ge 0}$, which we will show below)
Nevermind, Asaki is leaving this for us :(

(${\bar{c}^T}$ represents ${c}$ bar transpose.)

**Definition 3.3** A basis matrix ${B}$ is *optimal*
if ${a)}$ ${B^{-1}b \ge 0}$
and ${b)}$ ${\bar{c}^T = c^T - c_B^T B^{-1}A \ge 0}$

___

### **Simplex Method (Nondegenerate Case)**

Step from one basic feasible solution to an adjacent basic feasible solution while reducing the objective value.
- ${x}$ is a basic feasible solution
- ${d}$ is a basic direction
- ${\theta^{*} = \max\{ \theta \ge 0 \,|\, x+\theta d \in P\}}$ (Biggest step we can possible take and remain in the polyhedron)
- ${\begin{align}x &\leftarrow x + \theta^{*}d \\ z &\leftarrow z + \theta^{*}c^Td \end{align}}$

___

### **Simplex Method Concept**
- ${x}$ a basic feasible solution
- ${d}$ a basic direction
- ${\theta* = \max\{\theta \ge 0 \,|\,x + \theta d \in P\}}$
- ${x \leftarrow x + \theta^* d}$
- ${z \leftarrow z + \theta* c^Td}$
- repeat until optimal

It's sometimes hard to get a basic feasible solution, but we will deal with that later...

___

We know that ${x + \theta d}$ satisfies equality constraint for all ${\theta}$, we need only check the non-negativity of ${x + \theta d}$.

If ${d \ge 0}$, then ${x + \theta d \ge 0}$ (recall ${x \ge 0}$) but that means this direction is unbounded (${\theta^* = \infty}$) as you can step as far as you want.

If some ${d_j}$, then ${x_i + \theta d_i \ge 0 \implies}$ ${\theta \le -\frac{x_i}{d_i}}$

${\theta* = \min\limits_{i,d_i < 0}(-\frac{x_i}{d_i}) = \min\limits_{i=1,...,m,d_B(i) < 0}-\frac{x_{B(i)}}{d_B(i)}}$

Result of ${\theta^*}$ more:
some ${x_B(l) \to 0}$
and ${x_j \to \theta^* \ge 0}$

"old basis" ${\{B(1),...,B(l),...B(m)\}}$
"new basis" ${\{B(1),...,B(j),...B(m)\}}$
differ by one element

This process is a pivot.

**Theorem 3.2**
${(a)}$ The columns ${A_{B(i)}}$, ${i \neq l}$ and ${A_j}$ in place of ${A_{B(e)}}$ form a linearly independent set
${\implies}$ a new basis matrix.
${(b)}$ ${y = x + \theta^*d}$ is the associated bfs

One useful definition ${u = -d_b = B^{-1}A_j}$

Go for the *Simplex Tableau*

${(a)\, Ax = b \implies B^{-1}b = B^{-1}Ax}$
${Bx_b + Nx_n = b \implies x_b = -Bb^{-1} = -B^{-1}Ax}$
${(b)\, 0 = z - z}$
${0 = \bar{c}^{T}\,x = c_B^{T}B^{-1}A + c}$
${-c_B^TB^{-1}Ax_B + c^Tx_B}$

| ${-c_B^TB^{-1}b}$ | ${c^T - c^T_bB^{-1}A}$ |
| ----------------------- | ---------------------------- |
| ${B^{-1}b}$       | ${B^{-1}A}$            |


___

**Full Example**
${\min z = x_1 + x_2 - 4x_3}$
${s.t. x_1 + x_2 + 2x_3 \le 9}$
${x_1 + x_2 - x_3 \le 2}$
${-x_1 + x_2 + x_3 \le 4}$
${x \ge 0, x\in \mathbb{R}^3}$

Standard form
${\min z = x_1 + x_2 - 4x_3}$
${s.t. x_1 + x_2 + 2x_3 + x_4 = 9}$
${x_1 + x_2 - x_3 + x_5 = 2}$
${-x_1 + x_2 + x_3 + x_6 = 4}$
${x \ge 0, x \in \Bbb{R}^4}$

${n = 6}$, ${m = 3}$

Let the slack variable be the initial basic variables, or the basis is the columns 4,5,6.

${A = \begin{bmatrix} 1 & 1 & 2 & 1 & 0 & 0 \\ 1 & 2 & -1 & 0 & 1 & 0 \\ -1 & 1 & 1 & 0 & 0 & 1 \end{bmatrix}}$

${b = \begin{bmatrix} 9 \\ 2 \\ 4 \end{bmatrix}}$

${c^T = \begin{bmatrix} 1 & 1 & -4 & 0 & 0 & 0 \end{bmatrix}}$

Basis = ${\begin{bmatrix} A_4 & A_5 & A_6 \end{bmatrix} = I}$

${x_B = B^{-1}b = b = \begin{bmatrix} 9 \\ 2 \\ 4 \end{bmatrix}}$, ${x_N = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}}$

${\bar{c}^T = c^T - c_B^T B^{-1}A = c^T - c_B^{T}A = c^{T}}$