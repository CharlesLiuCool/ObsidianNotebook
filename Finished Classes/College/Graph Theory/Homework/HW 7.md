1. Prove or disprove: If ${G}$ is a graph with ${\chi(G) \le 4}$, then ${G}$ is planar.

*False.*
 Consider the graph ${K_{3,3}}$. We know ${\chi(K_{3,3}) = 2}$ which is less than ${4}$, but ${K_{3,3}}$ is nonplanar.

2. Give an example of the following or explain why no such example exists:

*a)* A planar graph with chromatic number ${5}$
This is not possible. Every planar graph is ${4-}$colorable or less, by the ${4}$ colorable theorem. 


*b)* A nonplanar graph with chromatic number ${3}$.
Yes. Consider ${K_{3,3}}$ with one extra vertex of degree two connected to one node of each bipartite set of vertices.

![[HW 7 2025-04-23 14.20.18.excalidraw|200]]

*c)* A graph ${G}$ with ${\Delta(G) = 2\chi(G)}$
![[HW 7 2025-04-23 14.22.45.excalidraw|400]]
${\chi(G) = 2}$
${\Delta(G) =  4}$

*d)* A graph ${G}$ with ${\chi(G) = 2\Delta(G)}$
Consider ${P_2}$.
![[HW 7 2025-04-23 14.23.48.excalidraw|200]]
${\chi(G) = 2}$
${\Delta(G) = 1}$

*e)* A noncomplete graph of order ${n}$ with chromatic number ${n}$.

Not possible. For a noncomplete graph, two vertices don't have an edge. Since one vertex doesn't connect with another, the maximum number of colors we would need is ${n-1}$.


3. For each statement, list each number in the set ${\{0,1,2,3,4,5,6\}}$ that is correct response to each statement below. You can list more than one number for a statement.

*a)* The size of a nontrivial complete graph. (The complete graph of order one is trivial).
${1,3,6}$
We can have ${C_1, C_3, C_4}$, with ${1,3,}$ and ${6}$ edges respectively.

*b)* The number of distinct ${u-v}$ paths for vertices ${u}$ and ${v}$ in a tree.
There is a unique path between every pair of vertices.
${1}$
*c)* The number of cycles in a transitive tournament.
No cycles in a transitive tournament.
${0}$

*d)* The number of bridges in a tree of order ${6}$.
${5}$. ${n = m + 1}$ where ${n}$ is the number of vertices and ${m}$ is the number of edges.

*e)* The value of ${r}$ for a nonempty r-regular graph of order ${7}$.
${2, 4, 6}$

*f)* The maximum degree of a tree of order ${5}$.


The maximum degree is ${4}$.

*g)* The chromatic number for an odd cycle.

${3}$. It's isomorphic to ${C_3}$.

4. If every vertex of a tournament ${T}$ of order ${n}$ has the same outdegree ${x}$, then what is ${x}$?

First Theorem of Digraphs: in-degrees = out-degrees.

${\sum\limits_{i=1}^n \text{deg}_{\text{out}} (v_i) = \sum\limits_{i=1}^n \text{deg}_{\text{in}}(v_i) = m}$

There are ${n}$ choose ${2}$ arcs in a tournament with ${n}$ vertices. This means the total outdegrees is ${n(n-1)/2}$. Dividing by ${n}$ we get each vertex has outdegree ${(n-1)/2}$.

Thus, ${x = (n-1)/2}$

5. A graph ${G}$ of order ${n}$ has ${\chi(G) = \alpha(G) = k}$, where ${\alpha(G)}$ is the independence number of ${G}$. Furthermore, there is exactly one way to partition ${V(G)}$ into ${k}$ color classes; and in this coloring, every color class has distinct cardinality.
Show that ${\Delta(G) = n-1}$, where ${\Delta(G)}$ is the maximum degree of ${G}$.

The possible cardinalities of each color class are ${1,2,...,k}$ as the minimum is one and the maximum ${k}$ and all color classes have a different cardinality. One vertex must be adjacent to every other due to the cardinality, so ${\Delta(G) = n-1}$.


6. Show that the graph below is planar by drawing it as a plane graph. Verify Euler's Formula holds for the graph.

![[HW 7 2025-04-23 14.26.08.excalidraw]]

${n = 6}$
${m = 10}$
${r = 5}$
${6 - 10 + 6 = 2}$

7. A connected k-regular graph of order 12 is embedded in the plane, resulting in 8 regions.
What is k?

${n - m + r = 2}$
${12 - m + 8 = 2}$
${m = 18}$
${12k = 2m = 36}$
${\implies k = 3}$

8. (a) The vertices of a certain graph G have degrees ${3, 4, 4, 4, 5, 6, 6}$. Prove that G is nonplanar.
(b) The vertices of a certain graph G have degrees ${4, 4, 4, 5, 5, 5, 6, 6, 6, 7, 7, 7}$. Prove
that G is nonplanar.
9. Give an example of each of the following or explain why no such example exists.
(a) a planar graph of order 4
(b) a nonplanar graph of order 4
(c) a plane graph having 5 vertices, 10 edges, and 7 regions.
(d) a planar graph of order n ≥ 3 and size m with m = 3n − 6.
(e) a nonplanar graph of order n ≥ 3 and size m with m = 3n − 6.
10. Q4 and C4 × C4 are isomorphic graphs. Use this fact to show that Q4 can be successfully
drawn on a one-holed torus.
11. Prove that C4 ×C4 cannot be drawn in the plane. To do this, compute what n and m are and
then what r would have to be if it were drawn on a sphere (use your drawing from Question
10). Then use a total edge count argument—recall that C4 × C4 is bipartite—to arrive at a
contradiction.