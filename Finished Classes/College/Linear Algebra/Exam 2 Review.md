---
tags: Linear_Algebra, MATH_220, Mathematics
---

**1. (a)** Find the standard matrix for the linear transformation ${T}$: ${\mathbb{R}^2 → \mathbb{R}^2}$ which first  
reflects about the line ${x_2 = x_1}$ and then rotates clockwise by ${90\degree}$.  

reflect about ${x_2 = x_1}$

${\begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix}}$

rotate clockwise by ${90 \degree}$ from there

${\begin{bmatrix} \cos(90\degree) & -\sin(90\degree) \\ \sin(90\degree) & \cos(90\degree) \end{bmatrix}}$

= ${\begin{bmatrix} 0 & -1 \\ 0 & 1 \end{bmatrix}}$

>**Recall:** Rotational matrix: $${\begin{bmatrix} \cos(\theta\degree) & -\sin(\theta\degree) \\ \sin(\theta \degree) & \cos(\theta\degree) \end{bmatrix}}$$ for $\theta$ degrees counter clockwise


**(b)** Find the standard matrix for the linear transformation ${T}$: ${\mathbb{R}^4 \rightarrow \mathbb{R}^3}$ where ${T}$ is  
defined by the formula  
$${T (x_1, x_2, x_3, x_4) = (7x_1 + 2x_2 − x_3 + x_4, x_2 + x_3, −x_1) }$$ Since the transformation is ${\mathbb{R}^4 \rightarrow \mathbb{R}^3}$, the size of the standard matrix must be ${3 \times 4}$. 

The standard matrix is
$${\begin{bmatrix} 7 & 2 & -1 & 0 \\ 0 & 1 & 1 & 0 \\ -1 & 0 & 0 & 0\end{bmatrix}}$$

___

**2.** Given the matrices ${A}$, ${B}$, ${C}$, and ${D}$ evaluate or write "is not defined":  

${A}$ =  ${\begin{bmatrix} 1 & −1  \\ 0 & 3 \\ 2 & 0 \end{bmatrix}}$ ,  ${B}$ =  ${\begin{bmatrix} 1 & 0 & −1 \\  −2 & 0 & 0  \\ 0 & 1 & 0  \end{bmatrix}}$ ,  ${C}$ =  ${\begin{bmatrix} 3 & −1  \\ 9 & 3  \end{bmatrix}}$,  ${D}$ = ${\begin{bmatrix} 2 & 4 \\  1 & 2 \end{bmatrix}}$ 

${v^T}$ =  ${\begin{bmatrix} \,2\, \\ 1 \\ 0 \end{bmatrix}}$ ,   ${u = \begin{bmatrix} 3 \\ 3 \\ 1 \end{bmatrix}}$  

**a) ${2D}$**
${2D = 2\times \begin{bmatrix} 2 & 4 \\ 1 & 2 \end{bmatrix} = \begin{bmatrix} 4 & 8 \\ 2 & 4 \end{bmatrix}}$

**b) ${AC}$**
${AC = \begin{bmatrix} 1 & −1  \\ 0 & 3 \\ 2 & 0 \end{bmatrix} \times \begin{bmatrix} 3 & −1  \\ 9 & 3  \end{bmatrix} = \begin{bmatrix} 1 \times 3 + (-1) \times 9 & 1 \times (-1) + (-1) \times 3 \\ 0 \times 3 + 3 \times 9 & 0 \times (-1) + 3 \times 3 \\ 2 \times 3 + 0 \times 9 & 2 \times (-1) + 0 \times (3) \end{bmatrix}}$

${= \begin{bmatrix}-6 & -4 \\ 27 & 9 \\ 6 & -2 \end{bmatrix} }$

**c) ${AB}$**

${\begin{bmatrix} 1 & −1  \\ 0 & 3 \\ 2 & 0 \end{bmatrix}}$ is a ${3 \times \fbox{2}}$ matrix

${\begin{bmatrix} 1 & 0 & −1 \\  −2 & 0 & 0  \\ 0 & 1 & 0  \end{bmatrix}}$ is a ${\fbox{3} \times 3}$ matrix

The inner product is not the same (# of columns of ${A \neq}$ # of rows of ${B}$ )

Thus, it is not defined.

**d) ${C^{−1}}$**

${\begin{bmatrix} 3 & −1  \\ 9 & 3  \end{bmatrix}^{- 1} = \huge{\frac{1}{3 \times 3 - (-1) \times 9}}\large{\begin{bmatrix} 3 & 1 \\ -9 & 3 \end{bmatrix} = \frac{1}{18} \begin{bmatrix} 3 & 1 \\ -9 & 3 \end{bmatrix} = \begin{bmatrix} \frac{1}{6} & \frac{1}{18} \\ -\frac{1}{2} & \frac{1}{6} \end{bmatrix}}}$

**e) ${D^{−1}}$**  

${\det(D) = \det \left(\begin{bmatrix} 2 & 4 \\  1 & 2 \end{bmatrix}\right) = 2 \times 2 - 1 \times 4 = 0}$

${D}$ is not invertible since its determinant is zero (by *IMT*)


**f) ${B^T}$** 

${\begin{bmatrix} 1 & 0 & −1 \\  −2 & 0 & 0  \\ 0 & 1 & 0  \end{bmatrix}^T = \begin{bmatrix} 1 & -2 & 0 \\  0 & 0 & 1  \\ -1 & 0 & 0  \end{bmatrix}}$

**g) ${C + D}$** 

${\begin{bmatrix} 3 & −1  \\ 9 & 3  \end{bmatrix} + \begin{bmatrix} 2 & 4 \\  1 & 2 \end{bmatrix} = \begin{bmatrix} 5 & 3 \\  10 & 5 \end{bmatrix}}$

**h) ${(C + D)^{T}}$** 

${\left(\begin{bmatrix} 3 & −1  \\ 9 & 3  \end{bmatrix}+ \begin{bmatrix} 2 & 4 \\  1 & 2 \end{bmatrix}\right)^T = \begin{bmatrix} 5 & 3 \\  10 & 5 \end{bmatrix}^T = \begin{bmatrix} 5 & 10 \\  3 & 5 \end{bmatrix}}$

**i) ${(C^{−1})^{T}}$**

${C^{-1} = \begin{bmatrix} \frac{1}{6} & \frac{1}{18} \\ -\frac{1}{2} & \frac{1}{6} \end{bmatrix}}$

${(C^{-1})^{T} = \begin{bmatrix} \frac{1}{6} & \frac{1}{18} \\ -\frac{1}{2} & \frac{1}{6} \end{bmatrix}^T = \begin{bmatrix} \frac{1}{6} & -\frac{1}{2} \\ \frac{1}{18} & \frac{1}{6} \end{bmatrix}}$

**j) ${A^{-1}}$**

${A}$ is *NOT* a square matrix, so it cannot be invertible.

Not defined.

**k) ${AA^T}$** 

 ${\begin{align}AA^T &= \begin{bmatrix} 1 & −1  \\ 0 & 3 \\ 2 & 0 \end{bmatrix} \begin{bmatrix} 1 & 0 & 2 \\ -1 & 3 & 0 \end{bmatrix} = \begin{bmatrix} \;1 \times 1 + (-1) \times (-1) & 1 \times 0 + (-1) \times 3 & 1 \times 2 + (-1) \times 0\; \\ 0 \times 1 + 3 \times -1 & 0 \times 0 + 3 \times 3 & 0 \times 2 + 3 \times 0 \\ 2 \times 1 + 0 \times -1 & 2 \times 0 + 0 \times 3 & 2 \times 2 + 0 \times 0 \end{bmatrix} \\  \\ &= \begin{bmatrix} 2 & −3 & 2  \\ -3 & 9 & 0 \\ 2 & 0 & 4 \end{bmatrix}\end{align}}$
 
 

**l) ${A^TA}$**

 ${\begin{align}A^TA &=  \begin{bmatrix} 1 & 0 & 2 \\ -1 & 3 & 0 \end{bmatrix} \begin{bmatrix} 1 & −1  \\ 0 & 3 \\ 2 & 0 \end{bmatrix} =  \begin{bmatrix} \;1 \times 1 + 0 \times 0 + 2 \times 2 & 1 \times -1 + 0 \times 3 + 2 \times 0\; \\ (-1) \times 1 + 3 \times 0 + 0 \times 2 & (-1) \times (-1) + 3 \times 3 + 0 \times 0 \end{bmatrix} \\ \\ &= \begin{bmatrix} 2 & −3 & 2  \\ -3 & 9 & 0 \\ 2 & 0 & 4 \end{bmatrix}\end{align}}$
 
**m) ${vu}$**

${v^T = \begin{bmatrix} \,2\, \\ 1 \\ 0 \end{bmatrix} \implies v = \begin{bmatrix} \,2 & 1 & 0\, \end{bmatrix}}$ ,   ${u = \begin{bmatrix} 3 \\ 3 \\ 1 \end{bmatrix}}$ 

${\begin{align} vu &= \begin{bmatrix} \,2 & 1 & 0\, \end{bmatrix}\begin{bmatrix} 3 \\ 3 \\ 1 \end{bmatrix} = \begin{bmatrix} 2 \times 3 \\ 1 \times 3 \\ 0 \times 1 \end{bmatrix} \\ \\ &= \begin{bmatrix} \,6\, \\ 3 \\ 0 \end{bmatrix}\end{align}}$

**n) ${\text{rank}(A)}$**

${A}$ =  ${\begin{bmatrix} 1 & −1  \\ 0 & 3 \\ 2 & 0 \end{bmatrix}}$

Reduce to EF 

An EF of ${A}$ = ${\begin{bmatrix} \fbox{1} & −1  \\ 0 & \fbox{3} \\ 0 & 0 \end{bmatrix}}$

Two pivot columns, so ${\fbox{rank(A) = 2}}$

___

3. Given the size of the matrices ${A}$, ${B}$, ${C}$, and ${D}$, determine whether the following  
operations are defined, and if defined, determine the size of the resulting matrix.  
$${A\;\;3\times2\;\;\;\;\;B\;\;2\times2\;\;\;\;\;C\;\;2\times3\;\;\;\;\;D\;\;3\times3}$$
**(a) ${5A}$**

Defined. ${3 \times 2}$

**(b) ${B − C}$**

Defined. The two matrices involved are the same size. ${2 \times 2}$ 

**(c) ${(A − C^T )^T}$** 

Undefined. ${A}$ is ${3 \times 2}$ and ${C^T}$ is ${2 \times 2}$. Matrix subtraction requires both matrices to be the same size.

**(d) ${C^T A^T + 2D^T }$**

Defined. ${C^T}$ is ${3 \times 2}$ and ${A^T}$ is ${2 \times 3}$. These two can be multiplied since their inner products are the same, and yield a ${3 \times 3}$ matrix (outer dimensions). ${D^T}$ is a ${3 \times 3}$, and scalar multiplication does not change this, so ${2D^T}$ is also ${3 \times 3}$. Matrix of the same dimensions can be added. The result is a ${3 \times 3}$.

4. Find the determinant of the following matrices. Show all work. Which of these matrices  
are invertible?  
$${A =  \begin{bmatrix} 1 & −1 & 4  \\ 0 & 1 & 0 \\ 5 & 2 & 3 \end{bmatrix}},\;\;\;\; \large{B =  \begin{bmatrix} 3 & 5 & −6 & 4 \\ 0 & −2 & 3 & −3 \\ 0 & 0 & 1 & 5 \\ 0 & 0 & 0 & 3 \end{bmatrix}}$$

Cofactor expansion along *second row*

${\begin{align}\det(A) &= \det\left( \begin{bmatrix} 1 & −1 & 4  \\ 0 & 1 & 0 \\ 5 & 2 & 3 \end{bmatrix}\right) = 1^{(2 +2)} \times \det\left(\begin{bmatrix} 1 & 4 \\ 5 & 3 \end{bmatrix}\right) = 1 \times (1 \times 3 - 4 \times 5) \\ \\ &= 3 - 20 = -17 \neq 0\end{align}}$ 

Since ${\det(A) \neq 0}$, ${A}$ is invertible

Since the matrix ${B}$ is a triangular matrix, the determinant is the product of the main diagonals

$\iff \large{\det(B) = 3 \times (-2) \times 1 \times 3 = -18}$

5. Determine whether the set of vectors are linearly independent. Give reasons for your  
answer.  
**(a)**  

${ \left\{ \begin{bmatrix} 16 \\ -8 \\ 12 \end{bmatrix}, \begin{bmatrix} -4 \\ 2 \\ -4 \end{bmatrix}\right\}}$ 

${\begin{bmatrix} 16 \\ -8 \\ 12 \end{bmatrix} \neq c \times \begin{bmatrix} -4 \\ 2 \\ -4 \end{bmatrix}}$    ${c \in \mathbb{R}^n}$

Linearly independent, since one vector is a scalar multiple of the other

**(b)**  

${\left\{\begin{bmatrix} 2  \\ −5  \\ 1\end{bmatrix}, \begin{bmatrix} -6  \\ 5  \\ 3 \end{bmatrix}, \begin{bmatrix} 0  \\ 0  \\ 0 \end{bmatrix}\right\}}$

Not linearly independent, since one vector is the zero vector
 
**(c)**  

${\left\{ \begin{bmatrix} 5  \\ 5  \\ 1\end{bmatrix},\begin{bmatrix} -1  \\ 0  \\ 1\end{bmatrix}, \begin{bmatrix} 3  \\ 6  \\ 1\end{bmatrix}, \begin{bmatrix} 2  \\ 0  \\ 0 \end{bmatrix}\right\}}$

Not linearly independent, since there are more vectors than entries per vector

**(d)**  

${\left\{\begin{bmatrix} 1  \\ 1  \\ 3 \end{bmatrix}, \begin{bmatrix} -3  \\ 0  \\ 4\end{bmatrix}, \begin{bmatrix} 5  \\ -1  \\ 2\end{bmatrix}\right\}}$

Linearly independent, since the echelon form of the matrix of the column vectors has a pivot in each column


${\begin{bmatrix} 1 & -3 & 5 \\ 1 & 0 & -1 \\  3 & 4 & 2 \end{bmatrix} \xrightarrow {\huge{R_3 \rightarrow R_3 - 3 \times R_1}}\begin{bmatrix} 1 & 0 & -1 \\ 0 & 1 & 1 \\ 0 & 4 & 5 \end{bmatrix} \xrightarrow {\huge{R_3 \rightarrow R_3 + (-4) \times R_2}}\begin{bmatrix} \fbox{1} & 0 & -1 \\ 0 & \fbox{1} & 1 \\ 0 & 0 & \fbox{1} \end{bmatrix}}$


___

6. Given Ax = b is represented by the augmented matrix  


${\begin{bmatrix} -1 & 1 & -3 & -6 & -4 \\-3 & 3 & -8 & -16 & -10 \\2 & -2 & 7 & 14 & 10 \end{bmatrix}}$ ~ ${\begin{bmatrix} 1 & -1 & 3 & 6 & 4 \\ 0 & 0 & 1 & 2 & 2 \\ 0 & 0 & 0 & 0 & 0 \end{bmatrix}}$

**(a)** How many solutions does the system of equations have?  
Infinite solutions.

**(b)** Are the columns of A independent? Explain.  
No. There are more columns than entries per vector, so the column vectors of A cannot be linearly independent.

**(c)** Do the columns of A span ${\mathbb{R^3}}$?  
No. ${A}$ only has ${2}$ pivot rows in the first and second row, so it can only span ${\mathbb{R^2}}$, not ${\mathbb{R}^3}$

**(d)** Is Ax = b consistent for every b? Explain.  
No. If ${b}$ is a vector that after row reduction in the augmented matrix has a non-zero entry as its third entry, then the last column of the augmented matrix for ${Ax = b}$ would become a pivot column. This means ${Ax = b}$ would be inconsistent.

**(e)** If ${T}$: ${\mathbb{R^n} \rightarrow \mathbb{R}^m}$ is a linear transformation given by ${T(x) = Ax}$, what is ${n}$?  What is ${m}$?  
$\large n$ is the number of columns in the matrix ${A}$, or ${\fbox{4}}$ (The augmented matrix ${[\;A\;|\;b\;]}$ has ${5}$ columns, so ${A}$ as ${5 - 1 = 4}$).
${m}$ is the number of rows in the matrix ${A}$, or ${\fbox{3}}$

**(f)** Find a basis for the column space of ${A}$.  

The pivot positions of ${A}$ are:
${\begin{bmatrix} \fbox{-1} & 1 & -3 & -6 \\-3 & 3 & \fbox{-8} & -16 \\2 & -2 & 7 & 14\end{bmatrix}}$ 

So a basis for the column space of ${A}$ is 

${\left\{ \begin{bmatrix} -1 \\ -3 \\ 2 \end{bmatrix} \begin{bmatrix} -3 \\ -8 \\ 7\end{bmatrix}\right\}}$

**(g)** What is the rank of A?  
The rank of ${A}$ is ${\fbox{2}}$ since there are two elements in the basis of the column space of ${A}$.

**(h)** What if the nullity of A?  
By the Rank Theorem,
rank(${A}$) + nullity(${A}$) = # of columns

So 2 + nullity(${A}$) = 4

Thus, the nullity of ${A}$ is ${4 - 2 = \fbox{2}}$

___

7. Determine ${A^{-1}}$ if ${A = \begin{bmatrix} 1 & 1 & 2 \\ 2 & 3 & -2 \\ 3 & 3 & 7 \end{bmatrix}}$.

By Gaussian-Jordan Method,

${\begin{align}&\begin{bmatrix} 1 & 1 & 2 & | & 1 & 0 & 0\\ 2 & 3 & -2 & | & 0 & 1 & 0 \\ 3 & 3 & 7 & | & 0 & 0 & 1\end{bmatrix} \xrightarrow[\huge{R_3 \rightarrow R_3 + (-3) \times R_1}]{\huge{R_2 \rightarrow R_2 + (-2) \times R_1}} \begin{bmatrix} 1 & 1 & 2 & | & 1 & 0 & 0\\ 0 & 1 & -6 & | & -2 & 1 & 0 \\ 0 & 0 & 1 & | & -3 & 0 & 1\end{bmatrix} \\ \\ & \xrightarrow[\huge{R_2 \rightarrow R_2 + (6) \times R_3}]{\huge{R_1 \rightarrow R_1 + (-2) \times R_3}} \begin{bmatrix} 1 & 1 & 0 & | & 7 & 0 & -2\\ 0 & 1 & 0 & | & -20 & 1 & 6 \\ 0 & 0 & 1 & | & -3 & 0 & 1\end{bmatrix} \xrightarrow{\huge{R_1 \rightarrow R_1 + (-1) \times R_2}} \\ \\ &\begin{bmatrix} 1 & 0 & 0 & | & 27 & -1 & -8\\ 0 & 1 & 0 & | & -20 & 1 & 6 \\ -3 & 0 & 1 & | & -3 & 0 & 1\end{bmatrix}\end{align}}$

Therefore, ${A^{-1}} = \begin{bmatrix} 27 & -1 & -8 \\ -20 & 1 & 6 \\ -3 & 0 & 1 \end{bmatrix}$

10. Matrix ${A}$ is given below. Your classmate claims ${A^{−1}}$ is the matrix ${B}$. Is the classmate  
right or wrong? How do you know?  

${A = \begin{bmatrix} 1 & -1 & -2 \\ 2 & -3 & -5 \\ -1 & 3 & 5 \end{bmatrix}}$,    ${B = \begin{bmatrix} 0 & 1 & 1 \\ 5 & -3 & -1 \\ -3 & 1 & 0 \end{bmatrix}}$

If ${A^{-1} = B}$, then ${AA^{-1} = AB = I}$

However, we can see that $${\begin{align}AB &= \begin{bmatrix} 1 & -1 & -2 \\ 2 & -3 & -5 \\ -1 & 3 & 5 \end{bmatrix} \begin{bmatrix} 0 & 1 & 1 \\ 5 & -3 & -1 \\ -3 & 1 & 0 \end{bmatrix} \\ \\  &= \begin{bmatrix} 1 \times 0+(-1)\times5+(-2) \times (-3) & 1 \times 1 + (-1) \times (-3) + (-2) \times 1 & 1 \times 1 + (-1) \times (-1) + (-2) \times 0 \\ 2 \times 0 + (-3) \times 5 + (-5) \times (-3) & 2 \times 1 + (-3) \times (-3) + (-5) \times (1) & 2 \times 1 + (-3) \times (-1) + (-5) \times 0 \\ -1 \times 0 + 3 \times 5 + 5 \times (-3) & -1 \times 0 + 3 \times 5 + 5 \times (-3) & (-1) \times 1 + 3 \times (-1) + 5 \times 0 \end{bmatrix} \\ \\ & = \begin{bmatrix} 1 & 2 & 2 \\ 0 & -6 & 5 \\ 0 & 0 & -4 \end{bmatrix} \neq \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}\end{align}}$$
Therefore, ${B}$ cannot be the inverse of ${A}$

___

9. Given that ${A}$, ${B}$, and ${C}$ are all invertible ${n \times n}$ matrices, find the inverse of ${ABC}$ and  
show that what you think is the inverse, really is the inverse.  

$${(ABC)^{-1} = ((AB)C)^{-1} = C^{-1}(AB)^{-1} = C^{-1}B^{-1}A^{-1}}$$
If ${C^{-1} B^{-1} A^{-1}}$ is the inverse of ${ABC}$, then ${ABC \times C^{-1} B^{-1} A^{-1} = I}$

$${\begin{align}&ABC \times C^{-1} B^{-1} A^{-1} = AB(CC^{-1})B^{-1}A^{-1} = AB (I)B^{-1} A^{-1} = ABB^{-1}A^{-1} \\ &= A(BB^{-1})A^{-1} = A(I)A^{-1} = AA^{-1} = I\end{align}}$$

Therefore, ${C^{-1} B^{-1} A^{-1}}$ is the inverse of ${ABC}$

___

10. True or False: For all n×n matrices A, B, and C (no explanation required):  
**(a)** ${A + B = B + A }$
True

**(b)** ${(A + B)^T = A^T + B^T}$
False

**(c)** ${(AB)^T = A^T B^T}$
False

**(d)** ${(A^T)^T = A}$
True

**(e)** ${\det(A + B) = \det(A) + \det(B) }$
False

**(f)** ${\det(AB) = \det(A) \det(B)}$
True

**(g)** If A is invertible, then ${\det(AA^{−1}) = 1}$
True

**(h)** If AB = AC then B = C.  
False

**(i)** If B = C then AB = AC.  
True

___

11. True or False: (no explanation required):  
**(a)** Every linear transformation rotates a vector.  
False

**(b)** Not every linear transformation from ${\mathbb{R}^{n}}$ to ${\mathbb{R}^{m}}$ is a matrix transformation.  
False

**(c)** If an ${n\times n}$ matrix ${A}$ can be row reduced to the identity matrix, then ${A}$ must be  
invertible.  
True

**(d)** If the columns of an ${n\times n}$ matrix A are linearly dependent, then A is invertible.  
False

**(e)** If ${A}$ and ${B}$ are both ${n\times n}$ invertible matrices then ${(AB)^{−1} = A^{−1}B^{−1}}$.  
False

**(f)** If A is ${n \times n}$ and ${Ax = 0}$ has only the trivial solution, then the dimension of the  
Nul(A) is 1.  
False

**(g)** If A is a ${3 \times 4}$ matrix, then the column vectors belong to ${\mathbb{R}^3}$.  
True

**(h)** If A is a ${3 \times 4}$ matrix that has ${3}$ pivot columns, then the linear transformation  
${T}$: ${x \rightarrow Ax}$ is onto.  
True

**(i)** All sets of vectors in ${\mathbb{R}^2}$ have a basis. 
False

**(j)** If ${S}$ is a set of 2 vectors, each of which is in ${\mathbb{R}^3}$, then ${S}$ is linearly independent.  
False

**(k)** If ${S}$ is a set of 4 vectors, each of which is in ${\mathbb{R}^3}$, then ${S}$ is linearly dependent.  
True

**(l)** If ${S}$ is a set of 4 vectors, each of which is in ${\mathbb{R}^3}$, then  ${S}$ spans ${\mathbb{R}^3}$.  
False

**(m)** If ${S}$ is a set of 2 vectors, each of which is in ${\mathbb{R}^3}$, then ${S}$ does not span ${\mathbb{R}^3}$.
True

#### Tags

>[!quote] Tags:
> [[Linear Algebra Information|Linear Algebra Information]]

