### **Families of Graphs**  
– Be able to identify and name the following families of graphs:  
${P_n, C_n, K_n, K_{m,n}, Q_n}$  

*${P_n}$*: a path graph with ${n}$ vertices
- ${n-1}$ edges
- first and last vertex have ${1}$ edge, every other has ${2}$
- all connected

*${C_n}$*: a cycle graph with ${n}$ vertices
- every vertex degree ${2}$
- simple cycle (usually looks like a loop)

*${K_n}$*: complete graph of ${n}$ vertices
- every vertex is adjacent to every other one
- every vertex degree ${n-1}$

*${K_{m,n}}$*: complete bipartite graph
- ${m}$ vertices in one disjoint subset, ${n}$ in the other
- each vertex in ${m}$ is connected to every vertex in ${n}$
- every vertex in ${m}$ has degree ${n}$, every vertex in ${n}$ has degree ${m}$

*${Q_n}$*: ${n}$-dimensional hypercube graph



### **Degree Sequences**  
– Be able determine whether a given degree sequence is *graphic*. 
- The given degree sequence representing degrees of vertices of a graph can construct a valid graph.

– Be able to apply the *Havel-Hakimi algorithm* and use this to build a graph with a given degree sequence.  
>**Havel-Hakimi Theorem**
**Theorem.** Given two finite sequences of integers is non-increasing order:
${(1)\,s,t_1,t_2,...,t_s,d_1,d_2,...,d_k}$
${(2)\,t_1-1,t_2-1,...,t_s-1,d_1,d_2,...,d_k}$
Then ${(1)}$ is graphic if and only if ${(2)}$ is graphic.


### **Bipartite Graphs**  
– Be able to determine whether a given graph is *bipartite* or not and be able to justify  
your conclusion.  
- no odd cycles

### **Graph Isomorphism**
– Be able to determine if two graphs are isomorphic.  
- How to tell it's *NOT* isomorphic
	- structures not preserved (e.g. cycles)
	- degree counts differ between graphs
	- different amount of vertices
- How to tell it *IS* isomorphic
	- take ${\phi}$ and map one element in the first graph to the next
	- repeat with adjacent elements preserving adjacencies in either graph
	- create final bijective map and prove that *at least one* isomorphism exists, so the two graphs are isomorphic

– If two graphs are isomorphic, be able to find an isomorphism between their vertex sets. 
– Be able to create the incidence matrix, the adjacency matrix, and the degree matrix of a graph.  
- *Incidence Matrix*
	- e.g. ${\begin{bmatrix}  & e_1 & e_2 & e_3 & e_4 & e_5 \\ a & & & & & & \\ b \\ c \\ d \\ e \end{bmatrix}}$
- *Adjacency Matrix*
	- e.g. ${\begin{bmatrix}  & a & b & c & d & e \\ a & & & & & & \\ b & & & & & \\ c & & & & & \\ d & & & & & \\ e & & & & & \end{bmatrix}}$

	- ${1}$ if adjacent, ${0}$ if not
	- ${0}$ for same vertex twice
- *Degree Matrix*
	- e.g. ${\begin{bmatrix} & a & b & c & d & e & \\ a & deg(a) & 0 & 0 & 0 & 0 \\ b & 0 & deg(b) & 0 & 0 & 0 \\ c & 0 & 0 & deg(c) & 0 & 0 \\ d & 0 & 0 & 0 & deg(d) & 0 \\ e & 0 & 0 & 0 & 0 &deg(e)\end{bmatrix}}$

– Be able to draw a graph given its incidence or adjacency matrix.  
- Let ${A}$ be the adjacency matrix, ${B}$ be the incidence matrix, and ${D}$ be the degree matrix. ${BB^{T} = A+D}$.

### **Vocabulary and Theorems**  
– Know the following definitions: trail, circuit, path, cycle.  
- *Trail:* A walk that doesn't repeat edges
- *Circuit:* A closed trail
- *Path:* A walk that doesn't repeat vertices
– Know that the total degree is always equal to twice the number of edges.  
– Know the Handshaking Lemma.  
### **Eulerian Graphs**  
– Be able to determine if a given graph has an Eulerian Circuit and be able to justify  
your conclusion.
- Every vertex has even degree
- There is a closed trail

– Be able to determine if a given graph has an Eulerian Trail and be able to justify your  
conclusion.  
- Two vertices have odd degree
- doesn't have to start and end at same location

– Be able to determine if a doodle can be drawn without lifting one’s pencil or retracing  
a line.  
- Eulerian trail
### **Matchings**  
– Be able to apply’s *Hall’s Condition* to determine if a full matching exists.  
- For a bipartite graph, we want a matching
- A perfect matching exists if and only if for every subset ${U}$, the neighbor of that subset of the vertices ${U}$ is greater than the number of vertices you picked.

### **Proof**
– There will be two proofs on the exam; you will choose one to submit for grading