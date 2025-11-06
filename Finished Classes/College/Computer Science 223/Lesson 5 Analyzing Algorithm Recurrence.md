---
tags: CPT_S_223 Computer_Science
---

## *Total Work*
Total amount of work:
Left subtree + right subtree

If the function calls itself 'n' times.
It will have 'n' subtrees
The total work ${= \sum\limits_{k=0}^n}$ Work done (subtree ${n}$)
Constant if ${n \le 1}$

## *Binary Search*
- Problem Statement: Find the position of a target value in a sorted array
- *Preconditions:* Array is sorted

The area of search starts with whole array of size '${n}$'
At each step the area of search shrinks to ${n/2}$
The operation we do at each step
- Compare middle element
- Based on outcome of comparison, recursively search left half, right half, or return.