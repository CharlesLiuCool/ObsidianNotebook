---
tags: CPT_S_223 Computer_Science
---

## *What is a Traversal?*

Traversal refers to *visiting all the nodes* in some order
Used in:
- Expressed evaluation
- Search operations
- Sorting
- etc.

## *Types of Binary Tree Traversal*

*Depth-First Traversals* (DFS)
- In-order (Left Root Right)
- Pre-order (Root Left Right)
- Post-order (Left Right Root)
*Breadth-First Traversal* (BFS)
- Also known as level-order traversal

*Note:* Binary Tree vs. Binary Search Tree
Binary tree  => two children per node
Binary search tree => sorted

## *In-order Traversal*

Search entire left subtree, root, then right subtree.
- Retrieves elements in sorted order
- Good for searching ${k}$-th smallest element
- Check tree for sortedness - validate tree

## *Pre-order Traversal*

Search root, left subtree, right subtree.
Searching in a *binary tree* (not *binary search tree*)
Generating *prefix* (polish) notation in Expression Trees

`+ 3 * 2 4` represents `(3 + (2*4))`

## *Post Order*

Search left, right, root

- Tree deletion (Memory Deallocation)
- Expression Tree Evaluation 
	- `(3+2) * (4-1)` ensures addition happens before multiplication
- Generating *postfix notation* (reverse polish notation)

## *Level-Order Traversal*

- Shortest path in an unweighted tree/graph
- Processing trees in real-world applications
- Building a binary heap

## *Complexity of AVL Trees*

${O(\log (n))}$

## *AVL Search*

- What is the complexity
- It's a balanced search tree

## *AVL Insert*

$O(\log n)$

- Complexity of insertion
	- Insert
		- Worst case complexity of inserting an element
		- $O(\log n)$
	- Update Balance Factor
		- After inserting the new leaf, you need to update balance factor
		- Of all the parent - grandparent of the leaf up to the root node
		- $O(\log n)$
	- If necessary, do rotations
		- At most six pointers need to be modified $O(1)$