---
tags: CPT_S_223 Computer_Science
---

## *What Are Search Problems?*
- Finding a solution from a large set of possibilities.
- Common in AI, databases, networks, and optimization.
- For our case:
	- Let's simplify
	- Finding an element from a large collection

## *Searching in Linked Lists/Arrays*

Cost of accessing the next element
- ${O(1)}$

Cost of comparing the element to the query
- ${O(1)}$

At every step we compare and access the next element.
${O(1)}$

How many times do we do that in the worst case?
The value we are searching for is not in the list.
${O(n)}$

## *Binary Search*
${O(\log n)}$

## *Binary Search Tree (balanced)*

${O(\log n)}$

## *Binary Search Tree (unbalanced)*

${O(n)}$

## *Self-Balancing Search Tree*
- We can self balance binary search trees.
1. AVL Trees
2. Splay Trees
3. Red-Black Trees

We will see them next lesson!