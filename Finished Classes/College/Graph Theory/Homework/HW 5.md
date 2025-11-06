**Charles Liu**
Graph Theory - Dr. Abigail Cortez
March 29th, 2025

___

1. For each part of this question, draw a connected graph with at least five vertices that satisfies the given conditions:  

*(a)* Every edge is a bridge.  
![[HW 5 2025-03-29 16.59.48.excalidraw]]
*(b)* Every edge is a link.  
![[HW 5 2025-03-29 17.00.36.excalidraw]]
*(c)* Exactly one edge is a bridge.  
![[HW 5 2025-03-29 17.06.39.excalidraw]]
*(d)* Exactly three edges are links.  
![[HW 5 2025-03-29 17.08.44.excalidraw]]
*(e)* Every edge is a link, but if you remove any edge, the remaining edges become bridges in the new graph.  
![[HW 5 2025-03-29 17.10.02.excalidraw]]

___

2. *(a)* There are three different trees with five vertices, up to isomorphism. Draw these three trees.  
![[HW 5 2025-03-29 17.11.13.excalidraw]]
*(b)* There are six different trees with six vertices, up to isomorphism. Draw these six trees.  
![[HW 5 2025-03-29 17.14.57.excalidraw]]

___

3. Suppose T is a tree with the following properties:  
• Every vertex has degree at most 3  
• There exists a vertex r such that every vertex v of T satisfies d(r, v) ≤ 2. That is, there  
is a vertex r such that the distance between r and every vertex in T is less than or equal  
to 2.  
What is the minimum and maximum number of vertices T can have?  

The minimum number of vertices is ${0}$.
The maximum number of vertices is ${4}$.

___

4. A certain tree T of order 21 has only vertices of degree 1, 3, 5, and 6. If T has exactly 15 leaves and one vertex of degree 6, how many vertices of T have degree 5?  

The tree has ${21-1 = 20}$ edges.
Let ${v_1, v_2, v_3}$ and ${v_4}$ be the number of vertices of degree ${1,3,5}$ and ${6}$ respectively.

${v_1 = 15}$ and ${v_4 = 1}$

${15 + v_2 + v_3 + 1 = 21}$
${\implies v_2 + v_3 = 5}$
${\implies 3v_2 + 3v_3 = 15}$

${1 \cdot 15 + 3v_2 + 5v_3 + 6 \cdot 1 = 20 \cdot 2}$
${\implies 3v_2 + 5v_3 = 19}$

${\implies 2v_3 = 4}$
${\implies v_3 = 2}$
${\implies v_2 = 3}$

So there are ${2}$ vertices with degree ${5}$.

___

5. Give an example of a tree of order 6 containing four vertices of degree 1 and two vertices of degree 3. (Only one tree has these properties.)  

![[HW 5 2025-03-30 10.54.56.excalidraw]]

___

6. A certain tree T of order n contains only vertices of degree 1 and 3. Show that T contains ${(n − 2)/2}$ vertices of degree 3.  

A tree of order ${n}$ has ${n-1}$ vertices.
Let ${v_1}$ be the number of vertices of degree ${1}$ and ${v_2}$ be the number of vertices of degree ${3}$.

${v_1 + v_2 = n}$
${v_1 + 3v_2 = 2(n-1) = 2n - 2}$

${\implies 2v_2 = n -2}$
${\implies v_2 = \frac{n-2}{2}}$

___

7. Let G be a connected graph containing only even vertices. Prove that G cannot contain a bridge. (Hint: In any negative-type result, it is a good proof strategy to try proof by contradiction.)  

Let ${G}$ be a connected graph of only even vertices.
BWOC, assume ${G}$ has a bridge, ${b}$.
Then ${b}$ must connect two components, each a connected graph. Since each vertex has even degree, removing ${b}$ would result in one odd vertex in each of these components, a contradiction, as each connected graph must have an even number of odd vertices.
Thus, ${G}$ cannot have a bridge.

___

8. Apply Kruskal’s algorithm to find a minimum spanning tree in the weighted graph below.  
Illustrate each step of the algorithm.  

![[HW 5 2025-03-30 12.11.24.excalidraw]]

___

9. Determine the number of possible spanning trees of the graph below. Treat each vertex as a unique node. In other words, count every single possible spanning tree, regardless of whether a spanning tree is isomorphic to another spanning tree.  

![[HW 5 2025-03-30 11.47.07.excalidraw]]

Hint: How many edges must you remove to produce a spanning tree? How many ways can this number of edges be removed without disconnecting the graph? Consider two cases, depending on whether or not the shared edge is removed. 

We need to remove ${2}$ edges to build a spanning tree. However, we cannot remove two edges that both connect to the same node if that node has degree ${2}$.

There are ${8}$ nodes of degree ${2}$.

There are ${9}$ edges to delete from.

The amount of possible spanning trees is ${\begin{pmatrix} 9 \\ 2\end{pmatrix} - 8 = \frac{9 \cdot 8}{2} \cdot 8 = 288}$

___

10. Give a brief description of your intention for the final course project.  

*(a)* Are you doing the Graph Theorist Sketchpad or the PowerPoint slides? 
We intend to make a slideshow along with an algorithm that uses graph theory for recommending.

*(b)* You only need to answer one of the questions below.  

i. If you’re doing the sketchpad, what sort of coding environment are you planning  
on using?  
For the algorithm, we might use Python, C++ or Rust.

ii. If you’re doing the PowerPoint, what topics are you considering?  
We intend to build an algorithm/application that uses graph theory to recommend users content based on their behavior.

___

11. Find a video on YouTube that involves graph theory and give a one-paragraph report, including the URL and a brief synopsis.  

You can choose any video related to graph theory, but consider choosing a video that covers an application that interests you (DFS algorithm, BFS algorithm, neural networks, graph theory in transportation networks, Binary Search Trees, graph theory in biology, mazes, sudoku, linguistics, the world wide web, etc.).  

https://www.youtube.com/watch?v=NyNqzDKcKG4

Graph theory can be used to build neural networks that recommend users content/items based on behaviors. There is content-based filtering and collaborative filtering. Content-based filtering is recommending items they might like based off of other items they already liked. Collaborative filtering uses user similarities to recommend them items that similar users with similar behaviors liked. Rating information can be scored in a matrix corresponding to a user and item. This information can be placed onto a bipartite graph with edges being ratings connecting user and product. We can do link prediction using a formula to fill edges that don't exist yet and predict if a user will like an item or not.
___