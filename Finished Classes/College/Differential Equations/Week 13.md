### Applications of Second Order Constant Coefficient Linear Systems

#### Spring Systems

${mx'' + cx' + kx = f(x)}$

${c =0 \implies}$ undamped

${f(x) = 0 \implies}$ unforced

${M\vec{x}'' = Kx}$

${M}$ = mass matrix

${K}$ = stiffness matrix

${x = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}}$

${M = \begin{bmatrix} m_1 & 0 & 0 \\ 0 & m_2 & 0 \\ 0 & 0 & m_3 \end{bmatrix}}$

${K = \begin{bmatrix} -k_1-k_2 & k_2 & 0 \\ k_2 & -k_2-k_3 & k_3 \\ 0 & k_3 & -k_3-k_4 \end{bmatrix}}$

${M^{-1} = \begin{bmatrix} \frac{1}{m_1} & 0 & 0 \\ 0 & \frac{1}{m_2} & 0 \\ 0 & 0 & \frac{1}{m_1} \end{bmatrix}}$

${\vec{x}'' = M^{-1}k\vec{x}}$

${\vec{x}'' =  \begin{bmatrix} \frac{1}{m_1} & 0 & 0 \\ 0 & \frac{1}{m_2} & 0 \\ 0 & 0 & \frac{1}{m_1} \end{bmatrix} \begin{bmatrix} -k_1-k_2 & k_2 & 0 \\ k_2 & -k_2-k_3 & k_3 \\ 0 & k_3 & -k_3-k_4 \end{bmatrix}}$

${\vec{x}'' = A\vec{x}}$
"Guess"

${\vec{x} = \vec{v}e^{at}}$

${a^2 \vec{v}e^{at} = A\vec{v}e^{at}}$