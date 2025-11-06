**2.5.7**
- a) Using variation of parameters find a particular solution of .${y'' - 2y' + y = e^x}$
${y_h'' - 2y_h' + y_h = 0}$
${y = e^rx}$
${r^2 - 2r + 1 = 0}$
${(r-1)^2}$
${r = 1\,m\,2}$
${y_h = c_1e^{x} + c_2xe^{x}}$

${y_p =  e^{x}\int\dfrac{-xe^{x}e^{x}}{W(y_1,y_2)} + xe^{x} \int \dfrac{e^{x}e^{x}}{W(y_1,y_2)}dx}$

${W(y_1,y_2) = y_1y_2' - y_1'y_2 = e^x \cdot (e^x + xe^{x}) - e^x(xe^x) = e^{2x}}$

${e^{x} \int -x dx + xe^{x}\int 1dx = e^{x} (-\dfrac{x^2}{2}) + x^2e^x = \dfrac{x^2}{2}e^x}$

- b) Find a particular solution using undetermined coefficients.
${y_p = Ax^2e^{x}}$
${y_p' = A(2xe^{x} + x^2e^{x}) = 2Axe^{x} + Ax^2e^{x}}$
${y_p'' = A(2e^{x} + 2xe^{x} + 2xe^{x} + x^2e^{x}) = 2Ae^{x} + 4Axe^{x} + Ax^2e^{x}}$

${2Ae^{x} + 4Axe^{x} + Ax^2e^{x} - 2(2Axe^{x} + Ax^2e^{x}) + Ax^2e^{x} = e^x}$
${2Ae^{x} + 4Axe^{x} + Ax^2e^{x}v -4Axe^x - 2Ax^2e^x + Ax^2e^x = 2Ae^x = 1}$
${\implies A = \dfrac{1}{2}}$
${y_p = \dfrac{1}{2}e^x}$

- c) Are the two solutions you found the same? 
Yes, they are the same.


**2.5.104**
Use variation of parameters to find particular solution of ${y'' - y = \dfrac{1}{e^x + e^{-x}}}$

${y_h'' - y_h = 0}$
${y_h = e^{rx}}$
${r^2 - 1 = 0}$
${r = \pm 1}$

${y_h = c_1e^x + c_2e^{-x}}$

${y = e^{x} \int \dfrac{\frac{-e^{-x}}{e^x + e^{-x}}}{W(y_1,y_2)}dx + e^{-x}\int \dfrac{\frac{e^x}{e^x + e^{-x}}}{W(y_1,y_2)}dx}$

${W(y_1,y_2) = -e^{-x}e^{x} - e^{x}e^{-x} = -1 - 1 = -2}$

${y = \dfrac{e^{x}}{2} \int \dfrac{e^{-x}}{e^x + e^{-x}}dx + \dfrac{e^{-x}}{-2}\int \dfrac{e^x}{e^x + e^{-x}}dx}$

${\dfrac{e^{-x}}{2}\int \dfrac{e^{-2x}}{e^{-2x} + 1}dx + \dfrac{e^{-x}}{-2} \int \dfrac{e^{2x}}{e^{2x} + 1}dx}$

${u = e^{-2x} + 1}$
${du = -2e^{-2x} + 1}$
${v = e^{2x} + 1}$
${dv = 2e^{2x} + 1}$

${-\dfrac{e^{-x}}{4} \int \dfrac{1}{u} du -  \dfrac{e^{-x}}{4} \int \dfrac{1}{v} dv}$
${-\dfrac{e^{-x}}{4} \ln|u| - \dfrac{e^{-x}}{4} \ln|v| =}$
${ y_p = -\dfrac{e^{-x}}{4}\ln|e^{-2x} + 1| - \dfrac{e^{-x}}{4} \ln|e^{2x} + 1|}$

**2.4.2**
Consider a mass and spring system with a mass ${m = 2}$, spring constant ${k = 3}$, and damping constant ${c = 1}$.

1. Set up and find the general solution of the system.

${2x'' + x' + 3x = F_0\cos(\omega t)}$

${x = x_h + x_p}$
${c^2 = 1 < 4km = 24}$

So,
${x_h = e^{-pt} (c_1\cos(\omega_1 t) + c_2\sin(\omega_2t))}$

Where ${p = \dfrac{1}{4}}$

And,
${x_p = \dfrac{F_0\cos(\omega t - \delta)}{2\sqrt{(\frac{1}{2}\omega)^2 + (\omega_0^2 - \omega^2)^2}}}$

Where ${\delta = \arctan\left(\dfrac{\frac{1}{2}\omega}{w_0^2 - w^2}\right)}$
${x = e^{-\frac{1}{4}t} (c_1\cos(\omega_1 t) + c_2\sin(\omega_2t)) + \dfrac{F_0\cos\left(\omega t - \arctan\left(\dfrac{\frac{1}{2}\omega}{w_0^2 - w^2}\right)\right)}{2\sqrt{(\frac{1}{2}\omega)^2 + (\omega_0^2 - \omega^2)^2}}}$

3. Is the system underdamped, overdamped or critically damped?
Underdamped
3. If the system is not critically damped, find a ${c}$ that makes the system critically damped.
${c^2 = 24 \implies c = \sqrt{24}}$

**2.4.6**
Suppose you wish to measure the friction a mass of ${0.1}$ kg experiences as it slides along a floor (you wish to find ${c}$). You have a spring with spring constant ${k = 5 \frac{N}{m}}$. You take the spring, you attach it to the mass and fix it to a wall. Then you pull on the spring and let the mass go. You find that the mass oscillates with frequency 1 Hz. What is the friction?

${\omega = 2\pi f}$
${f = 1 Hz}$

${0.1x'' + cx' + 5x = F_0\cos(2\pi t)}$
${0.1x'' + cx' + 5x = 0}$

${\omega_0 = \sqrt{\dfrac{k}{m}} = \sqrt{50}}$

${\omega_1 = \sqrt{\omega_0^2 - p^2}}$

${p = \dfrac{c}{2m} = \dfrac{c}{0.2}}$

${\implies 2\pi = \sqrt{50 - \left(\dfrac{c}{0.2}\right)^2} \implies 16\pi^2 = 50 - \left(\dfrac{c}{0.2}\right)^2 }$

${\implies \left(\dfrac{c}{0.2}\right)^2 = 50 - 16\pi^2 \implies \left(\dfrac{c}{0.2}\right)^2 = \sqrt{50-16\pi^2}}$

${\implies c = 0.2 \sqrt{50 - 16\pi^2}}$


**2.6.2** 
Derive a formula for ${x_{sp}}$ if the equation is ${mx'' + cx' + kx = F_0\cos(\omega t) + F_1\cos(3\omega t)}$. Assume ${c > 0}$

${x_p = x_sp}$

${x_p = x_p (F_0) + x_p (F_1)}$

${x_p (F_0) = \dfrac{F_0\cos(\omega t - \delta)}{m\sqrt{(2\omega p)^2 + (\omega_0^2 - \omega^2)}}}$

${x_p (F_1) = \dfrac{F_1\cos(3\omega t - \delta)}{m\sqrt{(6\omega p)^2 + (\omega_0^2 - 3\omega^2)}}}$

So,

${x_p = \dfrac{F_0\cos(\omega t - \delta)}{m\sqrt{(2\omega p)^2 + (\omega_0^2 - \omega^2)}} + \dfrac{F_1\cos(3\omega t - \delta)}{m\sqrt{(6\omega p)^2 + (\omega_0^2 - 3\omega^2)}}}$

where ${p = \dfrac{c}{2m},\;\delta_0 = \arctan\left(\dfrac{2\omega p}{\omega_0^2-\omega^2}\right),\;\delta_1 = \arctan\left(\dfrac{6\omega p}{\omega_0^2 - 9\omega^2}\right), \omega_0 =\;\sqrt{\dfrac{k}{m}}}$