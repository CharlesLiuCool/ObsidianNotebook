**Charles Liu**
Graph Theory - Dr. Abigail Cortez
March 2nd, 2025
___

1. Determine whether the graphs below are isomorphic.  
If the graphs are isomorphic, give an appropriate one-to-one correspondence.  
Otherwise, prove that the graphs are not isomorphic. 

![[Pasted image 20250302112451.png]]

Let ${\phi: V(G) \to V(H)}$.

We can take

${\phi(a) = 1}$
${\phi(f) = 2}$
${\phi(j) = 3}$
${\phi(e) = 6}$
${\phi(c) = 5}$
${\phi(h) = 9}$
${\phi(g) = 8}$
${\phi(b) = 10}$
${\phi(d) = 7}$
${\phi(i) = 4}$

Since ${\phi}$ is bijective and preserves edges, it is an isomorphism. Since an isomorphism exists between ${G}$ and ${H}$, ${G}$ and ${H}$ are isomorphic.

___

2. Determine whether the graphs below are isomorphic.  
If the graphs are isomorphic, give an appropriate one-to-one correspondence.  
Otherwise, prove that the graphs are not isomorphic.  

![[Pasted image 20250303203014.png]]

We can find isomorphism ${\phi: V(G) \to V(H)}$, where
${\phi(u_3) = v_5}$
${\phi(u_4) = v_4}$
${\phi(u_2) = v_1}$
${\phi(u_1) = v_2}$
${\phi(u_5) = v_3}$
${\phi(u_6) = v_6}$

${\phi}$ is bijective and preserves edges, so it is an isomorphism. Since an isomorphism exists between ${G}$ and ${H}$, ${G}$ and ${H}$ are isomorphic.

___

3. Determine whether the graphs below are isomorphic.  
If the graphs are isomorphic, give an appropriate one-to-one correspondence.  
Otherwise, prove that the graphs are not isomorphic.  

![[Pasted image 20250303210100.png]]

No, the graph on the right of the image has a three-cycle (${e,g,h}$) but the graph on the left doesn't, so it can't preserve that structure.

___

4. Consider the following incidence matrix 

${B = \begin{bmatrix} 1 & 1 & 0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\ 0 & 1 & 1 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 1 & 0 & 0 & 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 & 1 & 0 & 0 & 0 & 0 & 1 \\ 1 & 0 & 0 & 0 & 1 & 1 & 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 1 & 1 & 1 & 1 & 1 \end{bmatrix}}$

*(a)* Draw the graph ${G}$ having ${B}$ as its incidence matrix.  

![[HW 4 2025-03-03 21.06.26.excalidraw]]

*(b)* Compute the adjacency matrix ${A}$ and the degree matrix ${D}$ for the graph ${B}$.  

${A = \begin{bmatrix} 0 & 1 & 0 & 0 & 1 & 1 \\ 1 & 0 & 1 & 0 & 0 & 1 \\ 0 & 1 & 0 & 1 & 0 & 1 \\ 0 & 0 & 1 & 0 & 1 & 1 \\ 1 & 0 & 0 & 1 & 0 & 1 \\ 1 & 1 & 1 & 1 & 1 & 0 \end{bmatrix}}$

${D = \begin{bmatrix} 3 & 0 & 0 & 0 & 0 & 0 \\ 0 & 3 & 0 & 0 & 0 & 0\\ 0 & 0 & 3 & 0 & 0 & 0 \\ 0 & 0 & 0 & 3 & 0 & 0 \\ 0 & 0 & 0 & 0 & 3 & 0 \\ 0 & 0 & 0 & 0 & 0 & 5 \end{bmatrix}}$



___

5. Draw all nonisomorphic graphs with ${4}$ vertices. 

![[HW 4 2025-03-03 21.16.13.excalidraw]]
___

6. Show that the maximum size of a bipartite graph of order ${10}$ is ${25}$.  

**Theorem.** The maximum size of a bipartite graph of order ${10}$ is ${25}$.
*Proof:*
Let ${G}$ be a bipartite graph of order ${10}$. Since ${G}$ is bipartite, it can be written as ${G = U \cup V}$ where ${U,V \neq \emptyset}$ are disjoint subsets of ${G}$ and ${|U| + |V| = 10}$.

Let the order of ${U}$ be ${n}$. Then the order of ${V}$ is ${10 - n}$.

All edges must connect one vertex in ${U}$ to one in ${V}$. At maximum, each vertex in ${U}$ can share an edge with every vertex in ${V}$ for a total of ${(10 - n)}$ edges per each of the ${n}$ vertices.

Thus, the size of ${G}$ is less than or equal to ${(10-n)n}$ where ${1 \le n \le 10}$ (there must be at least one vertex in both ${U}$ and ${V}$).

To find the maximum of ${f(n) = (10-n)n = 10n - n^2}$, we will take the derivative.
We solve that ${f'(n) = -2n + 10}$.
We get a critical point at ${n = 5}$.
We find that when ${n > 5}$, ${f'(n) < 0}$, and when ${n < 5}$, ${f'(n) > 0}$, so the point ${(5,f(5))}$ is an absolute maximum.

We can then solve that ${f(5) = 50 - 25 = 25}$, so the maximum size of ${G}$ is ${25}$.

___


7. Determine the maximum size of a bipartite graph of order ${n ≥ 2}$. Justify your conclusion.  

**Theorem.** The maximum size of a bipartite graph of order ${n \ge 2}$ is ${\frac{n^2}{4}}$ when ${n}$ is even, and ${n^2 - \frac{1}{2}n}$ when ${n}$ is odd.
*Proof:*
Let ${G}$ be a bipartite graph of order ${n \ge 2}$. It can be written as ${G = U \cup V}$ where ${U,V \neq \emptyset}$ are disjoint subsets of ${G}$ and ${|U| + |V| = n}$.


Let the order of ${U}$ be ${m}$. Then the order of ${V}$ is ${n - m}$.

All edges must connect one vertex in ${U}$ to one in ${V}$. At maximum, each vertex in ${U}$ can share an edge with every vertex in ${V}$ for a total of ${(10 - m)}$ edges per each of the ${m}$ vertices.

Thus, the size of ${G}$ is less than or equal to ${(n-m)m}$ where ${1 \le m \le 10}$ (there must be at least one vertex in both ${U}$ and ${V}$).

To find the maximum of ${f(m) = (n-m)m = nm - m^2}$, we will take the derivative with respect to ${m}$.
We solve that ${f'(m) = -2m + n}$.
We get a critical point at ${m = \frac{n}{2}}$.

We find that when ${m > \frac{n}{2}}$, ${f'(m) < 0}$, and when ${m < \frac{n}{2}}$, ${f'(m) > 0}$, so the point ${(\frac{n}{2},f(\frac{n}{2}))}$ is an absolute maximum.

*Case 1:* ${n}$ is even
We can then solve that ${f(\frac{n}{2}) = \frac{n^2}{2} - \frac{n^2}{4} = \frac{n^2}{4}}$, so the maximum size of ${G}$ is ${\frac{n^2}{4}}$.

*Case 2:* ${n}$ is odd
Since ${m = \frac{n}{2}}$ isn't an integer, we need to take the closest integer that still maximizes ${f(m)}$.
Since ${n}$ is odd, we can write it as ${n=2k+1}$ where ${k \in \Bbb{N}}$.
The closest two integers are ${\lfloor\frac{n}{2} \rfloor = 2k}$ and ${\lceil \frac{n}{2} \rceil = 2k + 2}$
We can solve that
${f'(\lfloor\frac{n}{2} \rfloor) = n\lfloor\frac{n}{2} \rfloor -\lfloor\frac{n}{2} \rfloor^2 = n (2k) - 4k^2}$

${f'(\lceil\frac{n}{2} \rceil) = n\lceil\frac{n}{2} \rceil - \lceil\frac{n}{2}\rceil^2 = n(2k+2) - 4(k+2)^2}$ 

${= n(2k) + 2n - 4k^2 - 16k - 16}$
${= n(2k) + 2n - 4k^2 - 8n - 8}$
${= n(2k) -4k^2 - 6n - 8}$

So ${f'(\lfloor\frac{n}{2} \rfloor) \ge f'(\lceil\frac{n}{2} \rceil)}$.

Thus, for the odd case, the maximum size of ${G}$ is ${f(\lfloor\frac{n}{2} \rfloor) = n\lfloor\frac{n}{2}\rfloor - \lfloor\frac{n}{2}\rfloor = \lfloor\frac{n}{2}\rfloor(n-1) = n (\frac{n-1}{2}) = n^2 - \frac{1}{2}n}$.

___

8. There are five women at a party and six men.  
The women: Anise (A), Betty (B), Celina (C), Daniela (D), and Evelyn (E).  
The men: Alejandro (a), Ben (b), Charles (c), Douglas (d), Eddie (e), and Frank (f ).  
The compatible dancing partnerships are displayed by means of a graph below.  

![[Pasted image 20250303210223.png]]


Is it possible to have all women dancing so that each dancing partnership is a compatible  
one? Justify your conclusion.  

No.
Alejandro, Charles, and Frank are only compatible with Celina. This means after Celina goes with someone, the other two will be compatible partnerless. This leaves ${3}$ more men (Ben, Douglas, and Eddie) with compatible partners and ${4}$ women (Anise, Betty, Daniela, and Evelyn). Since there are less men than women, at least one women will go partnerless.

___

9. A high school has openings for six teachers, with one teacher needed for each of these areas:  
mathematics, chemistry, physics, biology, psychology, and ecology.  
In order to hire a teacher in a particular area, he or she must have either majored or minored  
in that subject. The school receives six applicants for these positions:  

Mr. Arrowsmith. major: physics; minor: chemistry  
Mr. Beckman. major: biology; minors: physics, psychology, ecology  
Ms. Chase. major: chemistry; minors: mathematics, physics  
Mrs. Deerfield. majors: chemistry, biology; minors: psychology, ecology  
Mr. Evans. major: chemistry; minor: mathematics  
Ms. Form. major: mathematics; minor: physics  

*(a)* Draw a graph to represent this situation.  
![[HW 4 2025-03-03 22.06.57.excalidraw]]
*(b)* What is the largest number of applicants the school can hire? Justify your answer.

The school can hire at maximum ${5}$. Mr. Beckman and Mr. Deerfield are the only teachers for biology, psychology, and ecology, so one of those subjects will be guaranteed to lack a teacher. As a result, one teacher won't be hired as he would otherwise teach a repeat subject.

___