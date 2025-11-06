**Charles Liu**
Linear Optimization - Dr. Tom Asaki
February 11th 2025

___

*Textbook:* Introduction to Linear Optimization - Dimitris Bertsimas and John N. Tsitsiklis

___

1. Determine whether or not the following sets are polyhedra.  Use clear reasoning and appeal to the definition of a polyhedron and/or relevant geometric theorems from Chapter 2 of the textbook. 

*(a)* ${\Omega_1 = \emptyset}$

>**Theorem.** ${\Omega_1 = \emptyset}$ is a polyhedron.
*Proof:*
By *Definition 2.1* in our textbook, a polyhedron is a set that can be described in the form ${\{x \in \mathbb{R}^n\,|\,Ax \ge b\}}$ where ${A}$ is an ${m \times n}$ matrix and ${b \in \mathbb{R}^m}$.
>
Take ${A}$ as the zero matrix, and ${b}$ as an all-ones matrix. This is an equivalent representation of the empty set, as no value of ${x \in\mathbb{R}^n}$ can satisfy the inequality ${Ax \ge b}$. Since the empty set can be described in the form from *Definition 2.1*, it is a polyhedron.

*(b)* ${\Omega_2 = \{x \in \mathbb{R} \,|\, x \ge 5, x\le 0\}}$

>**Theorem.** ${\Omega_2 = \{x \in \mathbb{R} \,|\, x \ge 5, x\le 0\}}$ is *NOT* a polyhedron.
*Proof:*
BWOC, assume that ${\Omega_2}$ is a polyhedron.
From *Theorem 2.1* in our textbook, every polyhedron must be convex, so ${\Omega_2}$ must be convex.
By *Definition 2.4* in our textbook, for ${x,y \in \Omega_2}$, ${\lambda x + (1-\lambda)y \in \Omega_2}$ must be satisfied for ${\Omega_2}$ to be convex.
Take ${x = 5, y = 0}$, and ${\lambda = 0.5}$. Since ${x,y \in \Omega_2}$ and ${\lambda \in [0,1]}$, ${\lambda x + (1-\lambda)y}$ should be in ${\Omega_2}$.
However, ${\lambda x + (1-\lambda)y = 0.5 \cdot 5 + 0.5 \cdot 0 = 2.5 \notin \Omega_2}$, a contradiction.
Thus, ${\Omega_2}$ is *NOT* a polyhedron.

*(c)* ${\Omega_3 = \{x \in \mathbb{R} \,|\, x^2 - 9 \le 0\}}$

>**Theorem.** ${\Omega_3 = \{x \in \mathbb{R} \,|\, x^2 - 9 \le 0\}}$ is a polyhedron.
>*Proof:*
Take ${Y_1 = \{x \in \mathbb{R} \,|\, -x \ge -3\}}$ and ${Y_2 = \{x \in \mathbb{R} \,|\, x \ge -3\}}$.
>
${x^2 - 9 \le 0}$
${\leftrightarrow x \le 3 \text{ and } x \ge -3}$
${\leftrightarrow -x \ge -3 \text{ and } x \ge -3}$
> 
> So ${\Omega_3 = Y_1 \cap Y_2}$.
> 
> By *Definition 2.1* in our textbook, ${Y_1}$ is a halfspace as it is in the form ${\{x \in \mathbb{R}\,|\,Ax \ge b\}}$.
> Similarly, ${Y_2}$ is a halfspace.
> 
> Since a polyhedron is an intersection of finite halfspaces and ${\Omega_3 = Y_1 \cap Y_2}$, ${\Omega_3}$ is a polyhedra.

*(d)* ${\Omega_4 = \{x \in \mathbb{R}^n \,|\,\,||x|| \le 1\}}$.

>**Theorem.** ${\Omega_4 = \{x \in \mathbb{R}^n \,|\,\,||x|| \le 1\}}$ is *NOT* a polyhedron.
>*Proof:*
>We can write that ${x = (x_1, x_2, ..., x_n)}$, where ${x \in \Bbb{R}^n}$. This means that ${||x|| = x_1^2 + x_2^2 + ... x_n^2}$. Since ${||x|| = x_1^2 + x_2^2 + ... x_n^2 \le 1}$is nonlinear, it must require an intersection of infinite halfspaces.
> Thus, ${\Omega_4}$ is *not* a polyhedron.

___

2. Let ${f}$: ${\mathbb{R}^n \to \mathbb{R}}$ be a convex function and let ${c}$ be some constant.  Prove that ${S = \{x \in \mathbb{R}^n\,|\,f(x) \le c \}}$ is convex.

>**Theorem.** ${S = \{x \in \mathbb{R}^n\,|\,f(x) \le c \}}$ is convex.
*Proof:*
>Let ${a,b \in S}$.
>By *Definition 1.1* in our textbook, since ${f}$ is convex,
>$${f(\lambda a + (1-\lambda)b) \le \lambda f(a) + (1-\lambda)f(b)}$$
>for ${\lambda \in [0,1]}$.
>
>It follows that
>$${f(\lambda a + (1-\lambda)b) \le c\lambda + (1-\lambda)c \le c}$$
>So,
>$${\lambda a + (1-\lambda)b \in S}$$
>and ${S}$ is convex by *Definition 2.4*.
___