| 0               | 0           | 0           | 0           | ${\delta}$ | 3            | ${\gamma}$ | ${\epsilon}$ |
| --------------- | ----------- | ----------- | ----------- | ---------------- | ------------ | ---------------- | ------------------ |
| ${\beta}$ | ${0}$           | ${1}$           | ${0}$           | ${\alpha}$ | ${1}$  | ${0}$      | ${3}$        |
| ${2}$     | ${0}$ | ${0}$ | ${1}$ | ${-2}$     | ${2}$  | ${\eta}$   | ${-1}$       |
| ${3}$     | ${1}$ | ${0}$ | ${0}$ | ${0}$      | ${-1}$ | ${2}$      | ${1}$        |

*a)* The current point is a nonoptimal basic feasible solution.
${Ax = b}$
${x \ge 0}$
${\beta \ge 0}$
Suppose ${\delta < 0 \implies \alpha, \beta > 0}$ ensures a finite step size improving ${z}$

${\alpha, \beta > 0}$, ${\delta < 0}$, ${\gamma, \eta, \xi \in \Bbb{R}}$

*b)* Current point is infeasible.
${\beta < 0, \alpha, \delta, \eta, \delta, \xi \in \Bbb{R}}$

*c)* The problem is unbounded.
${\beta \ge 0, \delta < 0, \alpha < 0}$

*d)* The current basic feasible solution is degenerate.
${\beta = 0}$

*e)* Degenerate and optimal
${\beta = 0,  \gamma \ge 0, \delta \ge 0, \xi \ge 0}$

*f)* The current point is optimal with ${\delta < 0}$.
${\beta = 0, \delta < 0, \alpha > 0, \gamma, \eta, \xi \in \Bbb{R}}$ (maybe?)

*g)* The problem has exactly one optimal point and ${z^* < 0}$

### **Degeneracy and the Simplex Method**

*Bland's Rule*
- smallest ${j}$ for which ${\bar{c_j} < 0}$
- smallest ${i}$ for which ${x_i}$ passes ratio test.


### **Duality Theory**

*Primal Problem*
${\begin{align} \min\; &c^T x \\ \text{s.t. } &Ax = b \\ &x \ge 0\end{align}}$

Consider a *"relaxed"* problem

${\begin{align} \min\; &c^Tx + P^T(b-Ax) \\  \text{s.t. } &x \ge 0 \end{align}}$

${P^T}$ is a penalty term. If you don't satisfy the equality constraint, you make the objective worse.

Let ${g(p)}$ be the optimal cost of (${R}$)
${\begin{align} g(p) &= \min\limits{x \ge 0}\; c^Tx + P^T(b-Ax) \\ &\le c^Tx^* + P^T(b-Ax^*) \\ &= c^Tx^* \\ &= z^*\end{align}}$

${g(p)}$ is a lower bound for ${z^* = c^Tx^*}$ for all ${p}$.

${\begin{align} \max\;&g(P) \\  \text{s.t. } &p \in \Bbb{R}^m \end{align}}$

Now 
${\begin{align} g(p) &= \min\limits_{x \ge 0} c^Tx + P^T(b-Ax) \\ \\  & = p^Tb + \min\limits_{x \ge 0} (c^T - P^TA)x \\ \\ &= P^TB + \begin{cases} 0 & \text{if } c^T-P^TA \ge 0 \\ -\infty & \text{otherwise} \end{cases} \end{align}}$

${\begin{align} \max\;  &P^Tb  \\ \text{s.t. } &c^T - P^TA \ge 0 \end{align}}$

Rearranging this, we get

${\begin{align} \max\;&b^TP \\ &A^TP \le c \\ &p \in \Bbb{R}^m \end{align}}$

The dual problem of a LP is also a LP

The dual of a dual should be the primal problem (checking method)

The dual objective provides the best lower bound on the primal problem objective

${w^* \le z^*}$

**Theorem.** (Weak Duality)
If ${x}$ is primal feasible and ${p}$ is dual feasible, then
$${b^Tp \le c^Tx}$$

The objective value of a feasible point in the dual problem can never exceed the objective value of every feasible point in the primal problem.

*Proof:*
Define ${u_i = p_i(a_i^Tx - b_i)}$
and ${v_i = (c_j - p^TA_j)x_j}$

Let ${x}$ and ${p}$ be primal and dual feasible respectively

Notice that ${u_i \ge 0}$ and ${v_j \ge 0\,\forall\,i,j}$
${0 \le \sum u_i + \sum v_i}$
${= p^T(Ax-b) + (c^T - p^TA)x}$

${c^Tx \ge b^TP}$

*Corollary 4.1*
${a)}$ If ${z^* = -\infty}$ then the dual problem is infeasible
${b)}$ If ${w^* = \infty}$ then the primal problem is infeasible

*Corollary 4.2*
If ${c^Tx = b^TP}$ then ${x,p}$ are primal and dual optimal respectively.

**Theorem.** (Strong Duality)
If a primal problem has an optimal solution then so does the dual, and ${w^* = z^*}$

The previous Theorems and Corollaries lead to the following complete list of the ${4}$ possibilities of relations between primal and dual.

Primal, Dual
1. optimal exists, optimal exists
2. unbounded, infeasible
3. infeasible, unbounded
4. infeasible, infeasible

**Theorem.** (Complimentary Slackness)

${x}$ and ${p}$ are optimal if and only if ${u_i = 0\,\forall\,i}$ and ${v_j = 0 \forall j}$

${u_i = p_i(a_i^Tx - b_i)}$
${v_i = (c_j - p^TA_j)x_j}$

*Proof:*
${c^Tx - b^Tp = \sum u_i + \sum v_j }$
If ${c^Tx = b^Tp}$ then ${\sum u_i + \sum v_j = 0}$
${\implies u_i = 0, v_j = 0, \forall i,j}$

${u_i = p_i(a_i^Tx - b_i) = 0}$
${\implies}$ either ${a_i^Tx = b_i}$ (the ${i}$th primal constraint is active)
or ${p_i = 0}$ (the ${i}$th dual variable is zero)
or both.

${v_j = (c_j - p^TA_j)x_j = 0}$
${\implies}$ either ${A_j^Tp = c_j}$
or ${x_j = 0}$
or both.

Notice what happens at a nondegenerate optimal basic feasible solution.
${(c^T-p^TA)x = 0}$
${c_B^T - p^TB = 0}$
${p^T = c_B^TB^{-1}}$