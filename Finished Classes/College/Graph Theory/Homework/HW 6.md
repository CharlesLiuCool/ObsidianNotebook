**Charles Liu**
Graph Theory - Dr. Abigail Cortez
April 11th, 2025

___

1. A tournament ${T}$ is *transitive* if whenever ${(u, v)}$ and ${(v, w)}$ are arcs of ${T}$, then ${(u, w)}$ is also an arc of ${T}$ .  
Prove that a tournament is ${T}$ is transitive if and only if every two vertices of ${T}$ have distinct outdegrees.  

*Proof:*
"${\Rightarrow}$"
Assume ${T}$ is transitive.
By way of contradiction, assume two vertices, ${v_i, v_j}$, of ${T}$ have the same outdegree ${k}$.
By the definition of tournaments and without loss of generality, there must be a directed edge from ${v_i}$ to ${v_j}$. By definition of transitivity, there must thus be an arc directly from ${v_i}$ to ${v_j}$. However, this means ${v_i}$ has ${k+1}$ outdegrees, a contradiction.
Thus, every two vertices in ${T}$ must have distinct outdegrees.

"${\Leftarrow}$"
Assume every two vertices of ${T}$ have distinct outdegrees. Take three vertices, ${v_i}$, ${v_j}$ and ${v_k}$. By the definition of tournaments and without loss of generality, there must be a directed edge from ${v_i}$ to ${v_k}$, ${v_i}$ to ${v_j}$ (or vice versa) and ${v_j}$ to ${v_k}$ (or vice versa). Since for any given ${(v_i,v_k)}$, ${(v_i,v_j)}$ and ${(v_j,v_k)}$ both exist if there is a ${v_j}$, ${T}$ is transitive.

___

2. Let ${T}$ be a tournament of order ${n ≥ 3}$ with ${V (T ) = \{v_1, v_2, · · · , v_n\}}$. Prove that if  
${\text{deg}_\text{out}(v_i) > \text{deg}_\text{in}(v_i)}$ for ${1 \le i \le n− 1}$, then ${T}$ is not strongly connected.  

*Proof:*
Assume that ${\text{deg}_\text{out}(v_i) > \text{deg}_\text{in}(v_i)}$ for ${1 \le i \le n− 1}$.
BWOC, assume that ${T}$ is strongly connected.
Since its a tournament, and ${v_1,...v_{n-1}}$ satisfy the principle more outdegrees than indegrees, those ${n-1}$ vertices have at least ${n/2}$ outdegrees. This amounts to a total of ${(n)(n-1)/2}$ outdegrees. Since for any tournament, there must be ${n}$ choose ${2}$ or ${n(n-1)/2}$ outdegrees, ${v_n}$ can only have ${0}$ outdegrees. Thus, ${T}$ isn't strongly connected as there is no path from from ${v_n}$ to any other vertex.

___

3. Determine the chromatic number of each of the following  
(a) the Petersen graph  
![[HW 6 2025-04-13 21.17.20.excalidraw]]
Three

(b) the n-cube ${Q_n}$  
Two

(c) the wheel ${W_n = C_n + K_1}$  
![[HW 6 2025-04-13 21.20.04.excalidraw]]
 
4. Prove or disprove. To disprove a statement, it is sufficient to provide a counterexample.  

*(a)* If a planar graph contains a triangle, then its chromatic number is ${3}$.
False.
Consider the graph ${K_4}$, which has chromatic number ${4}$. It has a triangle (pick any three vertices), but doesn't have chromatic number ${3}$.

*(b)* If there is a ${4}$-coloring of a graph ${G}$, then ${\chi(G) = 4}$.  
False.
Consider the graph ${C_4}$ which has chromatic number number ${2}$. It is ${4}$-colorable not ${2}$-colorable.

*(c)* If a graph ${G}$ contains a subgraph isomorphic to the complete graph ${K_r}$, then ${\chi(G) \ge r}$.  
True.
*Proof:*
${G}$ contains the subgraph isomorphic to ${K_r}$. Consider the construction of ${G}$ by adding edges and vertices to ${K_r}$. ${K_r}$ has chromatic number ${r}$, and adding edges and vertices can't every decrease the chromatic number, so ${G}$ must have chromatic number of at least ${r}$.

*(d)* If ${G}$ is a graph with ${\chi(G) ≥ r}$, then ${G}$ contains a subgraph isomorphic to the complete graph ${K_r}$.  
False.
Consider the graph ${C_5}$,  with chromatic number ${3}$. There is no subgraph of ${C_5}$ that is isomorphic to ${K_3}$, as no vertex has degree ${3}$.

5. Eight mathematics majors at a small college are permitted to attend a meeting dealing with undergraduate research during final exam week provided they make up all the exams missed on the Monday after they return. The possible time periods for these exams on Monday are  

(i) 8:00–10:00; (ii) 10:15–12:15; (iii) 12:30–2:30;  
(iv) 2:45–4:45; (v) 5:00–7:00; (vi) 7:15–9:15.  

The eight students and the courses Advanced Calculus (AC), Differential Equations (DE), Geometry (G), Graph Theory (GT), Linear Programming (LP), Modern Algebra (MA), Statistics (S), Topology (T) each student is taking are

Alicia: AC, DE, LP; Brian: AC, G, LP; Carla: G, LP, MA;  
Diane: GT, LP, MA; Edward: DE, GT, LP; Faith: DE, GT, T;  
Grace: DE, S, T; Henry: AC, DE, S.

(a) Represent this situation with a graph. Think carefully about what the 
vertices and edges need to represent.  

![[HW 6 2025-04-13 22.34.01.excalidraw]]

(b) Use graph theory to determine the earliest time on Monday that all eight students can finish their exams if two exams cannot be given during the same time period if some student must take both exams.  

We need at least ${4}$ time blocks, so it would end at 4:45pm.

6. The road intersection shown in the figure below needs a traffic signal to handle the traffic flow. If cars from two different lanes could collide, then cars from these two lanes will not be permitted to enter the intersection at the same time.  

![[RoadLanes.png]]

*(a)* Represent this situation as a graph where the nodes are lanes and two nodes are joined by an edge if vehicles in these two lanes cannot safely enter the intersection at the same time.  

![[HW 6 2025-04-13 22.49.01.excalidraw]]

*(b)* What is the minimum number of signal phases that are needed to ensure safe traffic?

${3}$ phases.