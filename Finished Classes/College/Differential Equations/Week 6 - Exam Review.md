Bernoulli

${y' + \dfrac{1}{x}y = x^2y^3}$

${v = y^{1-3} = y^{-2}}$
${v' = -2y^{-3}y'}$

So,

${y' = \dfrac{y^3v'}{-2}}$

${v' - \dfrac{2}{x}v = -2x^2}$

Use integrating factor,

${v = y^{-2} = -2x^3 + cx^2}$
${y = \dfrac{1}{\sqrt{-2x^3 + cx^2}}}$

${y' + \dfrac{x}{y} = \dfrac{y^2}{x^2} + \dfrac{y}{x}}$

${y' + \dfrac{x}{y} = \dfrac{y^2}{x^2} + \dfrac{y}{x}}$

${\dfrac{y}{x} = v \implies xv = y}$
${xv' + v = y}$

${y' = 2(3-y)y^2(1-y)}$

a) Find all critical points
b) Classify them
c) Draw a phase portrait
d) Sketch typical solution curves

a) ${0 = 2(3-y)(1-y)y^2}$
${y = 3,1,0}$

b) ${}

c) ${y = 0}$, semi-stable
${y = 1}$ stable
${y = 3}$ unstable
![[Week 6 - Exam Review 2024-09-30 10.42.20.excalidraw]]

d)
![[Week 6 - Exam Review 2024-09-30 10.44.50.excalidraw]]

Euler's Method

${h}$ = step size
${(x_0,\;y_0)}$ = initial conditions
${x_{i+1} = x_i + h}$
${y_{i+1} = y_i + hf(x_i,y_i)}$
${y' = f(x,y)}$

Suppose

${y' = x(1-y)}$
${y(0) = 2}$
approximate ${y(2)}$ with a step size of 1.

| i   | x_i | y_i |
| --- | --- | --- |
| 0   | 0   | 2   |
| 1   | 1   | 2   |
| 2   | 2   |  1  |

${x+1 = x_0 + h = 0 + 1 = 1}$
${y_1 = y_0 + hf(x_0,\;y_0) = 2 + 1 \cdot 0 \cdot (1-2) = 2}$
${x_2 = x_1 + h = 1 + 1 = 2}$
${y_2 = 1}$

So,
${y(2) \approx 1}$

Slope Field

Sketch a slope field for
${y' = x(1-y)}$

yes

