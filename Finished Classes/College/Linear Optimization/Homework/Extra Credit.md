**Charles Liu**
Linear Optimization - Dr. Tom Asaki
February 5th 2025

___

## **Extra Credit Challenge**

**Construct linear constraints that model the given situation (where all variables are binary)**

>[!question] 1
>${x = 1}$ or ${y = 1}$

This is an *OR* operation, so our constraints are:

*Linear constraint:*
${x + y \ge 1}$

>[!question] 2
>${ x = 1}$ xor ${y =1}$

*Linear constraint:*
${x + y = 1}$

>[!question] 3
>Exactly ${5}$ of ${\{x_1,x_2...x_n\}}$ are ${1}$.

*Linear constraint:*
${x_1 + x_2 + ... x_n = 5}$

>[!question] 4
>If ${x = 1}$ then ${y = 1}$


*Linear constraint:*
${x = y}$

>[!question] 5
>If ${x = 1}$, then ${ y = 0}$

*Linear constraint:*
${x + y = 1}$

>[!question] 6
>If ${x_1 = 1}$ and ${x_2 = 1}$ then ${x_3 = 0}$


*Linear constraint:*
${(x_1+x_2) + x_3 = 1}$

>[!question] 7
>If ${x_1 = 1}$ and ${x_2 = 0}$ then ${x_3 = 0}$

*Linear constraint:*
${x_1 - x_2 + x_3\le 1}$

>[!question] 8
> ${x = y_1 \vee y_2}$

*Linear constraint:*

${y_1 + y_2 \ge x}$

>[!question] 9
>${x = y_1 \land y_2}$

*Linear constraint:*

${y_1 + y_2 \ge 2x}$
___

### **Table of Operations for Reference**

For ${x,y}$ binary variables,

| **Operation** |                       |
| ------------- | --------------------- |
| AND           | ${x + y = 2}$   |
| OR            | ${x + y \ge 1}$ |
| NAND          | ${x + y \le 1}$ |
| NOR           | ${x + y = 0}$   |
| XOR           | ${x + y = 1}$   |

*Constructed By Observing the Sums of Binary Variables in a K-map*
![[Extra Credit 2025-02-05 10.11.59.excalidraw]]
___
