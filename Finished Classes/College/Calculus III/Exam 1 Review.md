---
tags: MATH_273 Calculus_III
---

1. Suppose ${\mathbf{v} = 3\mathbf{i} - \mathbf{j} + 2\mathbf{k}}$ and ${\mathbf{w} = 5\mathbf{i} + 4\mathbf{j} - \mathbf{k}}$.
	**a)** Use the dot product to determine whether the angle between ${\mathbf{v}}$ and ${\mathbf{w}}$ is acute or obtuse.
		${\mathbf{v} \cdot \mathbf{w} = \langle 3, -1, 2 \rangle \cdot \langle 5, 4, -1\rangle = 3 \cdot 5 - 1 \cdot 4 + 2 \cdot (-1) = 15 - 4 - 2 = 9}$
		Since ${9 > 0}$, the angle is **acute**.
		
	**b)** Find a vector that is perpendicular to both ${\mathbf{v}}$ and ${\mathbf{w}}$.
		Use cross product
		
		${\begin{align} &\mathbf{v} \times \mathbf{w} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 3 & -1 & 2 \\ 5 & 4 & -1 \end{vmatrix} = \mathbf{i} \cdot \begin{vmatrix} -1 & 2 \\ 4 & -1 \end{vmatrix} - \mathbf{j} \cdot \begin{vmatrix} 3 & 2 \\ 5 & -1 \end{vmatrix} + \mathbf{k} \cdot \begin{vmatrix} 3 & -1 \\ 5 & 4 \end{vmatrix} \\ \\ &= \mathbf{i} \cdot ((-1) \cdot (-1) - 2 \cdot 4) - \mathbf{j} \cdot (3 \cdot (-1) - 2 \cdot 5) + \mathbf{k} \cdot (3 \cdot 4 - (-1) \cdot 5) \\ &= \langle 1, 0, 0 \rangle \cdot (-7) - \langle 0, 1, 0 \rangle \cdot (-13) + \langle 0, 0, 1 \rangle \cdot 17 = \color{magenta} \langle -7, 13, 17 \rangle\end{align}}$
	.

2. **a)** Find a vector equation for the line through the points ${(3, 2, 1)}$ and ${(5, -1, 7)}$.
	${\mathbf{r}_0 = \langle 3,2,1\rangle}$
	${\mathbf{v} = \langle 5, -1, 7 \rangle - \langle 3, 2, 1\rangle = \langle 2, -3, 6\rangle}$
	${\color{magenta} \mathbf{r}(t) = \mathbf{r}_0 + t \cdot \mathbf{v} = \langle 3, 2, 1 \rangle + t \langle 2, -3, 6 \rangle}$
	
	**b)** Find an equation for the plane which contains ${(-4, 1, 0)}$ and is orthogonal to the line ${x = 3 + t}$, ${y = -4 - 2t}$, ${z = 5t}$.
	normal direction vector ${ = \langle 1, -2, 5 \rangle}$
	${x - 2y + 5z = D}$
	${-4 - 2 \cdot 1 + 5 \cdot 0 = -4 -2 + 0 = -6 = D}$
	${\color{magenta} x - 2y + 5z = -6}$
    .
3. Given the space curve ${\mathbf{r}(t) = \langle \sin(\pi t), 4 - \dfrac{1}{2}t^2, \cos(\pi t) \rangle}$, ${t \geq 0}$:
	**a)** If this curve represents the position of a particle in space (with time in seconds and position coordinates in meters), find the *velocity*, *speed*, and *acceleration functions* for the particle. Also, find the velocity, speed, and acceleration at time ${\color{magenta} t = 3}$.
	${\mathbf{v}(t) = \mathbf{r}'(t) = \color{magenta} \langle \pi\cos(\pi t), -t, -\pi \sin(\pi t) \rangle}$
	
	${\begin{align}\mathbf{s}(t) &= |\mathbf{v}(t)| = \sqrt{(\pi\cos(\pi t))^2 + (-t)^2 + (-\pi \sin(\pi t)^2)} \\ &= \sqrt{\pi^2\cos^2(\pi t) + t^2 + \pi^2 \sin^2(\pi t)} = \sqrt{\pi^2(\cos^2(\pi t) + \sin^2(\pi t)) + t^2} \\ &= \color{magenta} \sqrt{\pi^2 + t^2}\end{align}}$ 
	**Recall speed is scalar!**
	
	${\mathbf{a}(t) = \mathbf{v}'(t) = \color{magenta} \langle -\pi^2 \sin(\pi t), -1, -\pi^2 \cos(\pi t) \rangle}$
	
	${\mathbf{v}(3) = \langle \pi\cos(3\pi), -3, -\pi \sin(3\pi) \rangle = \color{magenta} \langle -\pi, -3, 0 \rangle}$
	
	${\mathbf{s}(3) = \sqrt{\pi^2 + 3^2} = \color{magenta} \sqrt{\pi^2 + 9}}$
	
	${\mathbf{a}(3) = \langle -\pi^2 \sin(3\pi), -1, -\pi^2 \cos(3\pi) \rangle = \color{magenta} \langle 0, -1, \pi^2 \rangle}$
	
	**b)** Find the unit tangent vector ${\mathbf{T}(t)}$.
	
	${\begin{align} \mathbf{T}(t) &= \dfrac{\mathbf{r}'(t)}{|\mathbf{r}'(t)}| = \dfrac{\mathbf{v}(t)}{\mathbf{s}(t)} = \dfrac{\langle \pi\cos(\pi t), -t, -\pi \sin(\pi t) \rangle}{\sqrt{\pi^2 + t^2}} \\ \\ &= \color{magenta} \left\langle \dfrac{\pi\cos(\pi t)}{\sqrt{\pi^2 + t^2}}, -\dfrac{t}{\sqrt{\pi^2 + t^2}}, -\dfrac{\pi \sin(\pi t)}{\sqrt{\pi^2 + t^2}} \right\rangle\end{align}}$
	
	**c)** Find parametric equations for the line that is tangent to this curve at the point ${(0, 2, 1)}$.
	
	${\langle 0,2,1 \rangle = \langle \sin(\pi t), 4 - \dfrac{1}{2}t^2, \cos(\pi t) \rangle \implies 2 = 4 - \dfrac{1}{2}t^2 \implies t = \pm 2}$
	${t = 2}$ since ${t \geq 0}$
	
	${\mathbf{r}'(2) = \langle \pi\cos(2\pi), -2, -\pi \sin(2\pi) \rangle = \langle \pi, -2, 0 \rangle}$
	So, ${\color{magenta} x = \pi t, y = -2t + 2, z = 1}$
	
	**d)** Graph the curve for ${0 \leq t \leq 2}$. Indicate positive orientation, and label the points at ${t = 0}$, ${t = 1}$, and ${t = 2}$ with their coordinates.
	![[Exam 1 Review Graphic|800]]
    
4. For the curve ${\mathbf{r}(t) = t^2\mathbf{i} + (1 - t^2)\mathbf{j} + (2 + t^3)\mathbf{k}}$:
	**a)** Find expressions for the tangential acceleration, normal acceleration, and curvature at any ${t}$ value.
	${\mathbf{r}'(t) = 2t\mathbf{i} -2t\mathbf{j} + 3t^2 \mathbf{k}}$
	${\mathbf{r}''(t) = 2\mathbf{i} -2\mathbf{j} + 6t\mathbf{k}}$
	${|\mathbf{r}'(t)| = \sqrt{(2t)^2 + (2t)^2 + ((3t)^2)^2} = \sqrt{8t^2 + 9t^4} = t\sqrt{8 + 9t^2}}$
	
	${\begin{align} a_T &= \dfrac{\mathbf{r}'(t) \cdot \mathbf{r}''(t)}{|\mathbf{r}'(t)|} = \dfrac{2t \cdot 2 - 2t \cdot (-2) + 3t^2 \cdot 6t}{8t^2 + 9t^4} = \dfrac{4t + 4t + 18t^3}{t\sqrt{8 + 9t^2}} \\ \\ &= \color{magenta} \dfrac{8 + 18t^2}{\sqrt{8 + 9t^2}} \end{align}}$
	
	${\mathbf{r}'(t) \times \mathbf{r''}(t) = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 2t & -2t & 3t^2 \\ 2 & -2 & 6t \end{vmatrix} = \langle -6t^2, -6t^2, 0 \rangle}$
	
	${|\mathbf{r}'(t) \times \mathbf{r''}(t)| = |\langle -6t^2, -6t^2, 0 \rangle| = \sqrt{36t^4 + 36t^4} = 6t^2\sqrt{2}}$
	
	${\begin{align} a_N = \dfrac{|\mathbf{r}'(t) \times \mathbf{r''}(t)|}{|\mathbf{r}(t)|} = \dfrac{6\sqrt{2}t^2}{t\sqrt{8 + 9t^2}} = \color{magenta} \dfrac{6\sqrt{2}t}{\sqrt{8 + 9t^2}}\end{align}}$
	
	${\begin{align} \kappa = \dfrac{|\mathbf{r}'(t) \times \mathbf{r}''(t)|}{|\mathbf{r'(t)}|^3} = \dfrac{6\sqrt{2}t^2}{t^3(8+9t^2)^{\frac{3}{2}}} = \color{magenta} \dfrac{6\sqrt{2}}{t(8+9t^2)^{\frac{3}{2}}}\end{align}}$
	
	**b)** Find the length of the piece of the curve from ${t = 0}$ to ${t = 1}$.
	
	${\int_0^1 \sqrt{(2t)^2 + (2t)^2 + (3t^2)^4} = \int_0^1 \sqrt{8t^2 + 9t^4} = \int_0^1 t\sqrt{8 + 9t^2}}$
	${u = 8 + 9t^2, du = 18t\,dt \implies dt = \dfrac{du}{18t}}$
	${\int_0^1 t\sqrt{8 + 9t^2} = \int_0^{17} \dfrac{\sqrt{u}}{18} du = \dfrac{u^{\frac{3}{2}}}{27}\bigg|_{0}^{17} = \dfrac{17^{\frac{3}{2}}}{27}}$
    .
5. Sketch and describe the surfaces ${x^2 + 4y = 4}$ and ${z^2 + 4y^2 - 2x = 1}$ as well as you can.
    
6. For the function/surface ${z = f(x, y) = \sqrt{4x^2 + y^2}}$, plot level curves for ${z}$-levels of 0, 1, 2, 3, 4. Label each level curve with its ${z}$-level.
    
7. For the multivariable function ${G(x, y, z) = \ln(x^2 + y^2 + z^2 - 1)}$, do the following:
	**a)** Compute ${G(1, 2, 3)}$.
	**b)** Describe the domain of ${G}$.
	**c)** Describe the level surfaces of ${G}$.

8. Show that ${\lim_{(x,y) \to (0,0)} \dfrac{2xy}{x^2 + 2y^2}}$ does not exist.
    
9. Find the value of ${\lim_{(x,y) \to (2,2)} \dfrac{x^2 - y^2}{x - y}}$, and discuss the continuity of ${f(x, y) = \dfrac{x^2 - y^2}{x - y}}$.
    
10. Given the following relations, use the chain rule to find expressions for ${\dfrac{\partial w}{\partial t}}$ and ${\dfrac{\partial w}{\partial r}}$: ${w = x \sin(4z - 3y)}$, ${x = e^{3t-r^2}}$, ${y = rt^2}$, ${z = \dfrac{1}{rt}}$
    
11. Given that ${z = x^2y + \ln(2x + 3y)}$, ${x = t^2}$, ${y = e^{1-t}}$, find the value of ${\dfrac{dz}{dt} \bigg|_{t=1}}$.
    
12. For each question, write the letter for the correct answer in the blank.
	**i)** Which of the following statements is true? 
	(A) ${\mathbf{j} \times \mathbf{i} = \mathbf{k}}$
	(B) ${\mathbf{k} \times \mathbf{j} = \mathbf{i}}$
	(C) ${\mathbf{k} \times \mathbf{i} = \mathbf{j}}$ 
	**ii)** Which is the domain of the function ${f(x, y) = \dfrac{x}{\sqrt{x + y}}}$? (A) all points in ${\mathbb{R}^2}$ except those on the line ${y = x}$ (B) all points in ${\mathbb{R}^2}$ except those on the line ${y = -x}$ (C) all points in ${\mathbb{R}^2}$ below the line ${y = -x}$ (D) all points in ${\mathbb{R}^2}$ above the line ${y = -x}$ 
	**iii)** For which function is it true that ${f_x = 2x + 4y}$ and ${f_y = 4x + 3y^2}$? (A) ${f(x, y) = x^2 + y^3 + 4xy}$ (B) ${f(x, y) = x^2 + 4x + 4y + y^3}$ (C) ${f(x, y) = x^2y^3 + 4xy}$
