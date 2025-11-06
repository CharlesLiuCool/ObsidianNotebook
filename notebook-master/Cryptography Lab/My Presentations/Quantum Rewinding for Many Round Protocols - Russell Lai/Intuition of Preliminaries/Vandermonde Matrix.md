>**Definition** Vandermonde Matrix
>Given an *ordered set of elements*
>$$T = (r_0, r_1,...,r_{t-1})$$
>from some field (or ring), the *Vandermonde matrix* associated to $T$ is
>$$V_T = \begin{pmatrix} 1 & 1 & ... & 1 \\ r_0 & r_1 & ... &r_{t-1} \\ r_0^2 & r_1^2 & ... & r_{t-1}^2 \\ \vdots & \vdots & & \vdots \\ r_0^{t-1} & r_1^{t-1} & ... & r_{t-1}^{t-1} \end{pmatrix}$$
>where each column corresponds to one element $r_j$, and each row gives an increasing power of those elements.

*Intuition:*
$V_T$ is a compact way of representing the evaluation of monomials $1, x,x^2,...,x^{t-1}$ at the elements $r_0, r_1,...,r_{t-1}$

If we want to evaluate $f(x)$ at all points $r_0,...,r_{t-1}$, we can as a matrix-vector product:
$$\begin{pmatrix} f(r_0) \\ f(r_1) \\ \vdots \\ f(r_{t-1}) \end{pmatrix} = \begin{pmatrix} 1 & 1 & ... & 1 \\ r_0 & r_1 & ... &r_{t-1} \\ r_0^2 & r_1^2 & ... & r_{t-1}^2 \\ \vdots & \vdots & & \vdots \\ r_0^{t-1} & r_1^{t-1} & ... & r_{t-1}^{t-1} \end{pmatrix} \textbf{a}$$
or
$$y = V_T\textbf{a}$$
where $a$ is the coefficient vector of the polynomial $f$.

### **Polynomial Interpolation**

Notice that when the columns rely on distinct elements $r_i$ where no $i$ is the same, the matrix $V_T$ is invertible, so we can say
$$a = (V_T^T)^{-1} y$$
which allows us to reconstruct $f(x)$ from its values at certain points (*polynomial interpolation*).

>*Takeaway:* Using the matrix properties of the Vandermonde, particularly invertibility, we can do polynomial interpolation!

### **Discrete Fourier Transform (DFT)**

Suppose we choose the evaluation points to be the *roots of unity*:
$$r_i = \zeta_n^i \text{ where } \zeta_n = e^{2\pi i/n}$$

Then the Vandermonde matrix becomes
$$V = \begin{pmatrix} 1 & 1 & 1 & ... & 1 \\ 1 & \zeta_n & \zeta_n^2 & ... & \zeta_n^{n-1} \\ 1 & \zeta_n^2 & \zeta_n^4 & ... & \zeta_n^{2(n-1)} \\ \vdots & \vdots & \vdots& \ddots & \vdots \\ 1 & \zeta_n^{n-1} & \zeta_n^{2(n-1)} & ... & \zeta_n^{(n-1)^2} \end{pmatrix}$$

This is exactly the *Discrete Fourier Transform*!

>*Takeaway*: The DFT is really just a special Vandermonde matrix where the $r_i$ are complex roots of unity.