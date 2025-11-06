
## Eigenvalues and Eigenvectors

### Example:

Let ${A = \begin{bmatrix} 6 & 5 & 2 \\ 0 & 4 & 0 \\ 2 & 4 & 6 \end{bmatrix}}$ 

**(1)** Find the characteristic polynomial of ${A}$. Write it in factored form.

**(2)** Determine eigenvalues and their algebraic multiplicity.

### Solution:

**(1)**

Note: $${A = \lambda I = \begin{bmatrix} 6 & 5 & 2 \\ 0 & 4 & 0 \\ 2 & 4 & 6 \end{bmatrix} - \begin{bmatrix} \lambda & 0 & 0 \\ 0 & \lambda & 0 \\ 0 & 0 & \lambda \end{bmatrix} = \begin{bmatrix} 6 - \lambda & 5 & 2 \\ 0 & 4 - \lambda & 0 \\ 2 & 4 & 6-\lambda \end{bmatrix}}$$

Characteristic polynomial

${\det(A - \lambda I) = \begin{bmatrix} 6 - \lambda & 5 & 2 \\ 0 & 4 - \lambda & 0 \\ 2 & 4 & 6-\lambda \end{bmatrix}\;\;\;\;\begin{bmatrix} + & - & + \\ - & + & - \\ + & - & +\end{bmatrix}}$

${\begin{align} &= (4-\lambda) \begin{bmatrix} 6 - \lambda & 2 \\ 2 & 6 - \lambda\end{bmatrix} = (4 - \lambda)[\,(6-\lambda)^2 - 2^2\,] = (4-\lambda)(6-\lambda-2)(6-\lambda+2) \\ \\ &= (4-\lambda)(4-\lambda)(8-\lambda) = (4-\lambda)^2(8-\lambda) \end{align}}$  
#### Tags

>[!quote] Tags:
> [[Linear Algebra Information|Linear Algebra Information]]

