### Second Order Linear Homogeneous Constant Coefficient ODEs

${ay'' + by' + cy = 0}$
${a,b,c \in \mathbb{R}}$

To solve:
1. ${y = e^{rt}}$
2. Plug into ODE
3. Solve for ${r}$
4. Plug into final answer

(i) If ${r_1, r_2}$ are distinct and real
${y = c_1 e^{r_1t} + c_2 e^{r_2t}}$

(ii) ${r_1 = r_2}$
${y = c_1e^{r_1t} + tc_2e^{r_2t}}$

(iii) ${r = a \pm bi}$
${y = e^{at} (c_1 \cos(bt) + c_2\sin(bt))}$

${e^{i\theta} = \cos(\theta) + i\sin(\theta)}$

${ r = a \pm bi}$
${y = e^{(a+bi)t} = e^{at} e ^ {\pm bit} = e^{at}(\cos(bt) + i\sin(bt))}$

___

>[!question] Example 1
>${y'' + 5y' + 6y = 0}$
>${y = e^{rt}}$
>${y' = re^{rt}}$
>${r^2e^{rt}}$

>[!check]- Solution
>${r^2 + 5r + 6 = 0}$
>${(r+3)(r+2) = 0}$
>${r = -3, -2}$
>${y = c_1e^{-2t} + c_2e^{-3t}}$

>[!question] Example 2
>${y'' + 6y' + 9y = 0, y(0) = 4, y'(0) = 6}$
>${y = e^{rt}, y' = re^{rt}, y'' = r^2e^{rt}}$
>${r^2e^{rt} + 6re^{rt} + 9e^{rt} = 0}$
>${(r+3)^2 = 0}$
>${r = -3,-3}$
>${y = (c_1 + c_2t)e^{-3t}}$
>${y(0) = 4 \implies c_1 = 4}$
>${y' = c_2 e^{-3t} - 3(4+c_2t)e^{-3t}}$
>${y'(0) = c_2 -3 (4) = 6 \implies c_2 = 18}$
>
>${y = (4 + 18t)e^{-3t}}$

>[!question] Example 3
>${y'' + 2y' + 2y = 0,\;y(0) = 1,\;y(\frac{\pi}{2}) = 2}$

>[!check]- Solution
>${r^2 + 2r + 2}$
>${r = -1 \pm i}$
>${a = -1, b = 1}$
>${y = e^{-t}(c_1\cos(t) + c_2\sin(t))}$
>${y(0) = 1(c_1 \cdot 1 + 0) = c_1 = 1}$
>${y(\frac{\pi}{2}) = e^{-\frac{\pi}{2}}(c_2) = 2 \implies c_2 = 2 e^{\frac{\pi}{2}}}$
>${y = e^{-t} (\cos(t) + 2e^{\frac{\pi}{2}\sin(t)})}$

>[!question] Example 4
>${y'' + 9y' + 14y = 0,\;y(0) = 4,\;y'(0) = 23}$

>[!check]- Solution
>${r^2 + 9r + 14 = 0}$
>${(r+2)(r+7) = 0}$
>${r = -2, -7}$
>${y = c_1 e^{-2t} + c_2e^{-7t}}$
>${y(0) = c_1 + c_2 = 4}$
>${y'(0) = -2c_1 - 7c_2 = -23}$
>${c_2 = 3, c_1 = 1}$
>${y = e^{-2t} + 3e^{-7t}}$

>[!question] Example 5
>${y'' + 2ay' + 3a^2y = 0,\;y(0) = A,\;y'(0) = B,\;a > 0}$

>[!check]- Solution
>${r^2 + 2ar + 3a^2 = 0}$
>
>${r = \dfrac{-2a \pm \sqrt{-8a^2}}{2} = {\dfrac{-2a\pm2\sqrt{2}ai}{2}}}$
> 
> ${r = -a \pm \sqrt{2} ai}$
> ${y = e^{-at} (c_1 \cos(\sqrt{2}a) + c_2\sin(\sqrt{2}a))}$
> ${y(0) = 1 (c_1 \cdot 1 + a) = c_1 = A}$
> ${y' = -ae^{-at}(c_1\cos(\sqrt{a}) +}$
> ${ c_2\sin(\sqrt{2}a)) + e^{-at}(-c_1\sqrt{2}a \sin(\sqrt{2}at) + c_2\sqrt{2}a \cos(\sqrt{2}at))}$
> ${= -ac_1 + c_2 \sqrt{2}a}$
> ${y'(0) = -ac_1 + c_2\sqrt{2}a = -aA + c_2\sqrt{2}a = B \implies \sqrt{2}ac_2 = B + aA}$
> ${y = e^{-at} (A\cos(\sqrt{2}at) + \frac{B+aA}{\sqrt{2}a}\sin(\sqrt{2}at))}$

___

### Operator

An operator takes a real function and outputs a real function

>[!question] Example 1
>${\dfrac{d}{dx}}$
>
>${\dfrac{d}{dx}(3x) = 3}$

>[!question] Example 2
>${3(f(x))}$
>${3(x^2+2x+1 = 3x^2 + 6x + 3)}$

An operator, ${L}$, is linear, if for all functions ${f,g}$ and constants ${a}$,
the following hold:

1. ${L(af) = a L(f)}$
2. ${L(f + g) = L(f) + L(g)}$

**Recall:** A differential equation is linear if it can be written in the following form: 

${f_n(x) y^{(n)} + f_{n-1}(x)y^{n-1} + ... + f_0(x)y = g(x)}$

${\sum_{i=0}^n f_i(x)y^{(i)} = g(x)}$

${L(y) = g(x)}$

${L}$ is linear

Suppose ${L(y) = 0}$ for a linear operator ${L}$. Suppose ${y_1, y_2, ... y_n}$ all satisfy ${L(y_1) = 0}$

Then: ${L(c_iy_i) = c_iL(y_i) = c_i \cdot 0 = 0}$

${L(\sum_{i=1}^{n}y_i) = \sum_{i=1}^n L(y_i) = \sum_{i=1}^n 0 = 0}$

${\implies L(\sum_{i=1}^nc_iy_i)}$

**Superposition:**
Suppose ${\{y_1, y_2, ... y_n\}}$ are all solutions, so is ${c_1y_1 + c_2y_2 + ... + c_ny_n}$. In other words, any linear combination of solutions are also solutions.

>[!question] Example
>${y''' + 3y'' + 3y' + y = 0}$

>[!check]- Solution
>${y = e^{rt}}$
>${r^3 +3r^2 + 3r + 1 = 0}$
>${(r+1)^3 = 0}$
>${y_1 = e^{-t}, y_2 = te^{-t}, y_3 = t^2 e^{-t}}$
>${y(t) = c_1e^{-t} + c_2te^{-t} + c_3t^2e^{-t}}$

>[!question] Example
>Suppose the differential equation
> ${Ly = 0}$
> has the characteristic equation
> ${ 0 = (r^2 + 1)^2)(r-1)^3(r-2)}$

>[!check]- Solution
> ${\implies r = \pm i,i}$
> ${r = 1, 1, 1, 2}$
> ${y(t) = (c_1\sin(t) + c_2\cos(t)) + t (c_3\sin(t) + c_4\cos(t))+ c_5e^t + c_6te^t + c_7t^2e^t }$
> ${+ c_8e^{2t}}$

___

### Existence and Uniqueness

Suppose you have ${\sum_{i=0}^{n}f_i(x)y^{(i)} = g(x),\; y^{(i)}(x_0) = c_0}$ (for ${0 \leq i \leq n - 1}$) and ${f_i(x)}$ and ${g(x)}$ are all continuous on some interval ${I}$ containing ${x_0}$, Then a unique solution to the differential equation exists.

___

### Linearly Independence of Solutions

For 2nd order,
Check the Wronskian
${W = \begin{vmatrix} y_1 & y_2 \\ y_1' & y_2' \end{vmatrix} \neq 0}$

Higher order:
Suppose our linear ODE is of order ${n}$ and has solutions ${y_1, y_2... y_n}$

Then we check:

${W = \begin{vmatrix} y_1 & y_2 & ... & y_n \\ y_1' & y_2' & ... & y_n' \\ y_1^{(n-1)} & y_2^{(n-1)} & ... & y_n^{(n-1)} \end{vmatrix}}$

If ${W = 0}$, the solution set is *not* linearly independent. If ${W \neq 0}$, the solution set is linearly independent.

>[!question] Example 1
>${y_1 = e^{2t},\;y_2=e^{3t},\;y_3 = 1}$

>[!check]- Solution
>${W = \begin{vmatrix} e^{2t} & e^{3t} & 1 \\ 2e^{2t} & 3e^{3t} & 0 \\ 4e^{2t} & 9e^{3t} & 0\end{vmatrix} = 6e^{5t}}$
>
>The Wronskian is ${18e^{5t} - 12e^{5t} = 6e^{5t} \neq 0}$
>Solution set is linearly independent.

>[!question] Example 2
>${y_1 = e^{t}, y_2 = e^{-t}, y_3 = e^{t} + e^{-t}}$

>[!check]- Solution
>${\begin{vmatrix} e^t & e^{-t} & e^t + e^{-t} \\ e^t & -e^{-t} & e^{t} - e^{-t} \\ e^{t} & e^{-t} & e^{t}+e^{-t} \end{vmatrix} = 0}$
>Linearly dependent

### Linear Constant Coefficient Homogeneous ODEs

1. "Guess" ${y = e^{rt}}$
2. Plug ${y}$ into the ODE
3. Solve for ${r}$
4. Plug back into ${y}$.

If ${r}$ has multiplicity multiply by ${t}$ (for each multiplicity)
Otherwise, use the same rules for ${r}$ we saw with second order homogeneous constant coefficient linear ODEs.

>[!question] Example 1
>${y''' + 6y'' + 12y' + 8y = 0}$

>[!check]- Solution
>${r^3 + 6r^2 + 12r + 8 = 0}$
>${(r+2)^3}$
> 
> ${y = c_1e^{-2t} + c_2te^{-2t} + c_3t^2e^{-2t}}$

>[!question] Example 2
>${y^{(5)} + y^{(4)} + y^{(3)} + y^{(2)} = 0}$

>[!check]- Solution
>${y = e^{rt}, y^{(k)} = r^ke^{rt}}$
>${r^5 + r^4 + r^3 + r^2 = 0}$
>${(r^2 + 1)(r+1)r^2 = 0}$
>${r = 0\,m\,2,\;-1, \;\pm i}$
> 
> ${y = c_1 + c_2t + c_3e^{-t} + c_4\cos(t) + c_5\sin(t)}$

