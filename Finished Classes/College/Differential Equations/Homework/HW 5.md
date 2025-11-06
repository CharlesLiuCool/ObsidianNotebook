>[!question] 1.2.4
>Is it possible to solve the equation ${y' = \dfrac{xy}{\cos(x)}}$ for ${y(0) = 1}$? Justify.


Yes.

Plugging ${y(0) = 1}$ into the differential equations

${y' = 0}$, which is defined, so the solution exists.

Assuming ${f = y'}$

Finding ${\dfrac{\partial f}{\partial x} = \dfrac{x}{\cos(x)}}$
On a interval near ${x=0}$ such as ${-0.5<x<0.5}$, ${\dfrac{x}{\cos(x)}}$ is continuous, so the solution to the ODE is unique

>[!question] 1.8.2
>Solve the following exact equations, implicit general solutions will suffice:

**a)** ${(2xy + x^2)dx + (x^2 + y^2 + 1)dy = 0}$

${\int(M(x))dx = \int{2xy + x^2}dx= x^2y+\dfrac{x^3}{3} + A(y)}$

${\int(N(y))dy = \int{x^2 + y^2 + 1}dy = x^2y+ \dfrac{y^3}{3} + y + B(x)}$

${F(x,y) = x^2y + \dfrac{x^3}{3} + \dfrac{y^3}{3} + y = c}$


**b)** ${x^5+y^5\dfrac{dy}{dx} = 0}$

${\int(M(x))dx = \int{x^5}dx = \dfrac{x^6}{6} + A(y)}$
${\int(N(y))dy = \int{y^5}dy = \dfrac{y^6}{6} + B(x)}$

${F(x,y) = \dfrac{x^6}{6} + \dfrac{y^6}{6} = c}$

**c)** ${e^x + y^3 + 3xy^2\dfrac{dy}{dx} = 0}$

${\int(M(x))dx = \int (e^x + y^3)dx = e^x + y^3x + A(y)}$ 
${\int(N(y))dy = \int 3xy^2 dy = xy^3 + B(x)}$

${F(x,y) = xy^3 + e^x = c}$

**d)** ${(x+y)\cos(x) + \sin(x) + \sin(x)y' = 0}$

${\int(M(x))dx = \int((x+y)\cos(x) + \sin(x))dx }$
${= e\int x\cos(x) dx + \int y\cos(x) + \sin(x) dx}$

For ${\int x\cos(x) dx}$, use integration by parts
${x\sin(x) - \int(\sin(x))dx = x\sin(x) + \cos(x)}$

So,
${\int(M(x))dx = x\sin(x) + \cos(x) +y\sin(x) - \cos(x) + A(y) }$
${= (y+x)\sin(x) + A(y)}$

${\int(N(y))dy = \int(\sin(x))du = y\sin(x) + B(x)}$

${F(x,y) = (y+x)\sin(x)= c}$

>[!question] 2.1.5
>For the equation ${x^2y'' - xy' = 0}$, find two solutions, show that they are linearly independent and find the general solution. Hint: Try ${y = x^r}$.

${y' = rx^{r-1},\;y'' = r(r-1)x^{r-2}}$

${\implies x^2r(r-1)x^{r-1} - xrx^{r-1} = 0}$
${x^{r}(r-1)(r) - rx^r) = 0}$
${\implies r(r-1) - r = r^2 - 2r = r(r-2) 0}$
${r = 0, 2}$
${y = 1, x^2}$

Solve for Wronskian to prove linear independence
${\begin{vmatrix} 1 & x^2 \\ 0 & 2x \end{vmatrix} = 2x - 0 \neq 0}$
Since ${x>0}$, the Wronskian is not equal to so the two solutions ${y= 1, x^2}$ are linearly independent.

${y = c_1 + c_2x^2}$

>[!question] 2.1.9
>Take ${(1-x)^2y'' - xy' + y = 0}$

**a)** Show that ${y = x}$ is a solution
${y' = 1,\; y'' = 0}$
${\implies (1-x)\cdot 0 - x + x = 0 = 0}$
${y = x}$ satisfies the ODE, which means it is a solution

**b)** Use reduction of order to find a second linearly independent solution

${ y = xv, \; y' = xv'+v,\;y'' = xv''+v'+v' = xv''+2v'}$
${(1-x^2) \cdot (xv''+2v') - x(xv'+v) + xv = 0}$
${x(1-x^2)v'' + (2(1-x^2)-x^2)v' - xv + xv = 0}$
${x(1-x^2)v'' + (2-3x^2)v' = 0}$

${u = v'}$
${u' = v''}$
${x(1-x^2)u' + (2-3x^2)u = x(1-x^2)\dfrac{du}{dx} + (2-3x^2)u = 0}$

${\implies \int \dfrac {du}{u} = \int \dfrac{3x^2-2}{x(1-x^2)}dx = \int \dfrac{3x^2-2}{x(1-x)(1+x)}dx}$

${= \int \dfrac{3x^2}{x-x^3}dx + \int \dfrac{-2}{x(1-x)(1+x)}dx}$

For right hand side, cancel ${x}$ on top and bottom and use u-substitution on first term, then use partial fraction decomposition on second term.

${\int \dfrac{3x^2}{x-x^3}dx = \int \dfrac{3x}{1-x^2}dx}$
${s = 1-x^2}$
${ds = -2xdx}$

${\int \dfrac{3x}{1-x^2}dx = \dfrac{-3}{2}\int \dfrac{ds}{s} = \dfrac{-3}{2}\ln|s| = \dfrac{-3}{2}\ln|1-x^2|}$

Partial fraction decomposition

${\dfrac{-2}{x(1-x)(1+x)} = \dfrac{A}{x} + \dfrac{B}{1-x} + \dfrac{C}{1+x}}$

${-2 = A(1-x)(1+x) + Bx(1+x) + Cx(1-x)}$
Suppose ${x=1}$,
then
${-2 = 0 + 2B + 0}$
${\implies B = -1}$

Suppose ${x = 0}$
then
${-2 = A + 0 + 0}$
${\implies A = -2}$

Suppose ${x = -1}$
then 
${-2 = 0 + 0 - 2C}$
${\implies C = 1}$

Thus,
${\dfrac{-2}{x(1-x)(1+x)} = \dfrac{-2}{x} + \dfrac{-1}{1-x} + \dfrac{1}{1+x}}$

**c)**
${y = c_1x + c_2(e^{0.5}|1-x| + e^{\frac{0.5}{1-x}})}$

So ${\int \dfrac{-2}{x(1-x)(1+x)} dx = \int \dfrac{-2}{x} + \dfrac{-1}{1-x} + \dfrac{1}{1+x} dx}$

${= -2\ln|x| + \ln|1-x| + \ln|1+x|}$

For left hand side,

${\int \dfrac{du}{u} = \ln|u|}$

Therefore,

${\ln|u| = -\dfrac{3}{2}\ln|1-x^2| -2\ln|x| + \ln|1-x| + \ln|1+x|}$

So,

${|u| = |1-x^2|^{-\frac{3}{2}} - x^2 + |1-x| + |1+x|}$

Recall: ${u = v'}$
So,

${v = \int u dx = \pm \int |1-x^2|^{-\frac{3}{2}} - x^2 + |1-x| + |1+x|dx}$

Therefore, the solution is
${y = \pm x\int |1-x^2|^{-\frac{3}{2}} - x^2 + |1-x| + |1+x|dx}$

**d)**
${y = c_1x + c_2x\int |1-x^2|^{-\frac{3}{2}} - x^2 + |1-x| + |1+x|dx}$

>[!question] 2.2.6
>Find the general solution of ${2y'' + 2y' - 4y = 0}$.

${y = e^{rt},\;y' = re^{rt},\;y'=r^2e^{rt}}$
${2r^2 + 2r - 4 = 0 = 2(r^2 + r - 2) = 2(r+2)(r-1)}$
${r = -2, 1}$

${y = c_1e^{-2t} + c_2e^{t}}$