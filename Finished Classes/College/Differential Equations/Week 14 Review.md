### Outline

- Terminology
- Separation of Variables
- Integrating Factor\
- Substitutions
	- Bernoulli
	- $\frac{y}{x}$
	- others
- Exact
- Autonomous
	- e.g.
		- phase diagram
- Word problems
	- Tanks
	- Newton's Law of Cooling
	- Exponential Growth or Decay
	- Logistic Equations
- Initial Value Problem (IVP)

>[!question] Example 1
>Solve
${y' + \frac{y}{x} = \cos(x)}$

>[!check]-
>Integrating factor
>${y' + y\frac{1}{x} = \cos(x)}$
>${\mu = e^{\int \frac{1}{x}dx} = \ln|x| = x}$
>
>${y(x) = \dfrac{\int\mu(x)g(x)dx + c}{\mu(x)}}$
>
>${=\dfrac{\int x\cos(x)dx + c}{x} = \dfrac{x\sin(x) - \int \sin(x)dx}{x} = \dfrac{x\sin(x) + \cos(x)}{x}}$

>[!question] Example 2
>Solve
>${xy' + x^2 = 3 - x}$

>[!check]- Solution
>${xy' = x^2 - x + 3}$
>${y' = x - 1 + \frac{3}{x}}$
>${dy = (x - 1 + \frac{3}{x})dx}$
>${\int dy = \int(x - 1 + \frac{3}{x})dx }$
>${y = -\frac{x^2}{2} - x + 3\ln|x| + C}$

>[!question] Example 3
>Solve
>${x\cos(y)y' + \sin(y) = 2}$

>[!check]- Solution
>Exact
>${\dfrac{\partial x\cos(y)}{\partial x} = \cos(y) = \dfrac{\partial \sin(y) - 2}{\partial y}}$
>${\int x\cos(y)dy = x\sin(y) + f(x)}$
>${\int \sin(y) - 2dx = x\sin(y) - 2x + g(y)}$
>${x\sin(y) - 2x = c}$
>Also can use substitution ${u = \sin(y)}$ or ${u = \sin(y)-2}$.

>[!question] Example 4
>${y' + 4yy' = -2xy}$
>${\frac{y'(1+4y)}{y} = -2x}$
>Separate and integrate.

___

- Homogeneous
Linear constant coefficient ODEs.
	- 2nd order
	- Higher order
- Nonhomogeneous
	- Method of undetermined coefficients
	- Variation of Parameters
- Linear independence of solutions
	- Wronskian
- Laplace transform
	- Integral definition
	- Table
	- Shifting Theorem
- Convolution
- Dirac Delta
- Heaviside
- Volterra
- Springs

${x^3 + 3x^2 + 3x + 1 = 0}$
${(x+1)^3 = 0}$
${x = -1m3}$