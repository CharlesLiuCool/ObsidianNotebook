
### Euler's Method

${y' = f(x,y),\; y(x_0) = y_0}$

Intuition:
![[Week 4 2024-09-09 10.13.39.excalidraw]]
${L(x) = \Delta x f'(x) + y_0}$

**The method:**

0. Check existence and uniqueness of the solution
1. Pick a step size h
2. Update your x-value
e.g. ${x_{i+1} = x_i + h}$
3. Update y-value
e.g. ${y_{i+1} = y_i + h \cdot f(x,y)}$
4. Repeat until satisfied with result

>[!question] Example 1
>${\dfrac{dy}{dx} = xy = f(x,y), \;}$ ${y(1) = 2}$
>
>Approximate ${y(1.3)}$ with a step size of ${h = 0.1}$

>[!check]- Solution
>| ${i}$ | ${x_i}$ | ${y_i}$ |
>| --- | --- | --- |
>| 0 | 1 | 2 |
>| 1 | 1.1 | 2.2 |
>| 2 | 1.2 | 2.442 |
>| 3 | 1.3 | 2.73504 | 
> 
> Let's solve ${y}$ using separation of variables and compare the result
> 
> ${\int \frac{dy}{y} = \int x dx}$
> 
> ${\ln|y| = \frac{x^2}{2} + c}$
> 
> ${y = e^{\frac{x^2}{2} + c} = ce^{\frac{x^2}{2}}}$
> 
> ${y = 2e^{\frac{x^2 - 1}{2}}}$
>  
>  ${y(1.3) = 2e^{\frac{1.3^2 - 1}{2}} = 2.82}$

### Picard's Theorem

For ${y' = f(x,y)}$, ${y(x_0) = y_0}$. If ${f(x,y)}$ is continuous at ${(x_0, y_0)}$ and ${\frac{\partial f}{\partial y}}$ exists and is continuous near ${(x_0, y_0)}$, then a solution exists and is unique near ${(x_0, y_0)}$.

>[!question] Example 2
>${y' = x^3 - y^2,\; y(0) = 0,\; h = 0.1}$
>
>Approximate ${y(0.3)}$

>[!check]- Solution
>${f(x,y) = x^3 - y^2}$ is continuous at ${(0,0)}$
>
>${\frac{\partial f(x,y)}{\partial y} = -2y}$ is continuous near ${(0,0)}$
> 
> A solution exists and is unique.
> 
> | ${i}$ | ${x_i}$ | ${y_i}$ |
> | --- | --- | --- |
> | 0 | 0 | 0 | 
> | 1 | 0.1 | 0 |
> | 2 | 0.2 | 0.0001 |
> | 3 | 0.3 | 0.0017999 |

### Exact Equations

${F(x,y) = c}$

${dF(x,y) = \dfrac{\partial F}{\partial x} dx + \dfrac{\partial F}{\partial y}dy = F_x dx + F_y dy = 0}$

${0 = F_x + F_y \dfrac{dy}{dx}}$

${M + N \dfrac{dy}{dx} = 0}$

${F_{xy} = F_{yx}}$

Such that 
${M_y = N_x}$

**Step 1:**
Show ${M_y = N_x}$

**Step 2:**
Take ${\int M dx}$ and ${\int Ndy}$

**Step 3:**
Match terms from both integrals

>[!question] Example 1
>${\underbrace{y^2 + \dfrac{1}{x}}_M + \underbrace{(2xy) \dfrac{dy}{dx}}_N = 0}$

>[!check]- Solution
>${M_y = 2y}$
>${N_x = 2y}$
>${M_y = N_x = 2y}$ Exact!
> 
> ${\int y^2 + \dfrac{1}{x}dx = y^2x + \ln|x|}$
> 
> ${\int N dy = \int 2xy\,dy = xy^2 + B(x)}$
> 
> ${F(x,y) = xy^2 +\ln|x| = c}$

>[!question] Example 2
>${2y\sec^2(x) + (2\tan(x) + 6e^{2y})\dfrac{dy}{dx} = 0}$

>[!check]- Solution
>${M_y = 2\sec^2{x}}$
>${N_y = 2\sec^2{x}}$
>
>Exact!
>
>${\int Mdx = \int 2y\sec^2(x)dx = 2y\int \sec^2(x)dx = 2y\tan(x) + Ay}$
>
>${\int N dy = \int 2 \tan(x) + 6e^{2y} dy = 2y\tan(x) + 3e^{2y} + B(y)}$
> 
> ${F(x,y) = 2y\tan(x) + 3e^{2y} = c}$

### *Almost* Exact Equations

${M + N\dfrac{dy}{dx} = 0}$
but
${M_y \neq N_x}$

${uM + uN \dfrac{dy}{dx} = 0}$

${\dfrac{\partial (uM)}{\partial y} = \dfrac{\partial (uN)}{\partial x}}$

${u_yM + uM_y = u_xN + uN_x}$

Suppose ${u(x)}$ is only a function of ${x}$.

Then ${u_y = 0}$

${uM_y = u'N + uN_x}$

${u'N = u(M_y - N_x)}$

${\dfrac{u'}{u} = \dfrac{M_y - N_x}{N}}$

${\int \dfrac{du}{u} = \int \dfrac{M_y - N_x}{N}dx}$

${\ln|u| = \int \frac{M_y - N_x}{N}dx}$

${u = e^{\int \frac{M_y - N_x}{N}dx}}$

If ${\frac{M_y - N_x}{N}}$ is a function of ${x}$ then ${u = e^{\int \frac{M_y - N_x}{N}dx}}$

>[!question] Example 3
>${\cos(y) + 2e^x - \sin(y)\dfrac{dy}{dx} = 0}$

>[!check]- Solution
>${M = \cos(y) + 2e^x}$
>${N = -\sin(y)}$
>${M_y = -\sin(y) \neq N_x = 0}$
> 
>  ${\frac{M_y - N_x}{N} = \frac{-\sin(y) - 0}{-sin(y)} = 1}$
>  
>  ${u(x) = e^{x}}$
>  
>  ${(e^x\cos(y) + 2e^{2x}) + (e^x\sin(y))\dfrac{dy}{dx} = 0}$
> 
> ${M_y = -e^x\sin(y)}$
> ${N_x = -e^x\sin(y)}$
> ${\int M dx = \int e^x \cos(y) + 2e^{2x}dx = e^x \cos(y) + e^{2x} + A(y)}$
> ${\int N dy = \int -e^x \sin(y) dy = e^x \cos(y) + B(x)}$
> 
> ${F(x,y) = e^x \cos(y) + e^{2x} = c}$

If ${\dfrac{N_x - M_y}{M}}$ is a function of y, 

${u = e^{\int \frac{N_x - M_y}{M}dy}}$

### Second Order Linear ODEs

${A(x)y'' + B(x)y' + C(x)y = F(x)}$

${y'' + P(x)y' + Q(x)y = f(x)}$ (divide ${ A(x)}$ on both sides)

>[!question] Example 1
>${y'' + ky^2 = 0, k \in \mathbb{R}}$
>${y = c_1 \sin(kx) + c_2 \cos(kx)}$

>[!question] Example 2
>${y'' - k^2y = 0, k \in \mathbb{R}}$
>${y_1 = e^{kx}, y_2 e^{-kx}}$


### Superposition

Consider ${y'' + P(x)y' + Q(x)y = 0}$
If ${y_1, y_2}$ are solutions to the equation, then so is ${y = c_1y_1 + c_2y_2\;\;\forall\;c_1, c_2 \in \mathbb{R}}$

### Theorem

If ${y_1, y_2}$ are linearly independent solutions to ${y'' + p(x)y' + q(x)y = 0}$, then *all* solutions to that equation can be written in the form ${y = c_1y_1 + c_2y_2}$

>[!question] Example
>${y'' + ky^2 = 0}$
>${y_1 = \sin(kx), y_2 = \cos(kx)}$

>[!check]- Solution
>${y_1' = k\cos(kx), y_2' = -k\sin(kx)}$
>${k \neq 0}$
>
> ${\begin{vmatrix} \sin(kx) & \cos(kx) \\ k\cos(kx) & -k\sin(kx) \end{vmatrix} = -k}$

### Hyperbolic Trigonometric Functions

**Recall:** ${\cosh(x) = \dfrac{e^x + e^{-x}}{2},\sinh(x) = \dfrac{e^x - e^{-x}}{2}}$

${\implies \cosh(0) = 1,\;\sinh(0)}$

${\dfrac{d}{dx}(\cosh(x)) = \sinh(x), \dfrac{d}{dx}(\sinh(x)) = \cosh(x)}$

${\cosh^2(x) - \sinh^2(x)}$

___

Suppose ${y'' + p(x)y' + q(x)y = f(x)}$ with ${y(a) = b_0, y'(a) = b_1}$

If ${\exists}$ an open interval containing ${a}$ such that ${p(x), q(x), f(x)}$ are continuous on the entire open interval then ${\exists}$ an unique solution on the open term interval to

___

>[!question] Example
>${y'' + \dfrac{1}{x}y' - \dfrac{1}{x+1}y = \sin(x)}$
>${y(\frac{1}{2}), y'(\frac{1}{2}) = 2}$

>[!check]- Solution
>On ${(0, \infty)}$, we have ${p(x) = \frac{1}{x}, q(x) = \frac{1}{x+1}}$, and ${f(x) = \sin(x)}$ all continuous. ${\frac{1}{2}}$ is in this interval.
>${\exists}$ a unique solution on ${(0,\infty)}$

___

Suppose ${y'' + p(x)y' + q(x)y = 0}$ has a solution ${y_1}$ which is known. Then ${y_2(x) = y_1(x)u(x)}$ for some non-constant ${u(x)}$.

${y_2' = y_1'u + y_1u'}$
${y_2'' = y_1''u + y_1'u' + y_1'u' + y_1u'' = y_1''u + 2y_1'u' + y_1u''}$

${(y_1''u + 2y_1'u' + y_1u'') + p(x)(y_1'u + y_1u') +q(x)(y_1(x)u) = 0}$
${y_1u'' + 2y_1'u' + p(x)y_1u'}$

___

>[!question] Example
>Consider ${x^2y'' + xy' - y = 0}$


>[!check]- Solution
>${y = x^m}$
>${y' = mx^{m-1}}$
>${y'' = m(m-1)x{m-2}}$
>${x^2(m^2-m)x^{m-2} + xmx^{m-1} - x^m = 0}$
>${m^2 - 1 = 0}$
>${m = \pm 1}$
>${y_1 = x, y_2 = \frac{1}{x}}$
>
>${y_2 = xu}$
>${y_2' = u + xu'}$
>${y_2'' = u' + xu'' + u' = 2u' + xu''}$
>${x^2(2u'+xu'') + x(u+xu') - xu = 0}$
>${x^3u'' + 3x^2u' = 0}$
>${w = u'}$
>${w' = u''}$
>${x^3w' + 3x^2w = 0}$
>${w' = \frac{-3}{x}w = 0}$
>${\frac{w'}{w} = \frac{-3}{x}}$
>${\ln|w| = -3\ln|x| + C}$
>${w = cx^{-3} = u'}$
>${c_1 + \frac{cx^{-2}}{-2} = u}$
>${u = c_1 + cx^{-2}}$
>${y_2 = x(c_1 + cx^{-2}) = c_1x + cx^{-1}}$
>${y_2 = x^{-1}}$