---
tags: CPT_S_223 Computer_Science
---

### *Algorithmic Efficiency of BST*
${O(H)}$ where ${H}$ is the height of the tree.

- Balanced binary search tree
	- Complexity for searching: ${O(\log n)}$
- Binary search tree (unbalanced)
	- We will always assume the worst!
	- Complexity for searching ${O(n)}$
- How can I make sure that my binary tree is balanced?
- We can implement self-balancing binary search tree
1. AVL Trees
2. Splay Trees
3. Red-black trees

## *AVL Trees*
- Adelson-Velsky & Landis
- Balances using rotations after insertions/deletions
- Guarantees ${O(\log n)}$ height for efficient operations

### *Binary Search Tree Property*

Every node in the left subtree is lesser than the node, every node in the right subtree is greater
Each node has at most two children

### *New Property (AVL Property)*

For every node, the *height difference* between left and right subtrees should be *less than or equal to one*.

Balance factor = RH - LH
|Balance factor| ${ \le 1}$

If ${RH - LH > 0}$ or the balance factor is greater than ${0}$, the tree is right heavy.
If ${LH - RH > 0}$ or the balance factor is less than ${0}$, the tree is left heavy.

## *Balance Factor*

${BF = \{-1,0,1\}}$ then it satisfies ${AVL}$ property
${|BF| \ge 1}$ then it's not
Balance factor is not for a 'tree', its for each node since each node is a root of a subtree.

### *Four Cases*
- *LL Case*: Root tree is left heavy and left subtree is also left heavy
	- Perform a right rotation
- *RR Case:* Root tree is right heavy and right subtree is also right heavy
	- Perform a left rotation
- *LR Case:* Root tree is left heavy and right subtree is also right heavy
	- Perform a right rotation on left subtree and left rotation on the root tree
- *RL Case:* Root tree is right heavy and right subtree is left heavy
	- Perform a left rotation on right subtree then a right rotation on root tree