**Charles Liu**
Graph Theory - Dr. Abigail Cortez
January 14th
___

1. Let ${G}$ be a graph with order ${n}$ and size ${m}$. Prove that ${δ(G) \le \frac{2m}{n} \le ∆(G)}$

**Theorem.** ${δ(G) ≤ \frac{2m}{n} ≤ ∆(G)}$

*Proof.* Suppose that ${G}$ is a graph with order ${n}$ and size ${m}$ where ${V(G) = \{v_1, v_2, ... v_n\}}$. Since there is ${m}$ edges, ${\sum\limits_{i=1}^n\deg(v_i) = 2m}$, as each edge contributes one degree to two vertices. 

If ${\delta(G) > \frac{2m}{n}}$, then ${\sum\limits_{i=1}^n\deg(v_i) > \delta(G)\cdot n > \frac{2m}{n} \cdot n = 2m}$, which is a contradiction since ${\sum\limits_{i=1}^n\deg(v_i) = 2m}$.

Thus, ${δ(G) ≤ \frac{2m}{n}}$.

If ${\Delta(G) < \frac{2m}{n}}$, then ${\sum\limits_{i=1}^n\deg(v_i) < \Delta(G) \cdot n < \frac{2m}{n} \cdot n = 2m}$, which is a contradiction, since ${\sum\limits_{i=1}^n\deg(v_i) = 2m}$.
Thus, ${\Delta(G) \ge \frac{2m}{n}}$

With these results combined, ${δ(G) ≤ \frac{2m}{n} ≤ ∆(G)}$.

___

2. Show that in any group of two or more people, there are always two people with exactly the same number of friends inside the group.

*Proof.* Suppose there is a ${G}$ with order ${m \ge 2}$ where each vertex represents a person in the group and each edge represents a friendship between two individuals in the group. We want to show no one has the same amount of friends (same degree).

By the way of contradiction, let's assume no one has the same degree (amount of friends). That means ${\delta(G) \ge 0}$ and ${\Delta(G) \le n - 1}$. Since there are ${n}$ numbers between ${0}$ and ${n-1}$ and none of the ${n}$ vertices have the same degree, the sequence of degree count must go ${\{0, 1, ... n-1\}}$. However, a vertex with degree ${n-1}$ would need to be connected with all other vertices, whereas a vertex with degree ${0}$ is not connected to vertices, posing a contradiction.

Therefore, ${G}$ must have vertices that repeat degrees and a group of two or more people must have at least two people with the same number of friends in the group.

___

3. A sequence ${\{d_1, d_2, · · · , d_n\}}$ is graphic if there is a graph ${G}$ of size ${n}$ whose vertices have exactly ${\{d_1, d_2, · · · , d_n\}}$ for their degrees.  

(a) Explain why the sequence ${\{7, 6, 5, 4, 3, 3, 2\}}$ is not graphic.  

We can recognize that one of the vertices has degree ${7}$ although there are only ${7}$ elements, which is a contradiction since each vertex can only have a maximum degree of ${7-1 = 6}$. Therefore, the graph with the given degree sequence cannot exist, and is thus not graphic.

Alternatively,
For any graph, the summation of the degree count of all vertices is equal to double the size (${n}$) since each edge in the graph contributes two degrees to the sum of all degrees. 

Assume that a graphic graph for ${V(G) = \{v_1, v_2, ... v_7\} = \{7, 6, 5, 4, 3, 3, 2\}}$ exists. Since there are seven vertices, ${n = 7}$. ${\sum\limits_{i=1}^7\deg(v_i)}$ should equal ${2\cdot 7 = 14}$. However, ${\sum\limits_{i=1}^7\deg(v_i) = 7+6+5+4+3+3+2 = 30 \neq 14}$, resulting in a contradiction. Therefore, a graph with ${\{7, 6, 5, 4, 3, 3, 2\}}$ as degrees for vertices cannot exist, and the sequence is not graphic.

(b) Explain why the sequence ${\{6, 6, 5, 4, 3, 3, 1\}}$ is not graphic.

Assume that a graphic graph for ${V(G) = \{v_1, v_2, ... v_7\} = \{6, 6, 5, 4, 3, 3, 1\}}$ exists. Since there are seven vertices, ${n = 7}$. ${\sum\limits_{i=1}^7\deg(v_i)}$ should equal ${2\cdot 7 = 14}$. However, ${\sum\limits_{i=1}^7\deg(v_i) = 6+6+5+4+3+3+1 = 28 \neq 14}$, resulting in a contradiction. Therefore, a graph with ${\{7, 6, 5, 4, 3, 3, 2\}}$ as degrees for vertices cannot exist, and the sequence is not graphic.

___

4. Ten college students are attending a party and each student has at least one friend present.  
When Alphonso asks each of the other nine how many friends of theirs are at the party, each gives a different answer.  

(a) Draw a graph to represent this situation. Each student should correspond to a vertex in  
the graph; two vertices should have an edge between them if those students are friends.  
Label each vertex with one of the letters A, B, C, D, E, F, G, H, I, and J; let A represent  
Alphonso.  

![[HW 1 2025-01-14 19.33.15.excalidraw|300]]

(b) How many of Alphonso’s friends are at the party?
${5}$ of Alphonso's friends.

___

5. Draw an ${r}$-regular graph of order 9 for all possible values of ${r}$

![[HW 1 2025-01-14 20.11.34.excalidraw|300]]
![[HW 1 2025-01-14 20.07.07.excalidraw|300]]
![[HW 1 2025-01-14 20.08.56.excalidraw|300]]
![[HW 1 2025-01-14 20.16.51.excalidraw|300]]
![[HW 1 2025-01-14 20.18.36.excalidraw|300]]

___

6. Determine all of the induced subgraphs of the graph G below.

![[HW 1 2025-01-14 20.21.17.excalidraw|500]]