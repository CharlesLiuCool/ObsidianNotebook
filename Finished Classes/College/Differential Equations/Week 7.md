
>[!question] Example 1
>Solve the initial value problem
>${y'' - 2y' + y = e^x\ln(x), y(1) = 2, y'(1)=0}$

>[!check]- Solution
>${r^2 - 2r + 1 = 0}$
>${(r-1)^2}$
>${y_h = c_1e^x + c_2xe^x}$
>${y_1 = e^x, y_2 = xe^x}$
>
>${y_p -e^x\int\dfrac{xe^x\cdot e^x\ln|x|}{e^{2x}}dx + xe^x\int\dfrac{e^x\cdot e^x \ln|x|}{e^{2x}}dx}$
>
>${W(y_1,y_2) = \begin{vmatrix} e^x & xe^x \\ e^x & e^x+xe^x \end{vmatrix} = e^x(e^x+xe^x) - e^x\cdot xe^x = e^{2x}}$
>
>${y_p = -e^x \int x\ln(x)dx + xe^x\int \ln|x|dx}$
>
>${= -e^x\left(\dfrac{x^2}{2}\ln|x| - \int\dfrac{x}{2}dx) + xe^x(x\ln(x)-\int1dx\right)}$
>
>${\dfrac{x^2}{2}\ln(x)e^x-\dfrac{3}{4}x^2e^x}$
> 
> ${y = y_h + y_p = c_1e^x + c_2xe^x + \dfrac{x^2}{2}\ln(x)e^x - \dfrac{3}{4}x^2e^x}$
> ${y(1) = c_1e + c_2e - \frac{3}{4}e}$
> ${c_1e^x + c_2e^x + c_2xe^x + x\ln(x)e^x + \dfrac{x^2}{2}\cdot\dfrac{1}{x}e^x + \dfrac{x^2}{2}\ln(x)e^x - \dfrac{3}{2}xe^x - \dfrac{3}{4}x^2e^x}$

## Springs

${mx'' + cx' + kx = F(t)}$
${m}$ = mass
${c}$ = damping/friction
${k}$ = spring constant
${F(t)}$ = external force

### Undamped

${c = 0}$

${mx'' + kx = F_0\cos(\omega t)}$
${\omega \neq \omega_0}$

${\omega_0 = \sqrt{\dfrac{k}{m}}}$

${x_h}$ first

${mx'' + kx = 0}$
${mr^2 + k = 0}$

${r^2 = -\dfrac{k}{m}}$

${r = \pm \sqrt{\dfrac{k}{m}}i = \pm\,\omega_0\,i}$

${x_h = c_1\cos(\omega_0t) + c_2\sin(\omega_0 t)}$

${x_p = A\cos(\omega t) + B\sin(\omega t)}$

${x_p' = \omega (-A \sin(\omega t) + B\cos(\omega t))}$

${x_p'' = -\omega^2 (A\cos(\omega t) + B\sin(\omega t))}$

Plug into original equation ${mx'' + kx = 0}$

Compare terms

${\implies (-mw^2 + k) B\sin(\omega t) = 0 \implies B = 0}$

${\implies (-mw^2 + k) A\cos(\omega t) = F_0\cos(\omega t)}$

${A = \dfrac{F_0}{k-m\omega^2} = \dfrac{F_0}{m(\frac{k}{m} - \omega^2)} = \dfrac{F_0}{m(\omega_0^2 - \omega^2)}}$

${x = c_1\cos(\omega_0 t) + c_2\sin(\omega_0 t) + \dfrac{F_0}{m(\omega_0^2 - \omega^2)}\cos(\omega t)}$

#### Beats

${m = k = 1}$
${F_0 = 2}$
${\omega = 3}$

Complicated wave

```desmos-graph
left=-5; right=5;
top=4; bottom=-4;
---
y = \cos(x)+\sin(x)-2/(1*(1-4))\cos(3x) | x > -5 | x < 5 | RED
```

___

${c = 0}$

${mx'' + kx = F_0\cos(\omega_0 t)}$

${x = c_1\cos(\omega_0 t) + c_2\sin(\omega_0t)}$

${x_p = t(A\cos(\omega_0t) + B\sin(\omega_0 t))}$

${x_p' =\;...}$

${x_p'' =\;...}$

Plug into original equation ${mx'' + kx = F_0\cos(\omega_0 t)}$

${2m\omega_0 (A\sin(\omega_0 t) + B\sin(\omega_0 t)) = \cos(\omega_0 t)F_0}$

${\implies A = 0}$ (no ${\sin}$ term)

${2m\omega_0B = F_0}$

${\implies B = \dfrac{F_0}{2m\omega_0}}$

${x = c_1\cos(\omega_0 t) + c_2\sin(\omega_0t) + \dfrac{F_0t}{2m\omega_0}\sin(\omega_0t)}$

Special Case: **Resonance**
As time goes on, amplitude gets bigger and bigger until it goes to infinity.

```desmos-graph
left=-100; right=100;
top=100; bottom=-100;
---
y = \cos(x)+\sin(x)-1/2x\sin(x) | x > -100 | x < 100 | RED
```


### Damped

${mx'' + cx' + kx = F_0\cos(\omega t)}$

${c^2 < 4km}$

${mr^2 + cr + k = 0}$

${r = \dfrac{-c \pm \sqrt{c^2 - 4km}}{2m} = -\dfrac{c}{2m} \pm \omega_i}$

${\omega_i = \sqrt{k-\dfrac{c^2}{4m}}}$

${x_h = e^{-pt} \cdot (\cos(\omega_1t) + c_2\sin(\omega_1t)) = x_{tr}}$
This is called the **transient solution**.

${\omega_1 = \sqrt{\omega_0^2 - p^2} \neq \omega_0}$

```desmos-graph
left=-10; right=10;
top=5; bottom=-5;
---
y = e^{-1/5x}(\sin(20x) + \cos(20x)) | x > -10 | x < 10 | RED
```

${\begin{align} x_p &= \dfrac{(\omega_0^2 - \omega^2)F_0}{m(2\omega p)^2 + m(\omega_0^2 - \omega^2)^2}\cos(\omega t) + \dfrac{2\omega p F_0}{m(2\omega p)^2 + m (\omega_0^2 - \omega^2)^2}{\sin(\omega t)} \\ \\ &= \dfrac{F_0}{m\sqrt{(2\omega p)^2 + (\omega_0^2 - \omega^2)^2}}\cos(\omega t - \delta) \end{align}}$

Phase shift:
${\delta = \arctan(\dfrac{\omega p}{\omega_0^2 - \omega^2})}$

```desmos-graph
left=-5; right=10;
top=5; bottom=-5;
---
y = e^{-x}(\sin(20x) + \cos(20x)) + \sin(x) | x > -5 | x < 10 | RED
```


___

## TLDR:

### Undamped

For undamped cases (${c = 0}$)

If in the form:
$${mx'' + kx = F_0\cos(\omega t)}$$

Use: 
$${x = c_1\cos(\omega_0 t) + c_2\sin(\omega_0 t) + \dfrac{F_0}{m(\omega_0^2 - \omega^2)}\cos(\omega t)}$$

Graph:
```desmos-graph
left=-5; right=5;
top=4; bottom=-4;
---
y = \cos(x)+\sin(x)-2/(1*(1-4))\cos(3x) | x > -5 | x < 5 | RED
```


If in the form:
$${mx'' + kx = F_0\cos(\omega_0 t)}$$

It is a special case called **resonance**. As time goes on, the amplitude gets bigger and bigger and goes to infinity.

Use: 
$${x = c_1\cos(\omega_0 t) + c_2\sin(\omega_0t) + \dfrac{F_0t}{2m\omega_0}\sin(\omega_0t)}$$

Graph:
```desmos-graph
left=-40; right=40;
top=40; bottom=-40;
---
y = \cos(x)+\sin(x)-1/2x\sin(x) | x > -40 | x < 40 | RED
```

### Damped

If in the form:

$${mx'' + cx' + kx = F_0\cos(\omega t)}$$

The homogeneous solution ${x_h}$ is also called the **transient solution** ${x_{tr}}$

$${x_h = x_{tr} = e^{-pt} \cdot (\cos(\omega_1t) + c_2\sin(\omega_1t))}$$

Graph of transient/homogeneous solution looks like: 

```desmos-graph
left=-10; right=10;
top=5; bottom=-5;
---
y = e^{-1/5x}(\sin(20x) + \cos(20x)) | x > -10 | x < 10 | RED
```

And the particular solution (also called **steady solution**) looks like:
$${\begin{align} x_p &= \dfrac{(\omega_0^2 - \omega^2)F_0}{m(2\omega p)^2 + m(\omega_0^2 - \omega^2)^2}\cos(\omega t) + \dfrac{2\omega p F_0}{m(2\omega p)^2 + m (\omega_0^2 - \omega^2)^2}{\sin(\omega t)} \\ \\ &= \dfrac{F_0}{m\sqrt{(2\omega p)^2 + (\omega_0^2 - \omega^2)^2}}\cos(\omega t - \delta) \end{align}}$$

Where phase shift (${\delta}$):

${\delta = \arctan(\dfrac{2\omega p}{\omega_0^2 - \omega^2})}$

And ${x = x_{tr} + x_p}$

So, use:

$${x = e^{-pt} (c_1\cos(\omega_1t + c_2\sin(\omega_1 t)) + \dfrac{F_0}{m\sqrt{(2\omega p)^2 + (\omega_0^2 - \omega^2)^2}}\cos(\omega t - \delta)}$$

Graph:
```desmos-graph
left=-40; right=40;
top=40; bottom=-40;
---
y = \cos(x)+\sin(x)-1/2x\sin(x) | x > -40 | x < 40 | RED
```

___

>[!question] Example 1
>Suppose a spring with ${k = 4}$ N/m is attached to a mass of ${m = 1}$ kg and is driven by a force ${f(t) = 3\cos(t)}$. Assuming no friction, find ${x(t)}$.

>[!check]- Solution
${x'' + 4x = 3\cos(t)}$
>
${\implies \omega_0 = \sqrt{\frac{4}{1}} = 2}$
>
${x(t) = c_1\cos(2t) + c_2\sin(2t) + \dfrac{3}{4-1}\cos(t)}$

>[!question] Example 2
>Suppose a spring with ${k = 4}$ N/m is attached to a mass of ${m = 1}$ kg and is driven by a force ${f(t) = 2\cos(2t)}$. Assuming no friction, if ${x(0) = x'(0) = 0}$, how long will it take for ${x(t) = 10}$

>[!check]- Solution
>${\omega = \sqrt{\dfrac{k}{m}} = 2}$
>${x(t) = c_1\cos(2t) + c_2\sin(2t) + \dfrac{1}{2}t\sin(2t)}$
${x(0) = c_1 = 0}$
${x'(t) = -2\sin(2t) + c_2\cos(2t) + \dfrac{1}{2}(\sin(2t) + 2t\cos(2t))}$
${c_2 = 0}$
${x(t) = \dfrac{1}{2}t\sin(2t)}$
>
${20 = t\sin(2t)}$

${mx'' + cx' + kx = F_0 \cos(\omega t)}$
${x = x_h + x_p}$
${x_h = }$
${c_1e^{r_1t} + c_2e^{r_2t}}$, if ${c^2 > 4km}$
${c_1e^{-pt} + c_2te^{-pt}}$ if ${c^2 = 4km}$
${e^{-pt} (c_1\cos(\omega_1t) + c_2\sin(\omega_1t))}$ if ${c^2 < 4km}$

${x_p = \dfrac{F_0}{m\sqrt{(2\omega p)^2 + (\omega_0^2 - \omega^2)}}\cos(\omega t - \delta)}$

${\delta = \arctan\left(\dfrac{2\omega p}{\omega_0^2 - \omega^2}\right)}$

Find a particular solution to ${mx'' + cx' + kx = F_1\cos(\omega_1 t) + F_2\cos(\omega_2t)}$

${x_p = \underbrace{\dfrac{F_1}{m\sqrt{(2\omega_1p)^2 + (\omega^2-\omega_1^2)}}}_{\huge C(\omega)}\cos(\omega_1t - \delta_1) + \dfrac{F_2}{m\sqrt{(2\omega_2p)^2 + (\omega_0^2 - \omega_2^2)}}\cos(\omega_2t - \delta_2)}$

${\arctan\left(\dfrac{2\omega_1}{\omega_0^2 - \omega_1^2} p\right), \delta_2 = \arctan\left(\dfrac{2\omega p}{\omega_0^2 - \omega_2^2}\right)}$

${C'(w) = 0}$

Use quotient/product rule and cry.

${8\omega p^2 - 4\omega_0^2\omega + 4\omega^3 = 0}$
${\implies 2 \omega p^2 - \omega\omega_0^2 + \omega^3 = 0}$
${\implies \omega(2p^2 + \omega^2 - \omega_0^2) = 0}$

${\omega = 0, \sqrt{\omega_0^2 - 2p^2}}$
So, if ${\omega_0^2 - 2p^2 > 0}$

${C'(w) = \dfrac{-2\omega(2p^2 + \omega^2 - \omega_0^2)F_0}{(m((2\omega p)^2 + (\omega_0 - \omega^2)^2)^{\frac{3}{2}}}}$

If ${\omega_0^2 - 2p^2 > 0}$
${\sqrt{\omega_0^2 - 2p^2}}$ = practical resonance frequency
So, ${C(\sqrt{\omega_0^2 - 2p^2})}$

If ${\omega0^2 - 2p^2 \leq 0}$
No practical resonance exists

${\omega_0 = \sqrt{\dfrac{k}{m}}}$

${p = \dfrac{C}{2m}}$

${x'' + x' + x = \cos(\omega t)}$

${\omega_0^2 = 1}$

${p^2 = \dfrac{1}{4}}$

${\implies \omega_0^2 - 2p^2 = 1 - \dfrac{1}{2} = \dfrac{1}{2} > 0}$

>[!question] Example 4
>Find the practical resonance frequency and amplitude of ${x'' + x' + x = \cos(\omega t)}$.

>[!check]- Solution
>${\sqrt{\omega_0^2 - 2p^2} = \sqrt{\dfrac{1}{2}} = \omega_r}$
>${C(\omega_r) = \dfrac{F_0}{m\sqrt{(2\omega_rp)^2 + (\omega_0^2 - \omega_r^2)^2}} = \dfrac{1}{(2\cdot\sqrt{\dfrac{1}{2}} \cdot \dfrac{1}{2})^2 + (1-\sqrt{\dfrac{1}{2}}^2)^2} = \dfrac{2}{\sqrt{3}}}$
>Which is the practical resonance frequency.