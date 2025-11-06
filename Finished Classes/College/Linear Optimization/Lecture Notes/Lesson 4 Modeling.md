### Example Conversion to Standard Form

*Converting*
${\min w = -38y_1 -33y_2 + 51x_1 + 11x_2 + 40x_3}$
${s.t. y -4x_1-x_2-3x_3 = 0}$
${\;\;\;\;y_2-3x_1-x_2-4x_3 = 0}$
${\;\;\;\;3x_1+x_2+5x_3 \le 8,000,000}$
${\;\;\;\;5x_1 + x_2 + 3x_3 \le 5,000,000}$

${0 \le x < \infty}$
${0 \le y < \infty}$
${x \in \mathbb{R}^3}$
${y \in \mathbb{R}^2}$

*Converted*
${\min w = -38y_1 -33y_2 + 51x_1 + 11x_2 + 40x_3}$
${s.t. y -4x_1-x_2-3x_3 = 0}$
${\;\;\;\;y_2-3x_1-x_2-4x_3 = 0}$
${\;\;\;\;3x_1+x_2+5x_3 + x_4 = 8,000,000}$
${\;\;\;\;5x_1 + x_2 + 3x_3 + x_5 = 5,000,000}$

${0 \le x < \infty}$
${0 \le y < \infty}$
${x \in \mathbb{R}^5}$
${y \in \mathbb{R}^2}$

${\min w = c^T v}$
${s.t. Av = b}$
${v \ge 0}$
${v \in \mathbb{R}^7}$
is ${A}$ full rank?

**Exercise 1.4**

Consider the problem 
${\min z = 2x_1 + 3|x_2 - 10|}$
${s.t. |x_1+2| + |x_2| \le 5}$
${x \in \mathbb{R}^2}$

Reformulate as an equivalent linear program.

Optimization problem, but not linear. Absolute value is almost linear though, so it's pretty close.

${z = 2x_1 + 3 |x_2 - 10|}$
Let ${z = 2x_1 + 3(x_3 - 10)}$
Then add constraints ${x_3 \ge x_2 - 10}$ and ${x_3 \ge -(x_2 - 10)}$

note ${|x_2 - 10| = \max\{x_2-10, -(x_2-10)\}}$
then ${x_3^* = |x_2^* - 10|}$

>[!book] Equivalent Optimization Problem
${\min z = 2x_1 + 3x_3}$
${s.t. |x_1 + 2| + |x_2| \le 5}$
${x_3 \ge x_2 - 10}$
${x_3 \ge -x_2 + 10}$
${x \in \mathbb{R}^3}$

${\min z = 2x_1 + 3x_3}$
${s.t. |x_1+2| + |x_2| \le 5}$
${x_3 \ge x_2 - 10}$
${x_3 \ge -x_2 + 10}$
${x \in \mathbb{R}^3}$

${|x_1 + 2| \le 5- |x_2|}$


