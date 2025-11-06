---
tags: CPT_S_223 Computer_Science
---

### *Strictly Self-Balancing Binary Search Trees*

- Self-balancing Binary Search Trees (BSTs) maintain their height at $O(\log n)$
- Ensures efficiency
	- Insertions
	- Deletions
	- Search

1. *AVL Trees*
	- Maintains strict balance by ensuring the height difference between left and right subtrees is at most ${1}$.
2. *Red-Black Tree*
	- Allows some imbalance but ensures logarithmic height using color-based balancing (red/black properties) 
3. *Weight-Balanced Tree (WBT)*
	-  Ensures balance by tracking node sizes and keeping left and right subtree sizes within a constant factor.
4. *AA Tree*
	- A simplified variant of Red-Black Trees where red nodes are only allowed as right children, reducing complexity.

As Subu calls these trees, *$S^2B^2$ Search Trees* (Strictly self-balancing binary search tree). This means all operations (insertion, deletion, search) are $O(\log n)$.

### *Balanced-ish Binary Search Trees*

While not strictly $O(\log(n))$ in worst-case scenarios, these trees provide adaptive balancing or probabilistic balance, making them useful in specific contexts.

5. *Splay Tree*
	- Moves frequently accessed nodes closer to the root using amortized balancing
6. *Treap*
	- Uses randomized rotations based on priority values to maintain probabilistic balance.

*Binary Search Tree* is an *data structure* because its a specific implementation.

We can use the *set* ADT for this, because there is no duplicate elements in a BST.

## *Set ADT to implement $S^2B^2$ Tree*
What do we need?
- Insert
- Delete
- Contains (x element)
- And no duplicates

## *Key Value Pairs*

Pairs an index with a template in a class in a set. Use a $S^2B^2$ tree for finding/sorting/etc.
That's how `C++` works.

___

## *Code Practice*

`mapPractice.cpp`
```cpp
#include <iostream>
#include <map>
#include <string>

using namespace std;

class Student {
public:
	int studentId;
	string fname;
	string lname;	
	Student(int id, string fn, string ln):studentId(id), fname(fn), lname(ln){}
	//print function for Student class
	friend ostream &operator<<(ostream &os, const Student &s) {
		os << "ID: " << s.studentId << "First name: " << s.fname;
		os << "Last name: " << s.lname << endl; 
		return os;
	}
};

int main() {
	map<int, Student> studentMap;

	//three different ways to populate map
	
	Student s1(101,"Alice", "Johnson");
	studentMap.insert((s1.studentId, s1));

	Student s2(102, "Subu", "Kandaswamy");
	pair<int, Student> studentPair(s2.studentId, s2);
	studentMap.insert(studentPair);

	studentMap.emplace(103, Student(103, "John", "Doe"));

	//three different ways to find elements in map

	auto it = StudentMap.find(101);
	if (it != studentMap.end()) {
		cout << it->second << endl;
	} else {
		cout << "Student not found" << endl;
	}

	for (const auto &pair: studentMap) {
		cout << pair .second;
	}
	
	return 0;
}
```