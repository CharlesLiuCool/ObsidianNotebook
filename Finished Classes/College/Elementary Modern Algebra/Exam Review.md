---
tags: MATH_320 Elementary_Modern_Algebra Mathematics
---


1. Prove that the set of all ${3 \times 3}$ matrices with real entries of the form
$${\begin{bmatrix} 1 & a & b \\ 0 & 1 & c \\ 0 & 0 & 1 \end{bmatrix}}$$
is a group. The group operation is defined by
$${\begin{bmatrix} 1 & a & b \\ 0 & 1 & c \\ 0 & 0 & 1 \end{bmatrix} \begin{bmatrix} 1 & d & e \\ 0 & 1 & f \\ 0 & 0 & 1 \end{bmatrix} = \begin{bmatrix} 1 & a+d & b+af + e \\ 0 & 1 & c+f \\ 0 & 0 & 1 \end{bmatrix}}$$

Nonempty
The identity matrix exists in the group.
Closed
Associativity
${A,B,C \in G}$, then ${A(BC) = (AB)C}$ since matrix multiplication is associative.

1. In a finite group, show that the number of nonidentity elements that satisfy the equation ${x^5 = e}$ is a multiple of ${4}$. What can you say if instead we are working over an infinite group?

2. Prove that if ${a}$ is the only element of order ${2}$ in a group, then ${a}$ lies in the center of the group.

${(gag^{-1})^2 = e}$

${gag^{-1} = a}$
${ga = ag}$

___

1. Write each of the following permutations as product of disjoint cycles, then give their order.

*a)* ${(1235)(357869)}$
${(123)(57869)}$
order = ${15}$

*b)* ${(123)(124)(345)}$
${(13245)}$
order = ${5}$

*c)* ${(12)(12)(12)(367)}$
${(12)(367)}$

*d)* ${(345)(245)(145)}$
${(13425)}$

2. Show that a permutation with odd order must be an even permutation.

A permutation in the odd order is of the form ${(a_1, a_2, ... a_{2k+1})}$ where ${k \in \mathbb{Z}}$.

3. Show that ${\Bbb{Z}}$ has infinitely many subgroups isomorphic to ${\Bbb{Z}}$.

Take ${\langle n \rangle}$ where ${n \neq 0}$. Each of these are subgroups of ${\mathbb{Z}}$ and unique, and since there are infinitely many ${n}$, there are infinitely many of these subgroups. For each, you can take the map ${\phi(x) = nx}$ which yields an isomorphism.