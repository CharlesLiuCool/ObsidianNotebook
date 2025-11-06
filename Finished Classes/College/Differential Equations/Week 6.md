### Nonhomogeneous Constant Coefficient Linear ODEs

${c_2y'' + c_1y' + c_0y = f(x)}$

### Method of Undetermined Coefficient

- Polynomials
- Exponentials
- Sine and Cosine

Suppose ${f(x) = x^2 + x - 3}$
- guess

${y_p = Ax^2 + Bx + C}$

Suppose ${f(x) = e^{rt}}$
Guess

${y_p = Ae^{rt}}$

Suppose ${f(x) = \cos(bt)}$
Guess
${y_p = A\sin(bt) + B\cos(bt)}$

>[!tip]
>Polynomial of degree ${n}$, guess polynomial of degree ${n}$
>Sine or cosine, guess ${A\sin + B\cos}$
>Exponential, guess exponential

>[!question] Example 1
>Find a particular solution to ${y'' - 3y' - 4y = e^{2t}}$

>[!check]- Solution
>${y_p = Ae^{2t}}$
>${y_p' = 2Ae^{2t}}$
>${y_p'' = 4ae^{2t}}$
>
${4ae^{2t} - 3\cdot2 A e^{2t} - 4Ae^{2t} = e^{2t}}$
${-6Ae^{2t} = e^{2t}}$
${A = -\dfrac{1}{6}}$
So,
${y_p = -\dfrac{1}{6}e^{2t}}$

>[!question] Example 2
>${y'' - 3y' - 4y = x^2}$

>[!check]- Solution
>${y_p = Ax^2 + Bx + C}$
>${y_p' = 2Ax + B}$
>${y_p'' = 2A}$
> 
> ${-4A = 1 \implies A = -\dfrac{1}{4}}$
> ${-4B + \dfrac{6}{4} = 0}$
> ${B = \frac{3}{8}}$
> ${C = -\frac{13}{32}}$
> 
> Thus, ${y_p = -\frac{1}{4}x^2 + \frac{3}{8}x - \frac{13}{32}}$

>[!question] Example 3
>Find the general solution to
>${y'' + y = \cos(2t)}$

>[!check]- Solution
>First solve,
> ${y'' + y = 0}$
> ${r^2 + 1 = 0}$
> ${r = \pm i}$
> ${y_h = c_1 \cos(t) + c_2\sin(t)}$
> Guess,
> ${y_p = A\cos(2t) + B\sin(2t)}$
> ${2(-A\sin(2t) + B\cos(2t))}$
> ${y_p'' = -4(A\cos(2t) + B\sin(2t))}$
> ${-3A \cos(2t) - 3B\sin(2t) = \cos(2t)}$
> ${-3A = 1 \implies A = -\dfrac{1}{3}}$
> ${B = 0}$
> ${y_p = -frac{1}{3}\cos(2t)}$
> ${y = y_h + y_p = c_1\cos(t) + c_2\sin(t) - \frac{1}{3}\cos(2t)}$

>[!question] Example 4
>Find a general solution
>${y'' -6y' + 9y = e^{3t}}$
>${r^2 - 6 + 9 = 0}$
>${r = 3 m 2}$
>${y_h = c_1e^{3t} + c_2te^{3t}}$
>${y_p = At^2 e^{3t}}$
>${y_p', y_p''}$
> ${A = \frac{1}{2}}$
> ${y = y_h + y_p = c_1e^{3t} + c_2te^{3t} + \frac{1}{2}t^2e^{3t}}$

>[!question] Example 5
>Find the form of the particular solution to 
>${y'' + y = t^3\sin(t) + t^2e^t + \cos(2t)\cos(t)}$
>${y_h = c_1\cos(t) + c_2\sin(t)}$
>${\begin{align} y_p &= (At^3+Bt^2+Ct+D)(E+\sin(t)+Ft\cos(t)) + (Gt^2+Ht+I)(Je^t) + \\&(K\cos(2t)+Lt\cos(t))(Mt\sin(t)+Nt\cos(t)) \end{align}}$

### Variation of Parameters

${y'' + q(t)y' + r(t)y = f(t)}$
with ${y_1, y_2}$ being a fundamental solution set to ${y'' + q(t)y' + r(t)y = 0}$

"Guess" ${y_p = u_1y_1 + u_2y_2}$
${y_p' = u_1'y_1 + u_1y_1' + u_2'y_2 + u_2y_2'}$
assume ${u_1'y_1 + u_2'y_2 = 0}$

${y_p' = u_1y_1' + u_2y_2'}$
${y_p'' = u_1'y_1'+u_2'y_2'+u_1'y_1''+u_2y_2''}$

${ u_1'y_1'+u_2'y_2'+u_1'y_1''+u_2y_2'' + q(t) (u_1y_1' + u_2y_2') + r(t) (u_1y_1 + u_2y_2) = f(t)}$

${u_1'y_1' + y_2'y_2' = f(t)}$

${u_1' = -\frac{u_2'y_2}{y_1}}$

${y_p = y_1\int\dfrac{-y_2f(t)}{W(y_1,y_2)}dt + y_2 \int \dfrac{y_1f(t)}{W(y_1,y_2)}dt}$
${W(y_1,y_2) = y_1y_2' - y_1'y_2}$

>[!question] Example 1
>Solve
>${2y'' + 17y = 6 \tan(3t)}$
>${y'' + 9y = 3 \tan(3t)}$

>[!check]- Solution
>Homogeneous Equation
>${y'' + 9y = 0}$
>${r^2 + 9}$
>${r = \pm 3}$
>${y_n = c_1\sin(3t) + c_2\cos(3t)}$
> 
> ${y_p = -\sin(3t) \cdot \int \dfrac{\cos(3t)\cdot f(t)}{W(y_1,y_2)}dt + \cos(3t) \int \dfrac{\sin(3t)\cdot 3t}{W(y_1,y_2)}dt}$
> 
> ${W(y_1,y_2) = \sin(3t)(-3\sin(3t)) - 3\cos(3t)\cos(3t)}$
> ${= - 3}$
>  
>  ${y_p = \dfrac{3\sin(3t)}{3} \int \cos(3t) \tan(3t)dt  -\dfrac{3\cos(3t)}{3} \int \sin(3t)\tan(3t)dt}$
>  ${\int \cos(3t)\tan(3t)dt = \sin(3t)dt = \dfrac{-\cos(3t)}{3}dt}$
>  ${\int\dfrac{\sin^2(3t)}{\cos(3t)}dt = \int \sec(3t) - \cos(3t)}$
>  ${= \dfrac{1}{3} \ln | \sec(3t) + \tan(3t)| - \dfrac{\sin(3t)}{3}}$
>  
>  ${y_n = \underbrace{c_1\sin(3t) + c_2\cos(3t)}_{y_h} + \underbrace{\dfrac{1}{3} \ln | \sec(3t) + \tan(3t)|}_{y_p}}$

>[!question] Example 2
>${ty'' - (t+1)y' + y = t^2}$
>Given
>${ty''-(t+1)y' + y = 0}$ has a a general solution of ${y = c_1e^t + c_2(t+1)}$

>[!check]- Solution
>${y'' - \dfrac{(t+1)}{t}y' + \dfrac{1}{t}y = t}$
>${y_p = -e^t \int \dfrac{(t+1)\cdot t}{W(y_1, y_2)} + (t+1)\int \dfrac{e^t \cdot t}{W(y_1,y_2)}dt}$
>${W(y_1,y_2) = y_1y_2' - y_1'y_2 = e^{t} - e^{t}(t+1) = -te^t}$
>
>${\int\dfrac{(t+1)}{-e^t}dt = \int e^{-t})t+1}dt}$