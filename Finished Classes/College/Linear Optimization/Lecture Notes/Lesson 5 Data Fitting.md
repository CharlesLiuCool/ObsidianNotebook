**Exercise 1.8** (Road lighting) Consider a road divided into ${n}$ segments that is illuminated by ${m}$ lamps. Let ${p_j}$ be the power of the ${j}$th lamp. The illumination ${I_i}$ of the ${i}$th segment is assumed to be ${\sum\limits_{j=1}^{m}a_{ij}p_{j}}$, where ${a_{ij}}$ are known coefficients.

Let ${I_i^{*}}$ be the desired illumination of road ${i}$.
We are interested in choosing the lamp powers ${p_j}$ so that the illuminations ${I_i}$ are close to the desired illuminations ${I_i^{*}}$. Provide a reasonable linear programming formulation of this problem. Note that the wording of the problem is loose and there is more than one possible formulation.

![[Lesson 5 2025-01-23 10.41.46.excalidraw]]

${I_i = a_{i1}p_1 + a_{i2}p_2 + ... + a_{im}p_m}$
${i = 1,2,...n}$

${I = AP}$
${I = n \times 1}$
${A = n \times m}$
${P = m \times 1}$

${\min z = ||I - I^*||}$
${s.t.}$
${P \in \mathbb{R}^m}$
${I \in \mathbb{R}^n}$

${\min z = ||AP - I^*||}$
${s.t. P \in \mathbb{R}^m}$

*Try Euclidian norm:*
${\min z = \sum\limits_{i=1}^n (I_i - I_i)^2}$

It's not linear though...

*Try the 1-norm:*
Least Deviation
${\min z = \sum\limits_{i=1}^n | I_i - I_i^*|}$

${\text{s.t. }I = AP}$
${P \in \mathbb{R}^m}$
${I \in \mathbb{R}^n}$

${\min z = \sum\limits_{i=1}^n \delta_i}$

${\text{s.t. }I = AP}$

${\delta_i \ge I_i - I_i^*}$
${\delta_i \le -I_i + I_i^*}$
${i = 1,2,...n}$
${P \in \mathbb{R}^m}$
${I \in \mathbb{R}^n, \delta \in \mathbb{R}^n}$
${\delta \ge 0}$

Try the ${\infty\text{-norm}}$

${\min z = \max\limits_i\{|I_i-I_i^*|\}}$
${\text{s.t.} I = AP}$

${P \in \mathbb{R}^m, I \in \mathbb{R}^n}$

___

### Least Squares and Least Deviation Data Fitting

*DATA:* ${\{(x_k, y_k)\}_{k=1}^m}$

*EXPECTATION:* ${y \approx a_2x^2 + a_1x + a_0}$ for some ${a_2, a_1, a_0}$.
(data model)

The expression ${a_2x^2 + a_1x + a_0}$ is linear to ${a_2, a_1, a_0}$.

Approach: ${y_k \approx a_2x_k^2 + a_1x_k + a_0}$ for each ${k}$

![[Lesson 5 2025-01-23 11.07.31.excalidraw|600]]

Want: ${|y_k - (a_2x_k^2 + a_1x_k + a_0)|}$ to be small for all ${k}$.

___

### Least Squares Approach

${\min z = f(a) = \sum\limits_{k=1}^m (y_k - a_2x_k^2 - a_1x_k - a_0)^2}$
${s.t. a \in \mathbb{R}^3}$

minimize ${v}$ is solution to ${\nabla_af = 0}$.

${\nabla_a f = \begin{pmatrix} \frac{\partial f}{\partial a_2} \\ \frac{\partial f}{\partial a_1} \\ \frac{\partial f}{\partial a_0} \end{pmatrix}}$

= ${\begin{pmatrix} \sum\limits_{k=1}^m (-2x_k^2) (y_k-a_2x_k^2 - a_1x_k - a_0) \\ \sum\limits_{k=1}^m (-2x_k) (y_k-a_2x_k^2 - a_1x_k - a_0) \\ \sum\limits_{k=1}^m (-2) (y_k-a_2x_k^2 - a_1x_k - a_0) \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}}$

${-a_2\sum x_k^4 - a_1 \sum x_k^3 - a_0 \sum x_k^2 = -\sum x_k^2 y_k}$
${-a_2\sum x_k^3 - a_1 \sum x_k^2 - a_0 \sum x_k = -\sum x_k y_k}$
${-a_2\sum x_k^2 - a_1 \sum x_k - a_0 \sum 1 = -\sum y_k}$

${\begin{pmatrix} \sum x_k^4 & \sum x_k^3 & \sum x_k^2 \\ \sum x_k^3 & \sum x_k^2 & \sum x_k \\ \sum x_k^2 & \sum x_k & \sum 1 \end{pmatrix} \begin{pmatrix} a_2 \\ a_1 \\ a_0 \end{pmatrix} = \begin{pmatrix} \sum x_k^2 y_k \\ \sum x_k y_k \\ \sum y_k \end{pmatrix}}$

${ua = v}$
${a = u^{-1}v}$

___

### Least Deviation Approach

${\min z = f(a) = \sum\limits_{k=1}^m |y_k - a_2x_k^2 - a_1x_k - a_0|}$
${\text{s.t.} a \in \mathbb{R}^3}$

${\min z = \sum\limits_{k=1}^m \delta_k}$
${\text{s.t. }\delta_k \ge y_k - a_2x_k^2 - a_1x_k - a_0}$
${\delta_k \ge -y_k + a_2x_k^2 + a_1x_k + a_0}$

${a \in \mathbb{R}^3}$
${\delta \in \mathbb{R}^m}$

${\min z = 0a_2 + 0a_1 + 0a_0 + \delta_1 + \delta_2  + ... + \delta_m}$
${\text{s.t. } (-x_k^2)a^2 + (-x_k)a_1  -a_0 - \delta_k \le -y_k}$
${x_2a_2 + x_ka_1 + a_0 - \delta{k} \le y_k}$
${k = 1,2,...,m}$
${a \in \mathbb{R}^3, \delta \in \mathbb{R}^m}$

Let ${0_3 = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}}$


${1_m = \begin{pmatrix} 1 \\ 1 \\ . \\ . \\ . \\ 1\end{pmatrix},\;}$ ${x = \begin{pmatrix} x_1 \\ . \\ . \\ . \\ x_m\end{pmatrix},\;}$${y = \begin{pmatrix} y_1 \\ . \\ . \\ . \\ y_m \end{pmatrix},\;}$${x_2 = \begin{pmatrix} x_1^2 \\ . \\ . \\ . \\ x_m^2\end{pmatrix},\;}$ ${w = \begin{pmatrix} a_2 \\ a_1 \\ a_0 \\ \delta_1 \\ . \\ . \\ \delta_m \end{pmatrix}}$

${\min z = c^Tw}$
${\text{s.t.}\;Aw \le b}$
${w \in \mathbb{R}^{m+}}$

${c = \begin{pmatrix} 0_3 \\ 1_m \end{pmatrix}}$

${A = \begin{pmatrix} -x_2 & -x & - 1_m & -I_m \\ x_2 & x & 1_m & -I_m \end{pmatrix}}$

${b = \begin{pmatrix} -y \\ y \end{pmatrix}}$

___

### What Class of Model Functions is Accessible to Linear Programming?

Can I choose any function for least deviation fitting?

Previous example
*(1)* ${y = a_2x^2 + a_1x + a_0}$
The ${CO_2}$ example (reading)
*(2)* ${y = a_0 + a_1x + a_2x^2 + a_3\sin(2\pi x) + ay\cos(2\pi x)}$

These examples are of the form: ${y = \sum\limits_{k=0}^P a_k\phi_k (x)}$
Where ${\phi_k (x)}$ are given fixed functions.

*(1)*
${\phi_0 (x) = 1}$
${\phi_1 (x) = x}$
${\phi_2 (x) = x^2}$

*(2)*
${\phi_0 (x) = 1}$
${\phi_1(x) = x}$
${\phi_2(x) = x^2}$
${\phi_3(x) = \sin(2\pi x)}$
${\phi_4(x) = \cos(2\pi x)}$

No matter how nonlinear something is, as long as you can write it as a linear combination.

They key properties are
*(a)* ${y}$ is linear in each ${a_k}$
*(b)* Each ${\phi_k(x)}$ is a function

___

**The Least Squares General Result**

Let ${\Phi_{ij} = \sum\limits_{k=1}^m \phi_i(x_k) \phi_j(x_k)}$

and ${\Theta_i = \sum\limits_{k=1}^m \phi_i(x_k) y_k}$

${\Phi a = \Theta}$ (matrix equation)

If ${\Phi}$ is invertible, then
${a = \Phi^{-1} \Theta}$

If ${\Phi}$ is *not* invertible, then
${a = P \Theta}$, ${P}$ is pseudoinverse of ${\Phi}$

${\Phi a = \Theta}$ in MATLAB, ${a = \Phi \backslash \Theta}$

___