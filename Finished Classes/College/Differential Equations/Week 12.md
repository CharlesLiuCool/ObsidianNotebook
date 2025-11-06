### Solving Constant Coefficient Linear Systems of ODEs

Suppose you have the ODE system

${x'(t) = Ax(t)}$

then if ${A}$ is *NOT* defective

${x(t) = c_1\vec{v}_1e^{\lambda_1t} + c_2\vec{v}_2e^{\lambda_2t}+...+c_n\vec{v}_ne^{\lambda_nt}}$

>[!question] Example 1

${x_1' = - 5x_1 + 2x_2}$
${x_2' = -7x_1+4x_2}$

${\vec{x}(t) = \begin{pmatrix} x_1(t) \\ x_2(t) \end{pmatrix}}$

${\vec{x}'(t) = }$

>[!question] Example 1
>
${x_1' = x_1+x_2}$
${x_2' = x_1 - x_2}$

>[!check]-
${A = \begin{bmatrix} 1 & 1 \\ 1 & -1\end{bmatrix}}$
>
${\lambda = \pm \sqrt{2}}$

| ${\lambda}$            | Behavior                 |
| -------------------------- | ------------------------ |
| both positive              | source                   |
| both negative              | sink                     |
| one positive one negative  | saddle                   |
| strictly imaginary         | ellipses/centers         |
| complex with positive real | spiral out/spiral source |
| complex with negative real | spiral in/spiral sink    |

>[!question] Example 2
> Classify the behavior of the system of ODEs below
> 
> ${x_1' = 3x_1 + 2x_2}$
> ${x_2' = -2x_1 + 3x_2}$

>[!check]- Solution
>${\vec{x}' = \begin{pmatrix} 3 & 2 \\ -2 & 3\end{pmatrix}\vec{x}}$
>
>${\det\begin{pmatrix} 3-\lambda & 2 \\ -2 & 3-\lambda \end{pmatrix} = (3-\lambda)^2 + 4 = 0}$
>
>${(3-\lambda)^2 = -4}$
>${3-\lambda = \pm \sqrt{-4} = \pm 2i}$
>${3 \pm 2i}$
>Spiral Source
