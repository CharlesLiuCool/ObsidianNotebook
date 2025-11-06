**Charles Liu**
Linear Optimization - Dr. Tom Asaki
January 14th 2025

___

### **Problem 1**

*Problem:* Prove that ${P = \{x \in \mathbb{R}^n\,|\,Ax = b, Cx \le d\}}$ is a convex set in ${\mathbb{R}^n}$, where ${A, b, C, d}$ are appropriately sized real matrices/vectors.

*Proof:* Suppose that ${x,y \in P}$. We want to show that ${\lambda x + (1-\lambda) y \in P}$ for ${0 \le \lambda \le 1}$.
$${A(\lambda x + (1-\lambda) y) = \lambda Ax + (1-\lambda)Ay = \lambda b + (1 - \lambda)b = b}$$
$${C(\lambda x + (1-\lambda) y) = \lambda Cx + (1-\lambda) Cy \le (\lambda + 1 - \lambda)d = d}$$

Since ${A(\lambda x + (1-\lambda) y) = b}$ and ${C(\lambda x + (1-\lambda) y) \le d}$, we can see that ${\lambda x + (1-\lambda) y \in P,}$ so ${P}$ is convex by definition.

___

### **Problem 2**

*Problem:* Suppose ${f_1, ... ,f_m}$ are convex functions from ${\mathbb{R}^n}$ into ${\mathbb{R}}$ and let ${f(x) = f_1(x) + ... + f_m(x)}$. Prove that ${f(x)}$ is convex.

*Proof:* Suppose ${f_1, ... ,f_m}$ are convex functions from ${\mathbb{R}^n}$ into ${\mathbb{R}}$ and let ${f(x) = f_1(x) + ... + f_m(x)}$. We want to show that ${f(\lambda x + (1-\lambda)y) \le \lambda f(x) + (1-\lambda) f(y)}$ for ${0 \le \lambda \le 1}$.

$${\begin{align} f(x) &= f_1(x) +\,...\,+ f_m(x) \\& \le [\lambda f_1(x) + (1-\lambda)f_1(y)] + ... + [\lambda f_m(y) + (1-\lambda) f_m(y)] \\ &= \lambda (f_1(x) + ... + f_m(x)) + (1-\lambda) (f_1(y) + ... + f_m(y)) \\ &= \lambda f(x) + (1-\lambda) f(y) \end{align}}$$

Since ${f(\lambda x + (1-\lambda)y) \le \lambda f(x) + (1-\lambda) f(y)}$, ${f(x)}$ is convex by definition.

___