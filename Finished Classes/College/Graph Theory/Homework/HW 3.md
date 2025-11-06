**Charles Liu**
Graph Theory - Dr. Abigail Cortez
Feburary 17th 2025

___

1. Let ${G}$ be an ${r}$-regular bipartite graph where ${r \ge 1}$. Then the vertex set of ${G}$ can be divided into disjoint subsets ${U}$ and ${W}$ such that every edge of ${G}$ joins a vertex of ${U}$ and a vertex of ${W}$.  
Prove in this case that the sets ${U}$ and ${W}$ contain the same number of vertices.  

**Theorem.** ${|U| = |W|}$
*Proof.*
For every vertex in ${U}$, there is ${r}$ edges connected. This means that the degree sum of vertices in ${U}$ is ${r|U|}$.
Likewise, the degree sum of vertices in ${W}$ is ${r|W|}$.
This means the total number of edges in ${G}$ is ${\frac{r|U| + r|W|}{2}}$

Since the graph is bipartite, no vertex in ${U}$ is adjacent to another vertex in ${U}$. This means every edge of ${G}$ connects a vertex of ${U}$ and a vertex of ${W}$. Since each edge is shared, the total number of edges in graph ${G}$ can also be expressed as ${r|U|}$

Since ${\frac{r|U| + r|W|}{2} = r|U|}$, we can solve that ${r|U| = r|W|}$ and ${|U| = |W|}$, so ${U}$ and ${W}$ contain the same amount of vertices.


2. Consider the graph ${C_5 \times C_5}$ below. Explain why this graph is or is not bipartite.  

![[C5 x C5.png|400]]

The graph is not bipartite because there is odd cycles. 
![[HW 3 2025-02-17 14.19.07.excalidraw]]

1. Use the Havel-Hakimi theorem to determine which of the following sequences are graphical. For each graphical sequence, construct a graph for which the given sequence is a degree sequence of the graph.  

*(a)* ${s_1:\,5, 3, 3, 3, 3, 2, 2, 2, 1}$  
${2,2,2,2,2,2,1,1}$
Graphical
![[HW 3 2025-02-17 21.13.21.excalidraw]]

*(b)* ${s_2:\,6, 3, 3, 3, 3, 2, 2, 2, 2, 1, 1 }$ 
${2,2,2,2,1,1,2,2,1,1}$
${2,2,2,2,2,2,1,1,1,1}$
Graphical
![[HW 3 2025-02-17 14.28.16.excalidraw]]

*(c)* ${s_3:\,6, 5, 5, 4, 3, 2, 1 }$ 
${4,4,3,2,1,0}$
${3,2,1,0}$
${2,1,-1}$
*NOT* graphical, cannot have negative degree count.

*(d)* ${s_4:\,7, 6, 5, 4, 4, 3, 2, 1 }$
${5,4,3,3,2,1,0}$
${3,2,2,1,0,0}$
${1,1,0}$
Graphical

![[HW 3 2025-02-17 14.31.06.excalidraw]]

3. Determine whether each of the following figures can be drawn without lifting one’s pen from the paper or tracing a line more than once. Explain your reasoning. What does this have to do with graph theory?  

*(a)*  

![[HW 3 2025-02-17 14.34.10.excalidraw]]
Yes, it can be drawn with one line without retracing or lifting the pencil. With each line between intersections representing edges and each intersection/end-point representing a vertex, we can formulate the problem into a graph.
The only odd-degree vertices are the top and bottom (two total), so the graph has an Eulerian path, which means a path exists where no line is retraced but every line is traced.

*(b)*  

![[HW 3 2025-02-17 14.39.37.excalidraw]]

The graph has more than two intersections with an odd amount of lines connected to them. This means in the equivalent graph theory representation, more than two vertices have odd degree and the graph cannot have an Eulerian path. Thus, the graph *CANNOT* be traced with a single line without retracing.

*(c)*  

![[HW 3 2025-02-17 14.46.34.excalidraw]]
Yes, it can be drawn. There are only two vertices (intersections) with odd degree count, so an Eulerian path exists. Thus, a path can be drawn with a single line and no retracin

4. If possible, draw a graph ${G}$ with an even order and an odd size that contains an Eulerian Circuit; otherwise, prove why there is no such graph.  

![[HW 3 2025-02-17 15.02.07.excalidraw]]
Order: ${6}$ (even)
Size: ${7}$ (odd)

5. Sherlock Holmes is investigating the mysterious death of Count Chocula. This apparent crime occurred at the estate of the count (see below). The butler states that he saw a suspicious person enter the Computer Room (where the body was found) and then leave the room by the very same door. When the inspector questions the count’s business partner, Cap’n Crunch, he admits entering the estate by the front door and exiting by the rear door. However, Crunch says that he went through each doorway exactly once and so he could not  have been the person the butler saw. Is someone lying? How do you know?  

![[HW 3 2025-02-17 14.54.48.excalidraw]]

Captain Crunch is lying. When entering the front door, he would be in the lobby. Since the lobby has four remaining doors that Captain Crunch hasn't gone through, he would need to go through all of them (assuming his story is true). This means he would need to leave the lobby, re-enter, leave, then re-enter again, ending up stuck in the lobby. This contradicts his story that he left through the rear door, so Captain Crunch is lying.