---
tags: CPT_S_223 Computer_Science
---

## *Binary Heap*

A binary tree with two properties
- *Structure-Property*
	- Full tree
- *Order-Property*
	- *Min Heap*: parents <= children
	- *Max Heap*: parents >= children
	- (Note: <= means their can be duplicate priorities)

Height is ${\log_2(n)}$

We can implement *priority-queue* with a *binary heap* represented in an *array*.

To *dequeue*:
1. Take the root value away
2. Take the last added node, put it at root
3.  Percolate down (reliant on amount of children for complexity)

## *Leftist Heap*

*Null Path Length (NPL):* The null path length (NPL) of a node ${X}$ is the shortest path length from ${X}$ to a 'null'.
Path length -> number of nodes in-between
A node with zero or one child has an NPL of ${0}$.
Simply:
- Assume ${A}$ is a node which has two non-null children, ${B}$ and ${C}$
- NPL(${A}$) = Min (NPL(B), NPL(C)) ${+ 1}$

## *Leftist Heap Properties*

- *Heap Order Property*
	- A leftist heap follows the min-heap or max-heap order
	- For a min-heap, the parent's key is smaller than or equal to its children.
- *Leftist Property*

Solving NPL of node will appear on midterm.

## *Merging Leftist Tree*

1. Compare roots
2. ${R=}$ Merge(right subtree of smaller root, other tree)
3. Add ${R}$ as the new Right subtree (of the tree with smaller root)

