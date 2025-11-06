**Example 2**
${\min z = 2x_1 - 3x_2 + x_3 + x_4}$
${\text{s.t. } x_1 - 2x_2 - 3x_3 - 2x_4 = 3}$
${x_1 - x_2 + 2x_3 + x_4 = 11}$
${x \ge 0, x\in \Bbb{R}^4}$



Add new slack variables (auxiliary variables) - and consider a new objective

${\min w = x_5 + x_6}$
${x_1 - 2x_2 - 3x_3 -2x_4 + x_5 = 3}$
${x_1 - x_2 + 2x_3 + x_4 + x_6 = 11}$
${x \ge 0, x\in \Bbb{R}^6}$

We solve this to find a feasible basis for the original problem.

If ${x_5, x_6 = 0}$, it finds a basic feasible solution.
If ${x_5, x_6 > 0}$, the equality constraints can never be satisfied in our original so the problem is infeasible.