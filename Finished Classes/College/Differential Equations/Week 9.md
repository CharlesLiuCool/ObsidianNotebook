>[!question] Example 2
>
${f(t) = }$
${t}$ if ${0 \le t < 2}$
${t^2}$ if ${t \geq 2}$
${\sin(t)}$ if ${t < 0}$

>[!check]- Solution
${ = \sin(t) + u(t)(t - \sin(t)) + u(t-2)(t^2 - t)}$

>[!question] Example 3
>${f(t) = }$
>${4}$ if ${t \geq 3}$
>${\sin(t - 3)}$ if ${t < 3}$
> 
> Take ${\mathcal{L}\{f(t)\}}$

>[!check]- Solution
>${f(t) = \sin(t-3) + (4-\sin(t-3))u(t-3)}$
>${\mathcal{L}\{f(t)\} = \mathcal{L}\{\sin(t-3) + (y - \sin(t-3)u(t-3)\}}$
>${= \mathcal{L}\{\sin(t-3)\} + 4\mathcal{L}\{u(t-3)\} - \mathcal{L}\{\sin(t-3)u(t-3)\}}$
>${= \dfrac{-s\sin(3) + \cos(3)}{s^2 + 1^2} + \dfrac{4e^{-3s}}{s} - e^{-3t}\dfrac{1}{s^2+1^2}}$

$${\mathcal{L}\left\{\int_0^t f(\tau) d\tau\right\} = \int_0^{\infty}e^{-st}\left(\int_0^{t}f(\tau)d\tau\right)dt }$$
$${= (\dfrac{-e^{-st}}{s})\int_0^tf(\tau)d\tau\bigg|_0^\infty + \underbrace{\dfrac{1}{s}\int_0^{\infty}e^{-st}f(t)dt}_{\mathcal{L}\{f(t)\}}}$$

${u = \int_0^{t} f(\tau) d\tau}$
${du = f(t)dt}$

So,
${\mathcal{L}\{\int_0^tf(\tau)d\tau\} = \dfrac{1}{s}\mathcal{L}\{f(t)\}}$

___

>[!question] Example 4
>${\mathcal{L}\{\int_0^{t}(\tau^3 + \tau^2 + 3 - \sin(4\tau)) d\tau\}}$ 

>[!check]- Solution
>${= \dfrac{1}{s}\mathcal{L}\{t^3 + t^2 + 3 - \sin(4t)\}= \dfrac{1}{s}\left(\dfrac{3!}{s^4} + \dfrac{2!}{s^3} + \dfrac{3}{5} - \dfrac{4}{s^2 + 4^2}\right)}$

>[!question] Example 5
${x(t) - t = \int_0^t x(\tau)d\tau}$

>[!check]- Solution
>${x'(t) - 1 = x(t)}$
>
>${x'(t) - x(t) = 1}$
>
>${\mu = e^{\int(-1)dt} = e^{-t}}$
>${x(t) = \dfrac{\int 1 e^{-t}dt + c}{e^{-t}}}$
>${= \dfrac{-e^{-t} + c}{e^{-t}} = 1 + ce^{-t}}$
>${-1 + ce^{t} - t = \int_0^{t}(-1 + ce^{t})dt = (-\tau + ce^\tau)\bigg|_0^t}$
>${= -t + ce^{t} - (-0 + ce^{0})}$
>${c = 1}$
>${x(s) - \dfrac{1}{s^2} = \dfrac{1}{s}x(s)}$
>${\dfrac{1}{s(s-1)} = x(s)}$
>${x(s) = \dfrac{1}{s-1} - \dfrac{1}{s}}$
>
>${x(t) = \mathcal{L}^{-1}\left\{\dfrac{1}{s-1} - \dfrac{1}{s}\right\} = -1 + e^t}$

Suppose ${f(t)}$ is periodic with period ${p}$
That is, ${f(t + p) = f(t)}$

$${\begin{align}\mathcal{L}f(t) &= \int_0^{\infty}e^{-st}f(t)dt = \int_0^{p}e^{-st}f(t)dt + \int_p^{\infty}e^{-st}f(t)dt \\ &= \int_0^{p}e^{-st}f(t)dt + \int_0^{\infty}e^{-s(u+p)}f(u+p)du \\ &= \int_0^p e^{-st}f(t)dt + \underbrace{e^{-sp}\int_0^\infty e^{-su}f(u)du}_{\mathcal{L}\{f(t)\}}\end{align}}$$

$${\mathcal{L}\{f(t)\} = \dfrac{1}{e^{-sp}}\int_0^pe^{-st}f(t)dt}$$

>[!question] Example 6
> 
> ${f(t) =}$
> ${1}$ for ${0 \le t < \dfrac{p}{2}}$
>${0}$ for ${\dfrac{p}{2}\le t < p}$
>is periodic with period ${p}$

>[!check]- Solution
>${\mathcal{L}\{f(t)\} = \dfrac{1}{1-e^{-sp}} \int_0^pe^{-st}f(t)dt}$
>${= \dfrac{1}{1-e^{sp}} \int_0^{\frac{p}{2}}e^{-st}dt = \dfrac{1}{1-e^{sp}} \cdot (\dfrac{-e^{-st}}{s})\bigg|_0^{\frac{p}{2}} = \dfrac{1-e^{-\frac{sp}{2}}}{s(1-e^{-sp})}}$

>[!question] Example 7
>Suppose ${f(t) = t}$ is periodic with period ${p}$
>${0 \le t < p}$

>[!check]- Solution
>${\mathcal{L}\{f(t)\} = \dfrac{1}{1-e^{-sp}}\left(\dfrac{-pe^{-sp}}{s} - \dfrac{e^{-sp} - 1}{s^2}\right)}$

### Convolution

${f * g = \int_0^t f(\tau)g(t-\tau)d\tau}$

>[!question] Example 1
>${t * \sin(t) = \int_0^{t}\tau\sin(t-\tau)d\tau}$


>[!check]- Solution
>${u = t - \tau}$
> ${du = -dt}$
>${\int_t^0 (t-u) \sin(u) -du = \int_0^t (t-u) \sin(u) du}$
> 
> ${w = t - u}$
> ${dw = -ds}$
> ${dv = \sin(u)du}$
> ${v = -\cos(u)}$
> ${t - \sin(t)}$

>[!question] Example 2
> 
> ${t^2 * (t-2) = \int_0^t\tau^2(t-\tau-2)d\tau = \int_0^{t} t\tau^2 - \tau^3 = 2\tau^2 d\tau}$
> 
> ${g(t) = t-2}$
> 
> ${t\dfrac{\tau^3}{3} - \dfrac{\tau^4}{4} - \dfrac{2}{3}\tau^3 \bigg|_0^t}$
> 
> ${= \dfrac{t^4}{3} - \dfrac{t^4}{4} - \dfrac{2}{3}t^3 = \dfrac{t^4}{12} - \dfrac{2}{3}t^3}$

### Properties of Convolution

${f * g = g * f}$
${(cf) * g = f * (g) = c(f * g)}$
${(f+g) * h = f * h + g * h}$
${(f * g) * h = f * (g * h)}$

${\mathcal{L}\{f * g\} = \mathcal{L} \{f\} \mathcal{L}\{g\}}$

>[!question] Example 3
>${F(s) = \left(\dfrac{1}{s^2}\right)\left(\dfrac{1}{s-1}\right) }$

>[!check]- Solution
>${= \mathcal{L}\{t\}\mathcal{L}\{e^t\} = \mathcal{L}\{t*e^t\}}$
>
>${f(t) = t * e^t}$
>
>${\int_0^t \tau e^{t - \tau} d\tau = e^t - t - 1}$

>[!question] Example 4

${\omega_0 > 0, x(0) = x'(0) = 0}$

Solve ${\mathcal{L}\{x'' + \omega_0^2x\} = \mathcal{L} \{f(t)\}}$

### Dirac Delta "Function"

*NOT* a function!

Take a square so squish it so its a line so area is ${1}$
as ${\lim \rightarrow \infty}$, height ${\rightarrow \infty}$

${\int_a^{b}\delta(t)f(t) = }$
${f(0)\;\text{for}\;0 \in [a,b]}$
${0\;\text{for}\;0 \notin [a,b]}$

>[!question] Example 1

\int_0^{\infty} \delta(t)e^{-t^2}$

>[!question] Example 7
>
${\int_{-3}^1 \delta(t-2) \sin(t)dt }$

>[!check]
${= \int_{-1}^{3}\delta{u}\sin(u-2)dt = \sin(-2)}$


>[!question] Example 8
> ${\int_{-1}^1 \delta{(2t)}\cos(t)dt }$

> [!check]-
> ${= \int_{-2}^2 \delta{u}\cos(\frac{u}{2}) \frac{du}{2} = \frac{1}{2}\cos(0) = \frac{1}{2}}$

___

${\mathcal{L} \{\delta(t)\}= \int_0^{\infty}e^{-st} \delta(t)dt = e^0 = 1}$

${\mathcal{L}\{\delta{t-a}\} = \int_0^{\infty} e^{-st} \delta(t-a)dt}$
${u = t-a}$
${du = dt}$

${= \int_{-a}^\infty e^{-s(u+a)}\delta(u)du = e^{-sa}\int_{-a}^{\infty} e^{-su} \delta(u) du = e^{-sa}e^0 = e^{-sa}}$

${\mathcal{L} \{\int_0^t f(\tau)d\tau\} = \dfrac{F(s)}{s} \implies \int_0^{t}\delta(\tau)d\tau = u(t)}$

___ 

**Impulse Response**

${Lx = \delta(x)}$

The solution to this is called the impulse response to ${Lx}$

>[!question] Example 9
> 
> Find the impulse response to
> ${x'' + \omega_0^2x = \delta (t), x(0) = x'(0) = 0}$

>[!check]- Solution
>${\mathcal{L} \{x'' + \omega_0^2x\} = \mathcal{L}\{\delta(t)\}}$
> ${(s^2x(s) - sx(0) = x'(0)) + \omega_0^2x(s) = 1}$
> ${s^2x(s) + \omega_0^2x(s) = 1}$
> ${\mathcal{L}^{-1}\{x(s)\} = \mathcal{L}^{-1}\{\frac{\omega_0}{s^2+\omega_0^2}\} = \frac{\sin(\omega_0t)}{\omega_0}}$
> ...
> ${x(t) = \frac{1}{\omega_0}\sin(u_0t)}$
> An impulse response has a sinusoidal motion.

### Euler Bernoulli Equation

${EI \dfrac{d^4y}{dx^4} = F(x)}$

${y(0) = y'(0) = y''(0) = y'''(0) = 0}$

>[!question] Example 10
>Find the impulse response to 
>${\dfrac{d^4y}{dx^4} = \delta (x)}$, ${y(0) = y'(0) = y''(0) = y'''(0) = 0}$

>[!check]- Solution
> ${\mathcal{L}\{\dfrac{d^4y}{dx^4}\} = \mathcal{L}\{\delta(x)\} = 1}$
>
${\mathcal{L}\{\dfrac{d^4y}{dx^4}\} = s^4Y(s) - s^3y(0) - s^2y'(0) - sy''(0) - y'''(0)}$
>
${s^4y(s) = 1 \implies Y(s) = \dfrac{1}{s^4}}$
${\mathcal{L}^{-1} \{Y(s)\} = \mathcal{L}^{-1}\{\dfrac{1}{s^4}\}}$
${y(t) = \mathcal{L}^{-1}\{\frac{3!}{3!s^4}\} = \frac{1}{6}\mathcal{L}^{-1}\{\frac{3!}{s^4}\}}$
${y(t) = \frac{1}{6}x^3}$
