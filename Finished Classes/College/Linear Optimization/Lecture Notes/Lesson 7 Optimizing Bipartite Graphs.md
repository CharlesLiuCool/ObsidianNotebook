### Transportation Problems

![[Lesson 7 2025-02-04 10.43.30.excalidraw]]

Let ${w_{ij}}$ be the given per unit cost of shipping from source ${i}$ to destination ${j}$.

Let ${x_{ij}}$ be the number of units shipped from source ${i}$ to destination ${j}$.

Compose a MIP for minimizing costs of shipping while meeting demand and not exceeding supply.

${\min z = \sum\limits_{i=1}^m\sum\limits_{j=1}^n w_{ij} x_{ij}}$
${\text{s.t. } \sum\limits_{i=1}^mx_{ij} \ge d_j \forall j}$
${\sum\limits_{j-1}^nx_{ij} \le s_i \forall i}$
${x \ge 0}$
${x \in \mathbb{Z}^{mn}}$

Let ${s = \sum\limits_{i=1}^m s_i, D = \sum\limits_{j=1}^nd_j}$

If ${S<D}$ then this IP is *infeasible*. (and has no solution).
If ${S > D}$ then this IP is *feasible*. (and has solution(s)).

${\sum\limits_{i=1}^m x^{*}_{ij} = d_j \forall j}$

If ${S = D}$ then 
*Standard Form*
${\sum\limits_{i=1}^mx^{*}_{ij} = d_{i} \forall j}$
${\sum\limits_{j=1}^n = d_j\;\forall\;j}$
${\sum\limits_{i=1}^n x^{*}_{ij} = s_i\;\forall\;i}$

${\implies}$ we don't need "${\ge}$", "${\le}$" and can replace with ${"="}$
Called a *"Balanced Problem"*.

### Creating a Balanced Problem

(a) ${S \ge D}$
Create a virtual destination with demand ${d_{n+1} = S - D}$

${\sum\limits_{i=1}^{m} s_i = \sum\limits_{j=1}^{n+1}d_j}$
- What is ${x_{i,n+1}}$?

Number of units remaining at source ${i}$.

- What is ${w_{i,n+1}}$?

maybe zero
maybe infinite (force shipping)
maybe per unit storage cost

(b) ${S \le D}$
create a virtual source with supply ${S_{m+1} = D - S}$

${\sum\limits_{i=1}^{m+1}s_i = \sum\limits_{j=1}^nd_j}$

- What is ${x_{i,n+1}}$?

Number of units needed at destination ${j}$ that you have to find from another source.

- What is ${w_{i,n+1}}$?

How much that outsourcing is going to cost per unit

___

**Implementing Fixed Fees**
Add a fixed source-destination cost.
If ${x_{ij} > 0}$, then a cost ${f_{ij}}$ is incurred regardless of the value of ${x_{ij}}$

Introduce binary variables.
${y_{ij} = \begin{cases} 1 & \text{if }x_{ij} \ge 0 \\ 0 & \text{if }x_{ij} = 0 \end{cases}}$

${\min z = \sum\limits_{i=1}^m\sum\limits_{j=1}^n w_{ij}x_{ij} + f_{ij}y_{ij}}$
${\text{s.t. } \sum\limits_{i=1}^m x_{ij} \ge d_j \;\forall\;j}$
${\sum\limits_{j=1}^n x_{ij} \le s_i \;\forall\;i}$
${y_{ij} \ge x_{ij}/s_{ij}\;\forall\;i,j}$

${x \ge 0}$
${x \in \mathbb{Z}^{mn}}$
${y \in \{0,1\}^{mn}}$

If ${x_{ij} > 0}$, ${y = 1}$ since ${0 < x_{ij}/s_i \le 1}$
We don't need to deal with ${x_{ij} = 0}$ since the objective function is always gonna take ${y = 0}$.

___

*Challenge:* Construct linear constraints that model the given situation:

${(1)\;x \in [a,b]}$
${a \le x \le b}$
${(2)\;x \in[c,d]}$
${c \le x \le d}$
${(3)\;x\in[a,b] \text{ or }x \in [c,d]}$

${y \in \{0,1\}}$
${ay + c(1-y) \le x \le by + d(1-y)}$

${x \le b}$
${(4)\; x \text{ is one greater than a multiple of 3}}$
${x = 3n +1}$
${n \in \mathbb{Z}}$

${(5)\;x\in\{2,7,8,12,20\}}$

${x = 2y_1 + 7y_2 + 8y_3 + 12y_4 + 20y_5}$
${y_1+y_2+y_3+y_4+y_5 = 1}$
${y\in\{0,1\}^5}$

${(6)\;y\le|x|}$
${y \le x}$
${y \le -x}$

${(7)\;Ax\le b \text{ or }Cx \le d}$

**Challenge** Construct linear constraints that model the given situation (where all variables are binary)

${(1)\;x=1 \text{ or } y=1}$
${}$