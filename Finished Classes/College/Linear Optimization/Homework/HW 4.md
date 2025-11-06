**Charles Liu**
Linear Optimization - Dr. Tom Asaki
February 5th 2025

___

1. A farmer is planning an orchard of mixed apple, pear and cherry trees that can hold a maximum of $345$ trees.  The seasonal cost of labor per tree is $\$150$, $\$200$ and $\$240$, respectively.. The seasonal cost of materials per tree is $\$275$, $\$180$ and $\$125$, respectively. Planting logistics require that **IF** any apple trees are planted then at least $150$ must be planted. Similar limits on pear and cherry trees are ${50}$ and $80$, respectively.  Write and solve an optimization model that maximizes the number of trees which the farmer can plant when labor costs are limited to a maximum of $50,000 and materials costs are limited to a maximum of $60,000. 

${\max a + p + c}$

${y_1 = \begin{cases} 1 & a > 0 \\ 0 & a = 0 \end{cases}}$
${y_2 = \begin{cases} 1 & p > 0 \\ 0 & p = 0 \end{cases}}$
${y_3 = \begin{cases} 1 & c > 0 \\ 0 & c = 0 \end{cases}}$

${a + p + c \le 345}$
${150y_1 \le a \le 345y_1}$
${50y_2 \le p \le 345y_2}$
${80y_3 \le c \le 345y_3}$

${150a + 200p + 240c \le 50000}$
${275a + 180p + 125c \le 60000}$

To maximize planting, we plant ${172}$ apple trees, ${0}$ pear trees, and ${100}$ cherry trees for a total of ${272}$ trees.

2. Radio station KOPT is studying where to place radio towers in the hills around Dennis County. Four tower sites are under consideration. The costs of building on sites A, B, C and D are $3500, $4000, $4500 and $2700, respectively. A tower on each site can reach one or more of ten districts of varying populations as shown in the table below, where populations are shown in thousands. For example, sites B and D can both broadcast to district 7 which has a population of 12,000. Construct and solve an integer program the provides the maximum radio coverage, by population, if KOPT has $10,000 for construction. Be careful to count any covered district only once.  

|               |     |     |     |     |     |     |     |     |     |     |
| ------------- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Site\District | D1  | D2  | D2  | D4  | D5  | D6  | D7  | D8  | D9  | D10 |
| A             | $30$  | $12$  |     | $21$  | $13$  | 4   |     |     |     |     |
| B             |     | $12$  | $28$  |     | 13  | 4   | 12  | 20  |     |     |
| C             |     |     |     | $21$  | 13  | 4   |     | 20  | 11  | 25  |
| D             |     |     |     |     |     | 4   | 12  | 20  | 11  |     |


${\max D=yp}$

${p = \begin{bmatrix} 30 & 12 & 28 & 21 & 13 & 4 & 12 & 20 & 11 & 25 \end{bmatrix}^{T}}$

${y = \begin{bmatrix} y_1 & y_2 & y_3 & y_4 & y_5 & y_6 & y_7 & y_8 & y_9 & y_{10}\end{bmatrix}}$

Where
${y_i = \begin{cases} 1 & P_ix \ge 1 \\ 0 & P_ix = 0 \end{cases}}$

${P = \begin{bmatrix} P_1 & P_2 & P_3 & P_4 & P_5 & P_6 & P_7 & P_8 & P_9 & P_{10} \end{bmatrix}}$

${= \begin{bmatrix} 1 & 1 & 0 & 1 & 1 & 1 & 0 & 0 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 1 & 1 & 1 & 0 & 0 \\ 0 & 0 & 0 & 1 & 1 & 1 & 0 & 1 & 1 & 1 \\ 0 & 0 & 0 & 0 & 0 & 0 & 1 & 1 & 1 & 0 \end{bmatrix}}$

${x = \begin{bmatrix} A & B & C & D \end{bmatrix}}$

${3500 A + 4000B + 4500C + 2700D \le 10000}$

Putting this through software, we get that we should buy towers at ${B}$ and ${C}$, getting to ${146,000}$ people.