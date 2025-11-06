*Lemma* A differentiable function ${f: D \to \mathbb{R}}$ is convex on ${D \iff}$ for all ${x,y \in D, f(y) \ge f(x) + (y-x)^T\nabla f(x)}$

*Lemma:* A twice continuously differentiable function ${f: D \to \mathbb{R}}$ is convex on ${D}$

*Example* show using all ${3}$ tests that ${f(x) = ||x^2||}$ on ${\mathbb{R}^n}$ is convex.
*Note:* ${f(x) = ||x^2|| = x_1^2 + x_2^2 + ... + x_n^2 = x^Tx}$
**Method 2:**
Let ${y = x+a}$
${\begin{align} f(y) = y^t y = (x+a)^T(x+a) = x^Tx + 2a^Tx + a^Ta\end{align}}$
${f(x) + (y-x)^T\nabla f(x) = x^Tx + a^T2x}$
>[!check]- Solve gradient
(We can solve ${\nabla f(x) = \begin{pmatrix} 2x_1 \\ 2x_2 \\ ...\\ 2x_n \end{pmatrix} = 2x}$)

${f(y) = x^Tx + 2a^Tx + a^Ta \ge x^Tx + 2a^Tx = f(x) + (y-x)^T\nabla f(x)}$

**Method 3:**
Solve Hessian

${\nabla^2f(x) = \begin{bmatrix} 2 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{bmatrix}}$

${\nabla^2f(x) \ge 0}$

*(A)* Determine whether or not the following subsets of ${\mathbb{R}^n}$ are convex.
1) ${S_1 = \{x \in \mathbb{R}^n\,|\,\max\{x_1,x_2,...,x_n\} \le 1}$
2) ${S_2 = \{ (3,4,0) \in \mathbb{R}^3\}}$
3) ${S_3 = \{x \in \mathbb{R}^n \,|\,x \ge 0\}}$
4) ${S_4 = \{(x,y) \in \mathbb{R}^2,|\,x^2+y^2 \le 1\}}$

*(B)* Determine whether or not the following functions are convex or not.
1) ${f_1(x) = x^2 \; (f: \mathbb{R} \to \mathbb{R})}$
2) ${f_2(x) = x^3\;(f:\mathbb{R}\to \mathbb{R})}$
3) ${f_3(x) = \frac{1}{x}\;(f:\;(0,\infty) \to \mathbb{R})}$
4) ${f_4(x) = c_tx + b\;(f: \mathbb{R}^n \to \mathbb{R}, c\in \mathbb{R}^n, b\in \mathbb{R})}$