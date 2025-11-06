---
tags: CPT_S_223 Computer_Science
---

If you run an operation ${m}$ times, you can't get rid of that information in the Big-O notation.

e.g. ${O (m \log n)}$

## *Splay Trees*

**Simple yet powerful**
Access a node, make it the root with rotations.

- **Definition:** A splay tree guarantees that any ${M}$ consecutive operations, starting from an empty tree, take at most ${O(M \times \log N)}$ time.

- *Key Points*:
	- Single operations might take ${O(N)}$ but the *amortized cost* per operation is ${O(\log N)}$
	- Over a long sequence, some operations may take more time, other less.

The recently accessed node was moved to the root using rotation.
- **Restructuring Benefits:**
	- Accessing deep nodes brings related deep nodes closer to the root.
	- Balances the tree (to some extent) during restructuring
- Logic
	- Frequently accessed nodes are likely to be accessed again
		- *temporal locality*
	- Reduces average access times over multiple operations

**Zigzag** is bringing a node on the bottom of a LR/RL case to the top

**Zigzig** is bringing a node of the bottom of a LL/RR case to the top

The process of using *zig-zig* and *zig-zag* is called *splaying*.