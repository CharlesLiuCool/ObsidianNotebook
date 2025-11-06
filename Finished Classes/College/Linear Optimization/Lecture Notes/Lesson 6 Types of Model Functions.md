### Using Linear Programming For Data Classification
![[Lesson 6 Types of Model Functions 2025-01-28 10.50.38.excalidraw|600]]

Find ${f(x)}$ that *maximally separates* data ${\{x_j,y_j\}}$ from data ${\{(x_i, y_i)\}}$.

If the green square ${ = (u,v)}$, If ${v \ge f(u)}$ then ${(u,v) \in \{{\color{red}{+}}\}}$
otherwise ${ (u,v) \in \{{\color{blue}o}\}}$

*Goal:* Separate Data, Classify Things, Predict Things

${\max z = \delta}$
${\text{s.t. } \delta \le y_j - f(x_j) \forall j}$
${\delta \le f(x_i) - y_i \; \forall_i}$
${\delta \in \mathbb{R}}$
${a \in \mathbb{R}^P}$
where ${f(x) = \sum\limits_{k=1}^P a_k \phi_k (x)}$

*Polar Coordinates*
![[Lesson 6 Types of Model Functions 2025-01-28 11.13.10.excalidraw]]

### Optimization Problems Modeled on Graphs/Networks

**Examples:** Shortest Path, Maximum Flow, Assignment Transportation, Coverings, Scheduling, etc.

*Covering Problem*

![[Lesson 6 Types of Model Functions 2025-01-28 11.16.33.excalidraw]]
${N = \{1,2,3,4,5,6\}}$
${E = \{(1,2), (1,3), (2,3), ..., (5,6)\}}$

Let's say we want to place smoke alarms in rooms (nodes) such that every room has at least one adjacent room with a smoke alarm (or has a smoke alarm).

Find a minimal set of nodes that *covers* the graph: Every node is either selected or adjacent to a selected node.

Consider the node-node adjacency matrix

${a_{ij} = \begin{cases} 1 & \text{if edge }(i,j) \in E \text{ or } i = j \\ 0 & \text{ if not} \end{cases}}$

${\begin{bmatrix} 1 & 1 & 1 & 0 & 0 & 0 \\ 1 & 1 & 1 & 1 & 0 & 1 \\ 1 & 1 & 1 & 1 & 1 & 0 \\ 0 & 1 & 1 & 1 & 0 & 1 \\ 0 & 0 & 1 & 0 & 1 & 1 \\ 0 & 1 & 0 & 1  & 1  & 1\end{bmatrix}}$

Let ${x_k =  \begin{cases}1 & \text{if node }k \text{ is selected} \\ 0 & \text{ if not} \end{cases}}$

${\min z = \sum\limits_{k=1}^6 x_k}$
${\text{s.t. } Ax \ge 1}$

${x \in \{0,1\}^6}$

___

### Shortest Path Problem

![[Lesson 6 Types of Model Functions 2025-01-28 11.34.46.excalidraw]]

${N = \{1,2,...,7\}}$
${E = \{(1,2),(1,3),(2,3),\}}$
${W = \{3,4,4,...,2\}}$

Node-edge adjacency matrix

${a_ij = \begin{cases} 1 & \text{if node } i \text{ is connected with edge j} \\ 0 & \text{otherwise} \end{cases}}$

${A = \begin{bmatrix} 1 & 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\ 1 & 0 & 1 & 1 & 1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\ 0 & 1 & 1 & 0 & 0 & 1 & 1 & 0 & 0 & 0 & 0 & 0 \\ etc.\end{bmatrix}}$

Let ${x_j = \begin{cases} 1 & \text{if edge j is in the path} \\ 0 & \text{otherwise} \end{cases}}$

Also let ${y_i = \begin{cases} 1 & \text{if node i in path} \\ 0 & \text{otherwise} \end{cases}}$

For the shortest path testing, we only need intermediary nodes to either have 0 or 2 edges connected, and the starting and ending node to only have 1.

Try: ${\min z = \sum\limits_{j=1}^{12} w_jx_j}$

${\text{s.t. }(Ax)_{i} = \begin{cases} 1 & \text{if }i \text{ if } i = k \text{ or } i = l \\ 0,2 & \text{otherwise} \end{cases}}$

${Ax = 2y \text { or } 1}$ - close, but not there
${Ax - Dy = b}$
${D_{kk} = D_{l\,l} = 0}$ beginning and ending nodes,
${D_{ii} = 2, D_{ij} = 0}$
${b_k = b_l = 1, b_i = 0}$

${Ax - 2y = 0 \text{ or } 1}$

${\begin{bmatrix} A & | & D \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} b \end{bmatrix}}$

### Assignment Problem

![[Lesson 6 Types of Model Functions 2025-01-30 11.05.40.excalidraw]]

${E = \{(i,j)\,|\, i \in A, j \in B\}}$
(*bipartite graph*)
${W = \{w_{ij} \in \mathbb{R}\,|\, (i,j) \in E\}}$

*Example.* Assign people (Set ${A}$) to teams (Set ${B}$) based on ability (${w_{ij}}$). Each team must have at least ${p}$ members. Each person can be on at most one team.

Let ${x_{ij} = \begin{cases} 1 & \text{if person } i \text{ is assigned to team }j \\ 0 & \text{otherwise} \end{cases}}$

${\max z = \sum\limits_{i=1}^m\sum\limits_{j=1}^n w_{ij} x_{ij}}$

${\text{s.t. }\sum\limits_{j=1}^n x_{ij} \le 1\\,\forall\,i}$
${\sum\limits_{i=1}^mx_{ij} \ge P \,\forall\,j}$
${x \in \{0,1\}^{mn}}$
${w}$ given, ${P = ()}$

### Another Example

Assign ${m}$ people to ${m}$ jobs.
(one job to each person)
minimize the time to complete all jobs.

Let ${w_{ij}}$ be the time a person ${i}$ to complete ${j}$ job.
Tasks can be performed simultaneously.

Let ${x_{ij} = \begin{cases} 1 & \text{if person } i \text{ is assigned task } j \\ 0 & \text{otherwise}\end{cases}}$
We will use constraints

${\sum\limits_{i=1}^m x_ij = 1\,\forall\,j}$
${\sum\limits_{j=1}^mx_ij = 1\,\forall\,i}$

What makes a good objective?
${\min T}$
${T \ge \sum\limits_{j=1}^m w_{ij}x_{ij} \,\forall\,i}$
${\sum\limits_{i=1}^m x_ij = 1\,\forall\,j}$ - task ${j}$ is completed
${\sum\limits_{j=1}^m x_ij = 1\,\forall\,i}$ - task ${i}$ each person gets one task
${x_ij \in \{0,1\}^{m^2}}$
${T \in \mathbb{R}}$