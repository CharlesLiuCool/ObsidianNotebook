---
tags: CPT_S_223 Computer_Science
---

## *Function*
What is a *Function*?
A function maps each element of a set A (domain) to exactly one element of a set B (codomain).
Representation: ${f: A \rightarrow B}$, where ${f(x)=y, x \in A, y \in B}$
Key Terms:
- *Domain*: Input set
- *Codomain*: Possible output set
- *Range*: Actual output set

### *Set-Theoretic Interpretation*
- A function is a relation that uniquely associates elements in one set (domain) with elements in another set (codomain).

### *Algebraic Interpretation*
- Functions can be represented as algebra formulas:
	- Example 1: ${f(x) = x^2}$
	- Example 2: ${g(x) = 2x+1}$
- Combining Functions:
	- Composition: ${f \circ g(x) = f(g(x))}$
- Inverse Function:
	- ${f^{-1}f(x) = x}$
- Especially useful when sets are infinite

### *Geometric Interpretation*
- Points on Cartesian plane: ${x, f(x)}$
- Examples:
	- ${f(x) = x:}$ Line
	- ${g(x) = x^2:}$ Parabola
	- ${h(x) = \log x:}$ Logarithmic curve
- Linear vs Non-linear functions
	- Linear: Straight line ${y = mx + c}$
	- Non-linear: Curves ${(y = x^2, y = \sin(x))}$

**Growth of Functions**
How functions behave as ${x}$ increases as ${x \to \infty}$
- Logarithmic grows slowest
- Linear is second slowest
- Factorial grows the fastest
- Exponential is the fastest

**Asymptotic notation**
- *Definition:* Describes the behavior functions as input grows large
- *Purpose:* Provides an upper bound, lower bound, or tight bound of a function's growth
- Independent of algorithms or computer science, applicable to any function.
*Key Idea:* Focus
- Dominant terms

## *Big-O Notation*
- Provides an upper bound for the growth of a function.
- Upper bounds provides the worst case estimate
- Soon, we will analyze and quantify the runtime of algorithms with respect to the size of input

If a function ${g(x)}$ can overtake another ${f(x)}$,
in other words,
${f(x) \in (g(x))}$ if there exists constants ${c > 0}$ such that ${f(x) \le c \cdot g(x)}$

**Big Omega Notation**
${f(x) \in \Omega(g(x))}$ if there exist constants ${c > 0}$ and ${x_0 > 0}$ such that:
${f(x) \ge c \cdot g(x), \forall x \ge x_0}$

**Big Theta Notation**
${f(x) \in \Theta(g(x))}$ if there exist constants ${c_1, c_2 > 0}$ and ${x_0 > 0}$ such that:
${c_1 \cdot g(x) \le f(x) \le c_2 \cdot g(x), \forall x \ge x_0}$

**Time Complexity**: How execution time grows with input size
**Space Complexity**: How memory usage grows with input size.

**Understanding Algorithm Analysis**
- Focuses on the growth rate rather than absolute execution time.
- Provides a mathematical framework to reason about performance
**Why not absolute time**?
- Machine Dependency: Execution time varies with:
	- Processor speed
	- System architecture
	- Programming and compiler
- Irrelevant time details

Steps for finding Upper Bounds - Big-O
1. Identify dominant term, exclude lower order terms and constants
2. Remove coefficients
3. Confirm the inequality

**Identifying Growth Patterns**
*Exponential*
Grows very fast!

*Geometric Progression*
${a, ar, ar^2, ar^3...}$

*Logarithmic Decay*
We start with ${8}$. So ${\log_28 = 3}$. It will take ${3}$ steps to fully decay to ${1}$

___

### *Call Stack and Stack Frames*
A *call stack* is a data structure that keeps track of a function calls in a program.
It operations in *Last in First Out (LIFO)* manner.
Helps in managing:
- Function invocations
- Local variables
- Return addresses

>[!question] What happens when a function is invoked?
> Each function call creates a stack frame.

A *stack frame* contains:
- Function arguments
- Local variables
- Return address (where to continue after the function finishes)
- Created when function is called and deleted after it is used.

```cpp
#include <iostream>

using namespace std;

int sumofn (int n) {
	if (n == 0) {
		return 0;
	}
	else {
		return n + sumofn(n-1);
	}
}
int main () {
	int input = 4;
	cout << sumofn(input) << endl;
	return 0;
}
```

```cpp
#include <iostream>
#include <stack>

int sum_of_stack(std::stack<int> &s) {
	if (s.empty()) {
		return 0;
	}
	int top = s.top();
	s.pop();
	return top + sum_of_stack(s);
}

int main (void) {
	std::stack<int> s;
	s.push(1);
	s.push(2);
	s.push(3); s.push(4);
	std::cout << sum_of_stack(s) << std::endl;
	return 0;
}
```