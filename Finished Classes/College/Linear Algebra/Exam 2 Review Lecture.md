---
tags: Linear_Algebra, MATH_220, Mathematics
---

## Linear Transformations

### Standard Matrix

### Example 1.

Find the standard matrix for the linear transformation ${T}$: ${\mathbb{R}^2 \rightarrow \mathbb{R}^4}$, where ${T}$ is defined by

$${T\left(\begin{bmatrix} x_1 \\ x_2\end{bmatrix}\right) = \begin{bmatrix} 7x_1 + 2 x_2 \\ -x_1 \\ 3x_2 \\ x_1 - x_2\end{bmatrix}}$$

#### Solution:

Standard basis of ${\mathbb{R}^2}$ 

$${e_1 = \begin{bmatrix} \,1\, \\ 0 \end{bmatrix},\;\;\;\;e_2 = \begin{bmatrix} 0 \\ 1\end{bmatrix}}$$
$${T(e_1) = T\left(\begin{bmatrix} 1 \\ 0\end{bmatrix} \right) = \begin{bmatrix} 7 \\ -1 \\ 0 \\ 1\end{bmatrix}}$$
$$${T(e_2) = T\left( \begin{bmatrix} 0 \\ 1\end{bmatrix} \right) = \begin{bmatrix} 2 \\ 0 \\ 3 \\ -1 \end{bmatrix}}$$
So the standard matrix of ${T}$ is 

$${A = [\;T(e_1)\;\;\;T(e_2)\;] = \begin{bmatrix} 7 & 2 \\ -1 & 0 \\ 0 & 3 \\ 1 & -1 \end{bmatrix}}$$
### [Domain and Codomain](1.8%20Introduction%20to%20Linear%20Transformation.md)

### Example 2.

Let ${T}$: ${\mathbb{R}^n \rightarrow \mathbb{R^m}}$ be a linear transformation given by ${T(x) = Ax}$ where 

$$\underbrace{\large{A = \begin{bmatrix} -1 & 1 & -3 & -6 \\ -3 & 3 & -8 & -16 \\ 2 & -2 & 7 & 15\end{bmatrix}}}_{\huge{\text{Standard Matrix for T}}}$$
**(1)** What's the domain of ${T}$?
**(2)** What's the codomain of ${T}$?

### Solution

${A = 3 \times 4}$ matrix

$${\underbrace{\begin{bmatrix} -1 & 1 & -3 & -6 \\ -3 & 3 & -8 & -16 \\ 2 & -2 & 7 & 15 \end{bmatrix}}_{\huge{3 \times 4}} \underbrace{\begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix}}_{\huge{4 \times 1}} = \begin{bmatrix} -x_1 + x_2 -3x_3 - 6x_4 \\ -3x_1 + 3x_2 -8x_3 -16x_4 \\ 2x_1 -2x_2 + 7x_3 +15x_4\end{bmatrix}}$$
**(1)** domain (input space) is ${\mathbb{R}^4}$ 

**(2)** codomain (output space) is ${\mathbb{R}^3}$ 

### 1 - 1 vs. Onto

### Example 3.

Let ${T}$: ${R_4 \rightarrow R_3}$ be a linear transformation given by ${T(x) = Ax}$ where 

$${A = \underbrace{\begin{bmatrix} -1 & 1 & -3 & -6 \\ -3 & 3 & -8 & -16 \\ 2 & -2 & 7 & 15 \end{bmatrix}_{3 \times 4}}_{\huge{\text{standard matrix for T}}}}$$
**(1)** Is ${T}$ *onto*? (or ${Ax = b}$ has at least one solution for every ${b}$ in ${\mathbb{R}^m}$)

**(2)** Is ${T}$ *1-1*? (or ${Ax = b}$ has at most one solution for every ${b}$ in ${\mathbb{R}^m}$)

#### Solution Key:

$${T \text{ is onto} \iff A \text{ has a pivot in every row}}$$
$${T \text{ is 1-1} \iff A \text{ has a pivot in every column}}$$
Note that by row reduction (ERO), we find an EF of ${A}$ 

$${A = \begin{bmatrix} -1 & 1 & -3 & -6 \\ -3 & 3 & 8 & -16 \\ 2 & -2 & 7 & 15 \end{bmatrix} \xrightarrow {\Huge{\text{ERO}}} \underbrace{\begin{bmatrix} \fbox{1} & -1 & 3 & 6 \\ 0 & 0 & \fbox{1} & 2 \\ 0 & 0 & 0 & 1 \end{bmatrix}}_{\Huge{EF}}}$$
**(1)** So we see that ${A}$ has a pivot in every row, which implies that ${T}$ is *ONTO*.

**(2)** But ${A}$ does *NOT* have pivot in every column, which shows that ${T}$ is *NOT* 1-1.

### Matrix Operations

- *Matrix Addition*
- *Scalar Multiplication*
- *Matrix Transpose*
- *Matrix Multiplication*
#### Example 4.

Given the matrices ${A}$, ${B}$, ${C}$, and ${D}$, compute the following if defined, otherwise explain why it is undefined

$${A \begin{bmatrix} 1 & -1 \\ 0 & 3 \\ 2 & 0 \end{bmatrix},\;\;\;B=\begin{bmatrix} 1 & 0 & -1 \\ -2 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix},\;\;\;C = \begin{bmatrix} 3 & -1 \\ 9 & 3 \end{bmatrix},\;\;\;D = \begin{bmatrix} 2 & 4 \\ 1 & 2\end{bmatrix}}$$

**(a)** ${3A}$

${3A = 3 \times \begin{bmatrix} 1 & -1 \\ 0 & 3 \\ 2 & 0 \end{bmatrix} = \begin{bmatrix} 3 & -3 \\ 0 & 9 \\ 6 & 0 \end{bmatrix}}$

**(b)** ${B + C}$

Matrix Addition requires matrices of the *same dimensions*. You cannot add a ${3 \times 3}$ with a ${2 \times 2}$

**(c)** ${C + 2D}$


${C + 2D = \begin{bmatrix} 3 & -1 \\ 9 & 3 \end{bmatrix} + 2 \times \begin{bmatrix} 2 & 4 \\ 1 & 2 \end{bmatrix} = \begin{bmatrix} 3 & -1 \\ 9 & 3 \end{bmatrix} + \begin{bmatrix} 4 & 8 \\ 2 & 4 \end{bmatrix} = \begin{bmatrix} 7 & 7 \\ 11 & 7 \end{bmatrix}}$

**(d)** ${A^T = \begin{bmatrix} 1 & -1 \\ 0 & 3 \\ 2 & 0 \end{bmatrix}^{T} = \begin{bmatrix} 1 & 0 & 2 \\ -1 & 3 & 0 \end{bmatrix}}$

**(e)** ${BC}$ is undefined as

$${B_{\huge{3\times\fbox{3}}}\;\;\large{C_{\huge{\fbox{2}\times2}}}}$$

the inner dimensions do *NOT* match

**(f)** ${CA^T}$

${C A^T = \begin{bmatrix} 3 & -1 \\ 9 & 3 \end{bmatrix} \begin{bmatrix} 1 & 0 & 2 \\ -1 & 3 & 0 \end{bmatrix} = \begin{bmatrix} 3 \times 1 + (-1) \times (-1) & 3 \times 0 + (-1) \times 3 & 3 \times 2 + (-1) \times 0 \\ 9 \times 1 + 3 \times (-1) & 9 \times 0 + 3 \times 3 & 9 \times 2 + 3 \times 0 \end{bmatrix}}$
${= \begin{bmatrix} 4 & -3 & 6 \\ 6 & 9 & 18 \end{bmatrix}}$

___

### Example 5. 

Given the dimensions of matrix ${A}$, ${B}$, ${C}$, and ${D}$, determine the dimensions of the matrices below or write "*NOT* defined".

$${A\;\;\;4\times2\;\;\;\;\;\;B\;\;\;5\times2\;\;\;\;\;\;C\;\;\;2\times3\;\;\;\;\;D\;\;\;3\times5}$$

**(a)** ${4A}$ has the same dimension as ${A}$ and hence ${4A}$ is ${4 \times 2}$

**(b)** ${B_{5 \times 2}\;C_{2\times3}}$  is ${5 \times 3}$ Since the inner dimensions match and the outer dimensions is ${5 \times 3}$.

#### Tags

>[!quote] Tags:
> [[Linear Algebra Information|Linear Algebra Information]]

