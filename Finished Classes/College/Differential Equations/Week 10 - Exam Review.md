>[!question] Example
>Solve
> ${y'' + 2y' - 3y = \cos(t), y(0) = y'(0) = 0}$
>a) method of undetermined coefficients
>b) variation of parameters
>c) Laplace transform

>[!check]- Solution
>1) Solve the homogeneous equation
>${y'' + 2y' - 3y = 0}$
>${y = e^{rt}}$
>${r^2 + 2r - 3 = 0}$
>${\implies (r+3)(r-1) = 0, r = -3,1}$
>So ${y_h = c_1e^{t} + c_2e^{-3t}}$
>a)
>${y_p = A\cos(t) + B\sin(t)}$
>${y_p' = -A\sin(t) + B\cos(t)}$
>${y_p'' = -A\cos(t) - B\sin(t)}$
>${-A\cos(t) - B\sin(t) + 2(-A\sin(t) + B\cos(t))}$
> Slap it in and compare coefficients
> ${y = c_1e^t + c_2e^{-3t} - \frac{1}{5}\cos(t) + \frac{1}{6}\sin(t)}$
> 2) Variation of parameters
>${y_p = -y_1\int \frac{y_2f(x)}{W(y_1,y_2)}dx + y_2\int\frac{y_1f(x)}{W(y_1,y_2)}dx}$

___

### Springs

${m = }$ mass in kg
${k = }$ spring constant ${\frac{N}{m}}$
${c = }$ damping coefficient ${\frac{N}{\frac{m}{s}} = \frac{Ns}{m}}$
${F_{ext} = }$external force, forcing function

If ${F_ext = 0}$ => unforced spring

${mx'' + cx' + kx = F_{ext}}$

if ${c = 0 \implies}$ undamped spring

**Case 1:** Two distinct real roots

${c^2 - 4mk > 0}$

${\implies}$ overdamped
${x = c_1e^{rt} + c_2e^{r_2t}}$

**Case 2:** Repeated root
${\implies c^2 = 4mk}$
${\implies}$ critically damped

${x = c_1e^{rt} + c_2te^{rt}}$

**Case 3:** Complex roots

${c^2 - 4mk < 0}$
${\implies}$ underdamped

${x = e^{pt} (c_1\cos(\omega_1t) + c_2\sin(\omega_1t))}$

${\omega_0 = \sqrt{k}{m}}$

if ${mx' + kx = 0}$
${mx'' + kx = \sin(\omega_t)}$
resonance ${\implies \omega = \omega_0}$
beats ${\implies \omega \neq \omega_0}$

### Dirac Delta

${\int_{-\infty}^{\infty} \delta(t)f(t)dt = f(0)}$

${\int_a^b \delta(t)f(t) dt = \begin{cases} f(0) & \text{if }0\;\in \;[a,b]\\ 0 & \text{otherwise  }\end{cases}}$

${\mathcal{L}\{\delta(t)\} = 1}$

### Heaviside Functions

${u_c(t) = u(t-c) = \begin{cases} 1 & \text{if } t \geq c \\ 0 & \text{otherwise} \end{cases}}$

${\mathcal{L}\{u_c(t)\} = \dfrac{e^{-cs}}{s}}$

${\mathcal{L}\{f(t-a)u(t-a)\} = e^{-as}\mathcal{L}\{f(t)\} = e^{-as}F(s)}$

>[!question] Example
>Find ${\mathcal{L}^{-1}\{e^{-3s} \frac{4}{s^2+9}\}}$

>[!check]- Solution
${= u(t-3)f(t-3)}$
>
${\mathcal{L}^{-1} \{\frac{4}{s^2+9}\} = \frac{4}{3}\mathcal{L}\{\frac{3}{s^2+9}\} = \dfrac{4}{3}\sin(3t) = f(t)}$
> 
> ${u(t-3) \cdot \frac{4}{3}\sin(3(t-3))}$

>[!question] Example 2
${\mathcal{L} \{u(t-1)t\}}$

>[!check]- Solution
${= \mathcal{L}\{u(t-1)(t-1+1)\} = \mathcal{L}\{u(t-1)(t-1)\} + \mathcal{L}\{u(t-1)\} = \frac{e^{-s}}{s^2} + \frac{e^{-s}}{s}}$

### Convolution

${f * g = g * f = \int_0^t f(\tau)g(t - \tau)d\tau}$

${\mathcal{L}\{f * g\} = \mathcal{L}\{f\}\mathcal{L}\{g\}}$

>[!question]- Example 4
> ${\mathcal{L}\{t * \sin(3t)\}}$

>[!check]- Solution
>${= \mathcal{L}\{t\} \mathcal{L}\{\sin(3t)\} = \frac{3}{s^2(s^2+9)}}$

>[!question] Example 5
>Find ${\mathcal{L}^{-1} \{\frac{s}{s^2+4} \cdot F(s)\}}$

>[!check]- Solution
>${\cos(2t) * f(t) = \int_0^t \cos(2\tau)f(t-\tau) d\tau}$