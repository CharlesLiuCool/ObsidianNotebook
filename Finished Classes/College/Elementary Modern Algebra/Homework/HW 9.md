**Charles Liu**
Elementary Modern Algebra - Dr. Ben Clark
April 15th, 2025

___

1. How many zeros does ${x^2 + 3x + 2}$ have in ${\Bbb{Z}_6}$? How about ${\Bbb{Z}_7}$?  

*In ${\Bbb{Z}_6}$*
${x^2+3x+2 = (x+2)(x+1)}$
So the zeros are ${4}$ and ${5}$, so two zeroes.

*In ${\Bbb{Z}_7}$*
The zeroes are ${5, 6}$, so also two zeroes.

___

2. Let ${f(x) = 5x^4 + 3x^3 + 1}$ and ${g(x) = 3x^2 + 2x + 1}$ be polynomials in ${\Bbb{Z}_7[x]}$. Determine the quotient and remainder upon dividing ${f (x)}$ by ${g(x)}$.  
$${\begin{align} &4x^2 + 3x + 6\\ -&--------- \\3x^2 + 2x + 1\;|\;5&x^4 + 3x^3 + 1 \\5&x^4 + x^3 + 4x^2 \\&\;\;\;\;\;\;\;2x^3 + 3x^2 + 1 \\ &\;\;\;\;\;\;\;2x^3 + 6x^2 + 3x\\ &\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;4x^2+4x+1\\&\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;4x^2+5x+6\\&\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;\;6x+2\end{align}}$$

Quotient: ${4x^2+3x+6}$
Remainder: ${6x+2}$
___

3. Show that ${2x + 1}$ has a multiplicative inverse in ${\Bbb{Z}_4}$.  

Consider ${a,b \in \Bbb{Z}_4}$.
${(2x+1)(ax+b) = 1 \implies 2ax^2 + 2bx + ax + b = 1}$
So, ${b = 1}$, ${a=2}$.
Thus, ${2x+1}$ has a multiplicative inverse, ${2x+1}$, which is in ${\Bbb{Z}_4}$.

___

4. Find a polynomial with integer coefficients that has 1/2 and −1/3 as zeros.  

First consider the polynomial ${(x-1/2)(x+1/3) = 0}$
This doesn't have integer coefficients, so we scale the first left component by ${2}$ and the second by ${3}$
${2(x-1/2) 3(x+1/3) = (2x-1)(3x+1) = 0}$.

So a polynomial is ${(2x-1)(3x+1) = 6x^2 -x - 1 = 0}$

___

5. Find infinitely many polynomials ${f (x)}$ in, ${\Bbb{Z}_3[x]}$ such that ${f (a) = 0}$ for all ${a \in \Bbb{Z}_3}$.  

We want the polynomial to have the zeroes ${0,1,2}$, or all the elements in ${\Bbb{Z}_3}$.

Consider the polynomial
${(x-0)(x-1)(x-2) = x^2 - 3x + 2}$
Convert this to a polynomial in ${\Bbb{Z}_3[x]}$, and we get 
${g(x) = x^2 + 2}$.
From its construction, ${0,1,2}$ must be zeroes of the polynomial.

Also consider that ${f(x) = x^ng(x) = x^{2+n} + 2x^n \;\forall\;n \ge 0, n\in\Bbb{Z}}$ has the zeroes ${0,1,2}$. Since there are infinite such polynomials, any polynomial of that form will satisfy ${f(a) = 0}$ for all ${a \in \Bbb{Z}_3}$.

___

6. Prove that the ideal ${\langle x \rangle}$ in ${\Bbb{Q}[x]}$ is maximal. 

*Proof:*
If ${\langle x \rangle}$ is an ideal in ${Q[x]}$, then if ${\langle x \rangle \subseteq I \subseteq \Bbb{Q}[x]}$, either ${\langle x \rangle = I}$ or ${I = \Bbb{Q}[x]}$.

Assume ${\langle x \rangle \subsetneq I}$. Then there must be some element, ${f(x) \notin \langle x \rangle}$, where ${f(x) = a_0 + a_1x + a_2x^2+...+a_nx^n}$ where ${a_0 \neq 0}$ and ${a_1,...,a_n \in \Bbb{Q}}$. Also consider ${g(x) = a_1x + a_2x^2 +...+a_nx^n\in \langle x \rangle \subset I}$. Then ${f(x) - g(x) = a_0 \in I}$. Since ${a_0 \neq 0}$, ${a_0^{-1}}$ exists and is in ${\Bbb{Q}[x]}$. Thus ${a_0a_0^{-1} = 1 \in I}$, so ${I = \Bbb{Q}[x]}$.

___


7. Prove that ${(50!)^2 \text{ mod } 101 = −1 \text{ mod } 101}$.

*Proof:*
We can solve that ${(50!)^2 \text{ mod } 101= 50! \times (-51 \times -52 \times ... -100) \text{ mod } 101 = 100! \text{ mod } 101 = -1}$ (By Wilson's Theorem).