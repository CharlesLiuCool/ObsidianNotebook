**Q.1**
Show the Laplace transform

${\mathcal{L}\{e^{at}\} = \dfrac{1}{s-a}}$

using the integral definition of the Laplace transform and assuming ${s > a}$.

$${\int_0^{\infty} e^{-st} e^{at} dt = \int_0^\infty e^{-(s-a)t}dt}$$

Since ${s > a}$, then we can replace ${s-a}$ with a new variable ${k>0}$

So,
$${\int_0^\infty e^{-(s-a)t}dt = \int_0^\infty e^{-kt}dt = -\dfrac{e^{-kt}}{k} \bigg|_0^{\infty} = \dfrac{1}{k} = \dfrac{1}{s-a}}$$

Which means

${\mathcal{L}\{e^{at}\} = \dfrac{1}{s-a}}$

**6.1.5**
Find the Laplace transform of ${3+t^5 + \sin(\pi t)}$.

${\mathcal{L}\{3+t^5 + \sin(\pi t)\} = \mathcal{L}\{3\} + \mathcal{L}\{t^5\} + \mathcal{L}\{\sin(\pi t\}}$

${= \dfrac{3}{s} + \dfrac{5!}{s^{6}} + \dfrac{\pi}{s^2+\pi^2}}$

**6.1.6**
Find the Laplace transform of ${a + bt + ct^2}$ for some constants ${a}$, ${b}$, and ${c}$.

${\mathcal{L} \{a + bt + ct^2\} = \mathcal{L}\{a\} + \mathcal{L}\{bt\} + \mathcal{L}\{ct^2\}}$

${\dfrac{a}{s} + \dfrac{b}{s^2} + \dfrac{2c}{s^3}}$

**6.1.12**
Find the Laplace transform of 
${f(t) =}$
${t}$ if ${t \ge 1}$,
${0}$ if ${t < 1}$

${f(t) = u(t-1)}$
(same as Heaviside function)

${\mathcal{L} \{f(t)\} = \int_1^\infty te^{-st}dt = -t\dfrac{e^{-st}}{s}\bigg|_1^{\infty} + \int_1^\infty \dfrac{e^{-st}}{s}dt}$

${= -\dfrac{e^{-s}}{s} - e^{-st}{s^2}\bigg|_1^\infty = \dfrac{e^{-s}}{s} + \dfrac{e^{-s}}{s^2}}$

**6.1.10**
Find the Laplace transform of ${\dfrac{2s}{s^2 - 1}}$

${\mathcal{L}^{-1} \{\dfrac{2s}{s^2 - 1}\}}$

Partial Fraction Decomposition
${2s = A(s-1) + B(s+1)}$
if ${s = 1}$
${2 = 2B \implies B = 1}$
if ${s = -1}$
${2 = 2A \implies A = 1}$

So, ${\mathcal{L}^{-1} \left\{\dfrac{2s}{s^2 - 1}\right\} = \mathcal{L}^{-1} \left\{\dfrac{1}{s+1} + \dfrac{1}{s-1}\right\} = \mathcal{L}^{-1} \left\{\dfrac{1}{s+1}\right\} + \mathcal{L}^{-1} \left\{\dfrac{1}{s-1}\right\} = e^t + e^{-t}}$

**6.1.102**

Find the inverse Laplace transform of ${\dfrac{8}{s^3(s+2)}}$

Partial Fraction Decomposition
${\dfrac{8}{s^3(s+2)} = \dfrac{A}{s} + \dfrac{B}{s^2} + \dfrac{C}{s^3} + \dfrac{D}{s+2}}$
We can assume this since The numerator of the fraction before decomposition is a constant.

${8 = As^2(s+2) + (B)s(s+2) + (C)(s+2) + Ds^3}$

if ${s = 0}$
${2C = 8}$
${\implies C = 4}$
if ${s = -2}$
${-8D = 8}$
${\implies D = -1}$

${8 = As^2(s+2) + (B)s(s+2) + (4)(s+2) - s^3}$

${8 = As^3 + 2As^2 + Bs^2 + 2Bs + 4s + 8 - s^3}$
${\implies 0 = (A-1)s^3 + (2A+B)s^2 + (2B + 4)s}$

Comparing of coefficients

${A - 1 = 0}$
${\implies A = 1}$
${2 + B = 0}$
${\implies B = -2}$

So, ${\dfrac{8}{s^3(s+2)} = \dfrac{1}{s} + \dfrac{-2}{s^2} + \dfrac{4}{s^3} + \dfrac{-1}{s+2}}$

Therefore 
${\begin{align} & \mathcal{L}^{-1}\{\dfrac{8}{s^3(s+2)}\} = \mathcal{L}\{\dfrac{1}{s} + \dfrac{-2}{s^2} + \dfrac{4}{s^3} + \dfrac{-1}{s+2}\} \\ &= \mathcal{L}\{\dfrac{1}{s}\} + \mathcal{L} \{\dfrac{-2}{s^2}\} + \mathcal\{\dfrac{4}{s^3}\} + \mathcal{L}\{\dfrac{-1}{s+2}\} = 1 - 2t + 2t^2 - e^{-2t} \end{align}}$