**Charles Liu**
Linear Optimization - Dr. Tom Asaki
January 18th

___

Consider the linear program given below.  Use software to find optimal solutions for values of ${\delta}$ from ${0.3}$ to ${1.0}$ in steps of ${0.1}$.  Compare the solutions and make some observations regarding how solutions change with respect to ${\delta}$.  Repeat the solutions for the corresponding integer program ${(x \in \mathbb{Z}^4)}$ making some observations about any significant relationships between the two sets of solutions (other than integer/non-integer).

${\begin{align} &\max_{x} \delta x_1 + \delta x_2 + x_3 + x_4 \\ & \;\;\;\text{s.t}\;x_1 + 2x_2 + x_3 + 2x_4 \le 70 \\ & \;\;\;\;\;\;\;\,2x_1 + x_2 + 2x_3 + x_4 \le 50 \\ & \;\;\;\;\;\;\;\, x_1 + x_2 + x_3 + 3x_4 \le 62 \\ &\;\;\;\;\;\;\;\,x \ge 0 \\ &\;\;\;\;\;\;\;\,x \in \mathbb{R}^4\end{align}}$

___

### Linear Program

*Result from software:*
>${\delta = 0.3,\;x = [ 0,   0,  17.6, 14.8] }$
>
>${\delta = 0.4,\;x = [ 0,   0,  17.6, 14.8]}$
>
>${\delta = 0.5,\;x = [ 0,   0,  17.6, 14.8]}$
>
>${\delta = 0.6,\;x = [ 0, 19, 10, 11]}$
>
>${\delta = 0.7,\;x = [ 0, 19, 10, 11]}$
>
>${\delta = 0.8,\;x = [ 0, 19, 10, 11] }$
>
>${\delta = 0.9,\;x = [ 0, 19, 10, 11]}$
>
>${\delta = 1,\;x = [10, 19,  0, 11]}$

We can plug values of ${x = (x_1, x_2, x_3, x_4)}$ into the objective function to get the optimized values and plot those values on the y-axis. With ${\delta}$ on the x-axis, we get the following plot:

![[HW 2 Graphic 1.png]]

*Dissecting this result:*
- ${0.3 \le \delta \le 0.6}$

We can see that the optimized value of the objective function remains *constant* (${32.4}$) here. This is because ${x}$ remains constant and ${x_1 = x_2 = 0}$. Since ${\delta}$ is multiplied by ${x_1}$ and ${x_2}$ in the objective function, the function doesn't grow as ${\delta}$ grows since ${x_1 = x_2 = 0}$. Therefore, the value of the objective function is only reliant on ${x_3}$ and ${x_4}$, which remain constant, explaining the observed behavior.

- ${0.6 \le \delta \le 1}$

We can see that the optimized value of the objective function *grows linearly* here. This is because ${x_2}$ becomes a non-zero constants and remain that value for the remainder of the interval. Since ${\delta}$ is multiplied by ${x_2}$ in the objective function, ${\delta}$ will be proportional to the growth of the graph in this interval. Specifically, the objective function grows linearly at ${19 \times 0.1 = 1.9}$.

___

### Mixed Integer Program

*Result from software:*
>${\delta = 0.3,\;x = [ 0, 0,  18, 14] }$
>
>${\delta = 0.4,\;x = [ 0, 0,  18, 14]}$
>
>${\delta = 0.5,\;x = [ 0, 4,  16, 14]}$
>
>${\delta = 0.6,\;x = [ 0, 19, 10, 11]}$
>
>${\delta = 0.7,\;x = [ 0, 19, 10, 11]}$
>
>${\delta = 0.8,\;x = [ 0, 19, 10, 11]}$
>
>${\delta = 0.9,\;x = [ 0, 19, 10, 11]}$
>
>${\delta = 1,\;x = [0, 19,  10, 11]}$

We can plug values of ${x = (x_1, x_2, x_3, x_4)}$ into the objective function to get the optimized values and plot those values on the y-axis. With ${\delta}$ on the x-axis, we get the following plot:

![[HW 2 Graphic 2.png]]

*Dissecting this result:*
- ${0.3 \le \delta \le 0.5}$

We can see that the optimized value of the objective function remains *constant* (${32}$) here. 

For ${0.3 \le \delta \le 0.4}$, the value is constant because ${x}$ remains constant and ${x_1 = x_2 = 0}$. Since ${\delta}$ is multiplied by ${x_1}$ and ${x_2}$ in the objective function, the function doesn't grow as ${\delta}$ grows since ${x_1 = x_2 = 0}$. Therefore, the value of the objective function is only reliant on ${x_3}$ and ${x_4}$, which remain constant, explaining the observed behavior.

For ${\large{\delta = 0.5}}$, there is a change in the values of ${x}$. ${x_2}$ goes from ${0}$ to ${4}$ and ${x_3}$ decreases by ${2}$. Doing calculations by plugging into the objective function, we can see these changes counteract each other as ${4 \times \delta = 4 \times 0.5 = 2}$ and ${x_3}$ decreases by ${2}$. Therefore, the optimized value also remains the same.

- ${0.6 \le \delta \le 1}$

We can see that the optimized value of the objective function *grows linearly* here. This is because ${x_2}$ becomes a non-zero constants and remain that value for the remainder of the interval. Since ${\delta}$ is multiplied by ${x_2}$ in the objective function, ${\delta}$ will be proportional to the growth of the graph in this interval. Specifically, the objective function grows linearly at ${19 \times 0.1 = 1.9}$.

___

### Comparison Between LP and MIP

From the interval ${0.3 \le \delta \le 1}$, the main difference between the linear program and mixed integer program is the optimized value of the objective function on ${0.3 \le \delta \le 0.5}$.

In the *linear program*, the values of ${x}$ aren't restricted to integers so there is no rounding/integer conforming behavior.

In contrast, in the *mixed-integer program*, values of ${x}$ are restricted to integers so the optimized value which is constant on the interval ${0.3 \le \delta \le 0.5}$ is different. Specifically, since ${\delta}$ is irrelevant in this interval as ${x_1 = x_2 = 0}$, the optimized value is an integer (${32}$), which differs from the linear program where it is ${32.7}$.

In the remaining interval ${0.6 \le \delta \le 1}$, both programs yield the same result for optimized objective values. This is because in the linear program, the values for ${x}$ are already integers, the mixed-integer program doesn't need to do additional conforming. 

___

**Python Code for Reference**
```py
# Programmer: Charles Liu
# Date: 1/19/2025
# Class: Linear Optimization

import numpy as np
import scipy.optimize as opt
import matplotlib.pyplot as plt

d_list = []
opt_list = []

for d in np.arange(0.3, 1.1, 0.1):
    # coefficient vector for the objective function
    c=np.array([d, d, 1, 1])

    #coefficient array for inequality constraints (Ax <= b)
    A = np.array([[1, 2, 1, 2],\
    [ 2, 1, 2, 1],\
    [ 1, 1, 1, 3]])

    b = np.array([70 , 50, 62])

    bounds=((0, None),(0,None),(0, None),(0, None))
    isint = [1,1,1,1]
    res=opt.linprog(-c,A_ub=A,b_ub=b,bounds=bounds, integrality=isint)

    if res.success:
        #print(f"d = {d}: {res.fun}\n")
        print(f"{res.x} \n")
        d_list.append(d)  
        opt_list.append(-res.fun)    
    else:
        print(f"d = {d}: Optimization failed. \n")

# list of all delta values (0.3 to 1)
print(d_list)
print("\n")

# list of optimized outcome
print(opt_list)
print("\n")

# plot
plt.plot(d_list, opt_list)
plt.show()
```

___