1. A technician for a large animal shelter must formulate a diet from two commercial products, food $A$ and food $B$, for the reptiles. In ${200}$ grams of food $A$ there are ${16}$ grams of fat, ${28}$ grams of carbohydrate, and ${6}$ grams of protein. In ${200}$ grams of food B there are ${8}$ grams of fat, 50 grams of carbohydrate, and 10 grams of protein. The minimum daily requirements are 176 grams of fat, $980$ grams of carbohydrate, and 200 grams of protein. Food $A$ costs 8 cents per 100 grams and food $B$ costs 18 cents per 100 grams. Compose and solve an optimization model to answer the following question: What is the minimum cost diet that meets all daily requirements.

${\min M}$
${8A + 18B = M}$
${8A + 4B \ge 176}$
${14A + 25B \ge 980}$
${3A + 5B \ge 200}$

Where ${A,B}$ are in units of ${100}$ grams.

${M = 560}$, or ${\$5.60}$.

```cpp
# Programmer: Charles Liu
# Date: 1/19/2025
# Class: Linear Optimization

import numpy as np
import scipy.optimize as opt
import matplotlib.pyplot as plt

# coefficient vector for the objective function
c=np.array([8,18])


#coefficient array for inequality constraints (Ax <= b)

A = np.array([[-8,-4],\
[-14,-25],\
[-3,-5]])

b = np.array([-176 , -980, -200])

bounds=((0, None),(0,None))
isint = [1,1,1,1]
res=opt.linprog(c,A_ub=A,b_ub=b,bounds=bounds)

if res.success:
    #print(f"d = {d}: {res.fun}\n")
    print(f"{res.fun} \n")  
    print(f"{res.x}\n")
else:
    print("Optimization failed. \n")
```

![[HW 3 Graphic 2.png]]

2. A producer of trail mix has year-end left-over stock of peanuts, chocolate, raisins, pretzels and dried papayas.  They would like to make and sell a holiday mix from this stock.  The goal is to create a mix of these ingredients that has as close to ${235}$ calories per bag as possible.  Processing machinery dispenses each ingredient in integer unit amounts.  The following table describes the stock.

|   |   |   |
|---|---|---|
|**Item**|**Weight** (grams per unit)|**Calories** (calories per unit)|
|peanuts|6|35|
|chocolate|5|26|
|raisins|7|21|
|pretzels|4|15|
|papaya|8|4|

Any optimal recipe for trail mix must contain at least one unit of each of the five items.  The total bag weight cannot exceed ${57}$ grams (about ${2}$ oz.).  Construct a linear optimization model whose solution provides the optimal trail mix recipe.  Solve using software and present the solution.


**Least Deviation Method**

${\min z = 0x_1 + 0x_2 + 0x_3 + 0x_4 + 0x_5 +\delta}$

${\text{s.t. }}$
${\delta \ge 35x_1 + 26x_2 + 21x_3 + 15x_4 + 4x_5}$
${\delta \ge -35x_1  -26x_2 - 21x_3 - 15x_4 - 4x_5}$
${6x_1 + 5x_2 + 7x_3 + 4x_4 + 8x_5 \le 57}$
${x_1,x_2,x_3,x_4,x_5 \in \mathbb{N}}$
${\delta \in \mathbb{Z}}$.

The optimal trail mix recipe uses ${4}$ peanuts, ${1}$ chocolate, ${1}$ raisin, ${3}$ pretzels, and ${1}$ papaya contributing to a ${56}$ gram bag for a total of ${236}$ calories.

![[HW 3 Graphic 1.png]]