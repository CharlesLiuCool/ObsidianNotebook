6.1.101, 6.2.6, 6.2.11, 6.3.1, 6.3.3

>[!question] 6.1.101
> Find the Laplace transform of ${4(t+1)^2}$.

${4(t+1)^2 = 4(t^2 + 2t + 1) = 4t^2 + 8t + 4 = \frac{8}{s^3} + \frac{8}{s^2} + \frac{4}{s}}$

>[!question] 6.2.6
>Solve ${x'' + x = u(t-1)}$ for initial conditions ${x(0) = 0}$ and ${x'(0) = 0}$

${\mathcal{L}\{x'' + x\} = \mathcal{L}\{x''\} + \mathcal{L}\{x\} = s^2X(s) - sx(0) - x'(0) + X(s)}$

${= \mathcal{L}\{u(t-1)\} = \frac{e^{-s}}{s}}$

So for ${x(0) = 0}$ and ${x'(0) = 0}$

${s^2X(s) - s \cdot 0 - 0 + X(s) = (s^2 + 1)X(s) = \frac{e^{-s}}{s}}$

${\implies X(s) = \frac {e^{-s}}{s^3}}$

${\mathcal{L}^{-1} \{X(s)\} = \mathcal{L}^{-1}\{\frac{e^{-s}}{s^3}\} = \mathcal{L}^{-1}\{e^{-s} \mathcal{L}\{\frac {1}{s} + \frac{-s}{s^2+1}\}\}}$

${= \mathcal{L}^{-1} \{e^{-s} (1 + \cos(t)\} = u(t-1)(1 + \cos(t - 1))}$

>[!question] 6.2.11
>Define
>${ f(t) = \begin{cases} (t-1)^2 & \text{if}\;1 \le t < 2 \\ 3-t &  \text{if} \;2 \le 3 \\ 0 & \text{otherwise} \end{cases}}$
>
>a) Sketch the graph of ${f(t)}$
>b) Write down ${f(t)}$ using the Heaviside function.
>c) Solve ${x'' + x = f(t), x(0) = 0, x'(0) = 0}$ using Laplace transform.

>[!check]- Solution
>a) ![[HW 9 2024-10-25 13.37.20.excalidraw]]
>b) ${u(t-1)}
>c) ${s^2X(s) +x(0) = \mathcal{L}\{u()\}}$

>[!question] 6.3.1
>Let ${f(t) = t^2}$ for ${t \ge 0}$ and ${g(t) = u(t-1)}$. Compute ${f * g}$ 

${\mathcal{L}\{t^2u(t-1)\} = \mathcal{L}\{t^2\} \cdot \mathcal{L}\{u(t-1)\} = \frac{2}{s^3} \cdot \frac{e^{-s}}{s} = \frac{2e^{-s}}{s^4}}$

${\mathcal{L}^{-1}\{\}}$