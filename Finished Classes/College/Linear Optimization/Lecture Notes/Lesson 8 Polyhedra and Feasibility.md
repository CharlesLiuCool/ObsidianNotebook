## **Key Concepts**

The *feasibility region* can be written as the intersection of polyhedra (e.g. halfspace, line)
The intersection of two convex sets is also convex
Polyhedron are convex
*Convex combinations* - see definition
*Convex hulls* - see definition
*Extreme point* - not a convex combination of two elements in the convex region
*Vertex* - rest of the convex set is in a halfspace from the vertex.
*Active* - see definition
*Polyhedron Standard Form*

___


*Recent Definitions:*
Hyperplane
Halfspace
Polyhedron
Convex (set)
Convex (function)

**Examples of Polyhedra in ${\mathbb{R}^n}$*

${\phi}$

${\mathbb{R}^n}$
${Ax \ge b}$ where ${A}$ is the zero matrix and ${b}$ is the zero vector of appropriate size.

Finite intersection of halfspaces.

>[!tip] Why do we care about **Polyhedra**?
>This helps us understand the *feasible region* of an optimization problem.


**Definition.** A set ${S \subseteq \mathbb{R}^n}$ is *bounded* if ${\exists K \ni ||x|| \le K\,\forall\,x\in S}$

>[!bug]  Doesn't work
>A set ${S \subseteq \mathbb{R}^n}$ is bounded if for some ${x_0 \in S}$, ${||x-x_0|| \le k\,\forall x\in S}$
> 
> *Why?:* Doesn't contain empty set.

**Definition.** Let ${x^1,...,x^k \in \mathbb{R}^n}$ and ${\lambda_1, ...,\lambda_k \ge 0}$ such that ${\lambda_1+...+\lambda_k = 1}$
*a)* Vector ${\lambda_1x^1 + ...+\lambda_kx^k}$ is a *convex combination* of vectors ${x^1, ..., x^k}$.
*b)* The *convex hull* of ${x^1, ...,x^k}$ is the set of all *convex combinations* of these vectors.

**Theorem 2.1**
*a)* The intersection of convex sets is convex.
*b)* Every polyhedron is a convex set.
*c)* The convex combination of finitely many elements of a convex set is also in the set.
*d)* The convex hull of finitely many vectors is a polyhedron so it is a convex set.

**Definition.** Let ${P}$ be a polyhedron. A vector ${x \in P}$ is an *extreme point* of ${P}$ if ${\not\exists y_1z \in P (y \neq x, z \neq z)}$ and ${\lambda \in [0,1]}$ such that ${x = \lambda y + (1-\lambda)z}$

![[Lesson 8 2025-02-11 11.06.05.excalidraw]]

${x}$ is a convex combination of ${y}$ and ${z}$,
${x}$ is *NOT* an extreme point

pick ${y \in P}$, ${y \neq x}$
then ${x = \lambda y + (1-\lambda)z \implies z \notin P}$.

**Definition.** Let ${P}$ be a polyhedron. A vector ${x \in P}$ is a *vertex* of ${P}$ if ${\exists\,c \in \mathbb{R}^n}$ such that ${c^Tx < c^Ty \,\forall\, y \in P, y\neq x}$

So linear optimization really amounts to finding the best supporting hyperplane.

**Definition.** A constraint ${f(x) \le b}$ or ${f(x) = b}$ is said to be *active* at ${x}$ if ${f(x) = b}$

**Theorem 2.2.** Let ${x \in \mathbb{R}^n}$ and ${I = \{i\,|\,a_i^Tx = b_i\}}$ be the index set of active constraints at ${x}$.
Then the following are equivalent.
*a)* There exists ${n}$ vectors in ${\{a_i\,|\,i \in I\}}$ which are linearly independent.
*b)* ${\text{span}\{a_i\,|\,i \in I\} = \mathbb{R}^n}$.
*c)* ${\{a_i^Tx = b_i\,|\,i \in I\}}$ has a unique solution.

| Point | Active Constraints | Feasible | Theorem 2.2 | Basic Feasible Solution |
| ----- | ------------------ | -------- | ----------- | ----------------------- |
| u     | 2,3                | Yes      | T           | Yes                     |
| v     | None               | Yes      | F           | No                      |
| w     | 1,2                | No       | T           | No                      |
| x     | 4                  | Yes      | F           | No                      |
| y     | None               | No       | F           | No                      |
| z     | 2,5,6              | Yes      | T           | Yes                     |

Feasibility has *nothing* to do with active constraints.

**Definition.** Consider polyhedron ${P}$ defined by linear equality and inequality constraints, and let ${x \in \mathbb{R}^n}$.
*a)* ${x}$ is a *basic solution* if 
*i)* An equality constraints are active.
*ii)* ${\text{span}\{a_i\,|\, i \in I\} = \mathbb{R}^n}$
*b)* If ${x}$ is a basic solution that satisfies all constraints, then ${x}$ is a *basic feasible solution*.

**Theorem 2.3** Let ${P}$ be a nonempty polyhedron and let ${x \in P}$. Then the following are equivalent.
*a)* ${x}$ is a vertex of ${P}$
*b)* ${x}$ is an extreme point of ${P}$.
*c)* ${x}$ is a basic feasible solution.

___

### **Polyhedra in Standard Form**

**Definition** A standard form polyhedron is a polyhedron which is represented as ${P = \{x \in \mathbb{R}^n | Ax = b, x \ge 0\}}$  for ${m \times n}$ matrix ${A}$ of rank ${m}$ and vector ${b \in \mathbb{R}^m}$.

Always in positive quadrant
Intersection of positive quadrant with any constraints.

${\dim(n-m) = 2}$ 
${m}$ is number of constraints
${\mathbb{R}^n}$
___

**Theorem 2.4.** Vector ${x \in \mathbb{R}^n}$ is a basic solution of standard form polyhedron ${P = \{x \in \mathbb{R}^n \,|\, Ax = b, x \ge 0\}}$ if and only if ${Ax = b}$ and there exists indices ${B(1),...,B(m)}$ such that:
*a)* ${\{A_{B(1)},...,A_{B(m)}\}}$ is linearly independent
*b)* If ${i \in \{B(1),...,B(m)\}}$ then ${x_i = 0}$

${A = \begin{bmatrix} 1 & 2 & 1 \\ 2 & -1 & 1 \end{bmatrix}}$,

${b = \begin{bmatrix} 3 & 4 \end{bmatrix}}$

${n = 3}$
${m = 2}$

Suppose ${B(1) = 1}$, ${B(2) = 3}$

${B = \begin{bmatrix} A_{B(1)} A_{B(2)} \end{bmatrix} = \begin{bmatrix} 1 & 1 \\ 2 & 1 \end{bmatrix}}$

${B}$ is invertible (if ${\{A_{B(1)} A_{B(2)}\}}$ is linearly independent)

Set ${x_2 = 0}$ because ${2 \not\in \{B(1), B(2)\}}$
${Ax = b}$ in this case becomes
${Bx_B = b}$
${x_B = \begin{bmatrix} 1 \\ 2\end{bmatrix}}$

${x = (1,0,2)}$ is a basic solution.

${x}$ is also a basic feasible solution because ${x \ge 0}$.

${\{B(1), ..., B(m)\}}$ is called a *basis* if ${B(\text{matrix})}$ is invertible

**Procedure for Constructing Basic Solutions**

*1)* Choose ${m}$ linearly independent columns of ${A: A_{B(1)}, ..., A_{B(m)}}$
*2)* Set ${x_i = 0}$ for all ${i \notin \{B(1),...,B(m)\}}$.
*3)* Solve ${Ax =b }$ for ${x_{B(1)}, ..., x_{B(m)}}$

**Definition.** Let ${x}$ be a basic solution of a standard form polyhedron. The variables ${x_{B(1)},...,x_{B(m)}}$ are called *basic variables* and all other variables are called *non-basic variables*.

**Definition.** Bases ${\{B(1),...,B(m)\}}$ and ${\{B'(1),...,B'(m)\}}$ of the same standard form polyhedron are *distinct bases* if the unordered sets do not contain the same elements, and are *adjacent bases* if the unordered sets differ in exactly one element each.

Two distinct basic solutions are adjacent if there are exactly ${n-1}$ linearly independent constraints acting at once.

Two bases are adjacent if they share all but one index.

These are not the same concept. Adjacent basic solution can be obtained from adjacent bases, adjacent bases may not lead to adjacent basic solutions. But if the two basic solutions are distinct, then they're adjacent.

Each basic solution can have multiple differing bases representing it.

**Theorem 2.5** Let ${P = \{x \in \mathbb{R}^n \,|\,Ax = b, x \ge 0\}}$ be a nonempty polyhedron where ${A}$ is ${m \times n}$ and ${A}$ has rank ${k < m}$ Suppose ${\{a_1,...,a_k\}}$ is linearly independent and let ${I = \{i_1,...,i_k\}}$. Then ${P = Q = \{x \in \mathbb{R}^n \,|\,ae_i^Tx = b_i, x \ge 0, i \in I\}}$

*Degeneracy*
**Definition** A basic solution ${x \in \mathbb{R}^n}$ is said to be *degenerate* if more than ${n}$ of the constraints are active at ${x}$.

**Definition.** Consider standard form polyhedron ${P = \{x \in \mathbb{R} \,|\, Ax = b, x \ge 0 \}}$ and let ${x}$ be a basic solution. Let ${m}$ the number of rows of ${A}$. The vector ${x}$ is a *degenerate* basic solution if more than ${n-m}$ of the components of ${x}$ are zero.

___

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