### Laplace Transform

${\mathcal{L}\{e^{at} f(t)\} = F(s + a)}$

${\int_0^\infty e^{-st}e^{at}f(t)dt = \int_0^\infty e^{at-st}f(t)dt}$

${t \xrightarrow u-a}$
${dt \xrightarrow du}$

${\int_a^\infty {e^{a(u-a) - s(u-a)}f(u-a)du}}$


>[!question] Example 1
${\mathcal{L}\{e^{3t}\cdot t^2\}}$

>[!check]- Solution
>${\dfrac{2!}{(5+3)^3}}$

>[!question] Example 2
> ${\mathcal{L}\{e^{2t}\sin(4t)}$

> [!check]- Solution
> ${\dfrac{w}{(s+2)^2 + w^2}\}}$

>[!question] Example 3
>${\mathcal{L}\{2e^{2t} + 3e^{2t}t^6 \}}$

>[!check]- Solution
>${= 2\mathcal{L}\{e^{2t}\} + 3\mathcal{L}\{e^{2t}t^6\} = \dfrac{2}{s-2} + 3 \dfrac{6!}{(s+2)^7}}$

### Inverse Laplace Transform

Finding ${\mathcal{L}^{-1} \{F(s)\}}$:

Try to turn a ${F(s)}$ into a linear combination of known Laplace results.

>[!question] Example 6
>
Find ${\mathcal{L}^{-1} \{\dfrac{3}{s^2} + \dfrac{7}{s^4}\}}$

>[!check]- Solution
> ${= \mathcal{L}^{-1} \{\dfrac{3}{s^2}\}  + \mathcal{L}\{\dfrac{7}{s^4}\}}$
> ${= 3\mathcal{L}^{-1}\{\dfrac{1}{s^2}\} + \dfrac{7}{3!} \mathcal{L}^{-1}\{\dfrac{3!}{s^4}\}}$
> ${= 3t + \dfrac{7}{6}t^3}$

>[!question] Example 7
${\mathcal{L}\left\{\dfrac{2s + 1}{s(s^2+4)}\right\}}$

>[!check]- Solution
>${\dfrac{2(s+1)}{s(s^2+4)} = \dfrac{1}{4s} + \dfrac{s}{4(s^2+4)} + \dfrac{2}{s^2+4}}$
>
>${\dfrac{1}{4} - \dfrac{1}{4}\cos(2t) + \sin(2t)}$

___

${u(t-2)t^2}$

Recall: ${u(t-a) = }$
${1}$ if ${t \geq a}$
${0}$ if ${t < a}$

Claim
${\mathcal{L}\{u(t-a)(f(t-a)\} = e^{-as}F(s)}$

Suppose

${\mathcal{L}\{f(t)\} = F(s)}$
${\mathcal{L\{f'(t)\}} = \int_0^{\infty}e^{-st}f'(t)dt}$

>[!question] Example
>Solve ${y''+2y'-3y = e^{4t}}$
>${y(0)=y'(0) = 0}$

>[!check]- Solution
>${s^2F(s) - sf(0) - f'(0) + 2(sF(s)-f(0)) - 3F(s) = \dfrac{1}{s-4}}$
>${s^2F(s)+2sF(s)-3F(s) = \dfrac{1}{s-4}}$
>${Y(t) = \dfrac{1}{21}e^{4t} + \dfrac{1}{28}e^{-3t}-\dfrac{1}{12}e^t}$