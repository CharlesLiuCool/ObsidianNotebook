**Exercise 1.16** A manager of an oil refinery has 8 million barrels of crude oil ${A}$ and ${5}$ million barrels of crude oil ${B}$ allocated for production during the coming month. These resources can be used to make either gasoline, which sells for ${\$38}$ a barrel, or home heating oil, which sells for ${\$33}$ per barrel. There are three production processes with the following characteristics.

|                    | Process 1 | Process 2 | Process 3 |
| ------------------ | --------- | --------- | --------- |
| Input Crude A      | 3         | 1         | 5         |
| Input Crude B      | 5         | 1         | 3         |
| Output Gasoline    | 4         | 1         | 3         |
| Output Heating Oil | 3         | 1         | 4         |
| Cost                   |      $51    |    $11      |    $40      |

All quantities are in barrels. For example, with the first process, 3 barrels of crude A and 5 barrels of crude B are used to produce 4 barrels of gasoline and 3 barrels of heating oil. The costs in this table refer to variable and allocated overhead costs, and there no separate cost items for the cost of the crudes. Formulate a linear programming problem that would help the manager maximize net revenue over the next month.

*Decision Variables:*
Let ${x_k}$ be the number of times to run process ${k,\; k = 1,2,3}$.

Can barrels be partial?
**Case 1:** Barrel can be partial, in other words ${x \in \mathbb{R}^3}$
objective function:
${\max z = }$ (profit) = (revenue) - (cost) = ${38y_1}$ + ${33y_2 - 51 x_1 - 11 x_2 - 40 x_3}$ 
where ${y_1}$ is the number of barrels of gasoline produced
and ${y_2}$ is the number of home heating oil produced.

>[!tip] Note
Whenever dependent variables are created you must also create constraints connecting them to the independent variable (decision variable).

*Constraints*
Dependent variable constraints: 
${y_1 = 4x_1 + x_2 + 3x_3}$
${y_2 = 3x_1 + x_2 + 4x_3}$

Raw material constraints:
${3x_1 + x_2 + 5x_3 \le 8,000,000}$
${5x_1 + x_2 + 3x_3 \le 5,000,000}$

Sign restrictions:
${x, y \ge 0}$

**Case 2:**

>[!check] Linear Programming Model
>${\max z = 38y_1 + 33y_2 - 51x_1 - 11x_2 - 40x_3}$
such that
${y_1 = 4x_1 + x_2 + 3x_3}$
${y_2 = 3x_1 + x_2 + 4x_3}$
${3x_1 + x_2 + 5x_3 \le 8,000,000}$
${5x_1 + x_2 + 3x_3 \le 5,000,000}$
${x \ge 0}$
${y \ge 0}$
${x \in \mathbb{R}^3}$
${y \in \mathbb{R}^2}$

**MATLAB Python Form**

${\min w = -38y_1 -33y_2 + 51x_1 + 11x_2 + 40x_3}$
such that ${\;\;\;\;\;\;\;\;y_1\;\;\;\;\;\;\;\;\;\;\;\;\;\;-4x_1\;\;-x_2\;-3x_3 = 0}$
${\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;y_2 \;\;\;\;\;\;\;\;3x_1 \;\;-x_2 \; -4x_3 = 0}$
${\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;3x_1+ \;\;x_2 \;\;+ 5x_3 \le 8M}$
${\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\; 5x_1 +\;\; x_2 \;\;+ 3x_3 \le 5M}$

${ 0 \le x < \infty}$
${0 \le y < \infty}$
${x \in \mathbb{R}^3}$
${y \in\mathbb{R}^2}$

*MATLAB Python Matrix Form*

${w = c^Tv}$
such that ${Av = b}$
${A_ev \le b_e}$
${l \le v \le u}$
${v \in \mathbb{R}^5}$

${v^T = \begin{bmatrix} y_1 & y_2 & x_1 & x_2 & x_3 \end{bmatrix}}$
${c^T = \begin{bmatrix} -38 & -33 & 51 & 11 & 40 \end{bmatrix}}$

${A = \begin{bmatrix} 0 & 0 & 3 & 1 & 5 \\ 0 & 0 & 5 & 1 & 3\end{bmatrix}, b = \begin{bmatrix} 8M \\ 5M\end{bmatrix}}$

${A_e = \begin{bmatrix} 1 & 0 & -4 & -1 & -3 \\ 0 & 1 & -3 & -1 & -4\end{bmatrix}, b_e = \begin{bmatrix} 0 \\ 0 \end{bmatrix}}$

${l^T = \begin{bmatrix} 0 & 0 & 0 & 0 & 0\end{bmatrix}}$
${u^T = \begin{bmatrix} \infty & \infty & \infty & \infty & \infty \end{bmatrix}}$

___