Mathematical optimization is the study and practice of determining optimal decisions.

## **Linear Program**

A *linear program* (LP) is defined by linear objective, linear constraints, and real-valued decision variables

${\min x = c^Tx}$
such that ${Ax \le b}$
${A_ex = b_e}$
${x \in \Omega}$

## **Linear functions**
*Def* A function ${f: \mathbb{R}^n \to \mathbb{R}^m}$ is said to be linear if ${x,y \in \mathbb{R}^n}$ and all ${a \in \mathbb{R}}$

Maximize and minimize are the same thing, you can write it all as minimizing. To maximize, you minimize the negative.

## **Affine functions**

Standard form linear program is a minimization problem with non-negativity constraints on all decision variables and otherwise no inequality constraints. Furthermore, the rank of equality constraint coefficient matrix ${A}$ is equal to the number of equality constraints ${M}$.

## **Convex Sets in ${\mathbb{R}^n}$**
*Def* A set ${S \subseteq \mathbb{R}^n}$ is *convex* if and only if ${x, y \in S}$ and all ${0 \le \lambda \le 1}$, ${\lambda x + (1-\lambda )y \in S}$.

*Claim* The set ${S = \{x \in \mathbb{R}^n\,| \langle x, a \rangle \ge 0\}}$ is convex.

*Proof.* Let ${S = \{x \in \mathbb{R}^n\,| \langle x, a \rangle \ge 0\}}$ where ${a \in \mathbb{R}^n}$.

Suppose ${x,y \in S}$ and ${\lambda \le 0 \le 1}$. We need to show that ${\lambda x + (1-\lambda)y \in S}$.
${\langle \lambda x + (1-\lambda)y, a \rangle = \langle \lambda x, a\rangle + \langle (1-\lambda)y,a\rangle = \lambda \langle x,a \rangle + (1-\lambda) \langle y, a \rangle}$.

Because ${x,y \in S}$, ${\langle x,a \rangle \ge 0, \langle y,a \rangle \ge 0}$ and also ${\lambda \ge 0, 1 - \lambda \ge 0}$. So ${\langle \lambda x + (1-\lambda)y, a \rangle \ge 0}$ and the set is convex.

*Claim* The set ${S = \{(x,y) | x^2 + y^2 \le 1\}}$ is convex.
![[Mixed Integer Programming 2025-01-14 11.20.35.excalidraw]]
*(Proof Argument)*

Let ${(w,z) = \lambda (x,y) + (1-\lambda) (u,v)}$

Show ${w^2 + z^2 \le 1}$

${(\lambda x + (1-\lambda) u)^2 + (\lambda y + (1-\lambda)v)^2}$

${\lambda^2 (x^2 + y^2) + (1-\lambda)^2(u^2+v^2) + 2\lambda(1-\lambda)(xu + yv) }$

${\le \lambda^2 + (1-\lambda)^2 + 2\lambda(1-\lambda) = (\lambda + (1-\lambda))^2 = 1}$

Therefore, ${w^2 + z^2 \le 1}$ and thus ${w,z}$ is in the set.

___

What about ${S = \mathbb{R}^n?}$
Is ${S}$ convex?

Yes.

What about ${S = \phi}$
Is ${S}$ convex?
Yes.

A convex set can be both open or closed.

**Convex Functions on ${\mathbb{R}}$**

*Def* A function ${f: D \to \mathbb{R}}$ is *convex* if and only if ${D}$ is convex and for all ${x,y \ in D}$ and all ${0 \le \lambda \le 1}$, ${f(\lambda x + (1-\lambda)y) \le \lambda f(x) + (1-\lambda) f(y)}$

Example: ${f(x) = x^2}$

*Lemma* A differentiable function ${f : D \to \mathbb{R}}$ is convex on ${D}$ if and only if for all ${x,y \in D}$, ${f(y) \ge f(x) + (y-x)^T\nabla f(x)}$

${D \subseteq \mathbb{R}^n}$
![[Mixed Integer Programming 2025-01-14 11.45.46.excalidraw]]

${f(y) \ge f(x) + (y-x) f'(x)}$

A function is convex when it lies above its tangent line/plane everywhere

___