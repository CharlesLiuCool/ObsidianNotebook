
### Systems of ODEs

${x_1' = F_1(x_1,x_2,...x_n,t)}$
${x_2' = F_2(x_1,x_2,...,x_n,t)}$
.
.
.
${x_n' = F_n(x_1,x_2,...,x_n)}$

>[!question] Example 1
>Latka-Volterra Equation
>${x =}$ population of prey
>${y =}$ population of predator
>
> ${\frac{dx}{dt} = \alpha x - \beta x y}$
> ${\frac{dy}{dt} = - \gamma y + wxy}$

>[!question] Example 2
>Linear ODE system
>${x_1' = 3x_1 + t^2x_2 + 4x_3 - \sin(t)}$
>${x_2' = x_1 - t^3}$
>${x_3' = x_1 + x_2 - 5x_3 + 0}$

>[!question] Example 3
>${x_c' = 3(x_m-x_c)}$, ${\;\;x_c =}$ cat's position
>${x_m' = 2}$, ${\;\;x_m =}$ mouse position

>[!check]- Solution
>${x_m' = 2}$
>${x_m = 2t + c_m}$
> 
> ${x_c' = 3(2t+c_m) - 3x_c}$
> ${x_c' + 3x_c = 6t + 3c_m}$
> ${\mu = e^{3t}}$
> ${x_c = \frac{\int e^{3t} (6t + 3cm)dt + c_c}{e^{3t}}}$
> ${x_c = 2t + c_m - \frac{2}{3} + c_ce^{-3t}}$

### Reduction of Order

${x'' + 3t^2x' + 2x = 4t}$

${x_1 = x}$
${x_1' = x' = x_2}$
${x'' = x_2'}$

${x_2' + 3t^2x_2 + 2x_1 = 4t}$
${x_1' = x_2}$

${x_2' + 5x_2 + 6x_1 = 0}$
${x_1' = x_2}$
${x_2' = x_1''}$

${x_1'' + 5x_1' + 6x_1 = 0}$
${r^2 + 5r + 6 = 0}$
${(r+2)(r+3) = 0}$
${x_1 = c_1e^{-2t} + c_2e^{-3t}}$

${x_2 = x_1' = -2c_1e^{-2t} -  3c_2e^{-3t}}$

____

${x_1'' = F_1(x_1', x_2', ... , x_n', x_1, x_2, ... ,x_n, t)}$
${x_2'' = F_2(x_1', x_2', ... , x_n', x_1, x_2, ... ,x_n, t)}$
.
.
.
${x_n'' = F_n(x_1', x_2', ... , x_n', x_1, x_2, ... ,x_n, t)}$

${x_1' = G_1(x_1, x_2, ... ,x_n, t)}$
${x_2' = G_2(x_1, x_2, ... ,x_n, t)}$
.
.
.
${x_n' = G_n(x_1, x_2, ... ,x_n, t)}$

___

>[!question] Example
> spring-mass1-spring-mass2
> ${m_1x_1'' = -k_1x_1 + k_2x_2}$
> ${m_2x_2'' = -k_2x_2}$

>[!check]- Solution
>${x_1'' = \frac{-k_1}{m_1}x_1 + \frac{k_2}{m_1}x_2}$
>${x_2'' = -\frac{k_2}{m_2}x_2}$
> 
> The remainder of the solution is trivial and is left as a exercise to the reader.

### Direction Field

${\frac{dy}{dt} = x + y}$
${\frac{dx}{dt} = x - y}$

### Existence and Uniqueness

${x_1' = F_1(x_1, x_2, ..., x_n, t)}$
${x_2' = F_2(x_1, x_2, ..., x_n, t)}$
.
.
.
${x_n' = F_n(x_1, x_2, ..., x_n, t)}$

If for every ${j = 1, 2, ..., n}$ and ${k = 1, 2, ..., n}$ each ${F_{j}}$ is continuous and ${\frac{\delta F_j}{\delta x_k}}$ exists and continuous near some ${(x_1^0, x_2^0, ... t^0)}$, then a solution to the system exists and is unique near ${x_1(t^0) = x_1^0, x_2(t^0) = x_2^0,...x_n(t^0) = x_n^0}$

### Systems of ODEs as Matrices

${\vec{V}(t) = \left(\begin{matrix} v_1(t) \\ v_2(t) \\ . \\ . \\ . \\ v_n(t)  \end{matrix}\right)}$

${\vec{V}'(t) = \left(\begin{matrix} v_1'(t) \\ v_2'(t) \\ . \\ . \\ . \\ v_n'(t)  \end{matrix}\right)}$

${A(t) = \left( \begin{matrix}A_{11}(t) & A_{12}(t) & ... & A_{1n}(t) \\ . \\ . \\ . \\ . \\ A_{n1}(t) & ... & & A_{nn}(t) \end{matrix}\right)}$

#### Properties
Let ${c \in \mathbb{R}}$
1) ${\frac{d}{dt} (A(t) + B(t)) = A'(t) + B'(t)}$
2) ${\frac{d}{dt}(cA(t)) = c\frac{d}{dt}(A(t)) = cA'(t)}$

3) Let ${C}$ be a constant matrix, then
${\frac{d}{dt}(CA(t)) = CA'(t)}$
${\frac{d}{dt}(A(t)C) = A'(t)C}$

4) ${\frac{d}{dt}(A(t)B(t) = A'(t)B(t) + A(t)B'(t)}$

A system of ODEs is linear if it can be written in the following form:
${x_1' = \Sigma_{i=1}^nf_i(t)x_i(t) + g_i(t)}$

>[!question] Example 2
>${x_1' = \sin(t)x_1 + \cos(t)x_2}$
>${x_2' = t^2x_1 - 3tx_2 + 7}$

