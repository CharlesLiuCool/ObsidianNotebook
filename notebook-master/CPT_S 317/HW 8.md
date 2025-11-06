**Charles Liu**
Dr. Zhe Dang
$11/1/2025$

___

1. Construct a DPDA to accept language $\{0^n1^{3n} : n \ge 1\}$. You need write down the explicit construction.  

$\delta (q_0, 0, *_1) = \{(q_1, 000*_1)\}$ where $*_1 = Z0 \text{ or } 0$ `// Each time you read 0 on the stack head or 0's, put three zeroes on top of stack. Change state to show you've read at least something (n >= 1 condition)`

$\delta(q_1, 1,0) = \{q_1, \Lambda\}$ `// If you read 1 and 0 is top of stack, pop it off`

$\delta (q_1, \Lambda, Z_0) = \{(q_2, Z_0)\}$ `//If we've popped everything off the stack (stack is empty, top is Z0) and we've also finished reading our inputs, the string must've satisfied the language and we accept`

$q_2$ = accepting state

___

2. Construct a PDA to accept language $\{w \in \{0, 1\}^* : \#_0(w) \ge \#_1(w)\}$. (It is fine you describe how your machine works in English.)  

We design PDA as follows.
First create a "mode" $m$ that can be on or off, start it at off.
If $m$ is off
1. When we read a $0$ we push to the stack of the PDA
2. When we read a $1$:
	1. If the stack is not empty (top isn't $Z_0$, its $0$), we pop from the stack
	2. If the stack is empty (top is $Z_0$), we switch mode $m$ to on, and push $1$ to the stack.

If $m$ is on
1. When we read a $1$, we push to the stack of the PDA
2. When we read a $0$:
	1. If the stack is not empty (top isn't $Z_0$, its $1$), we pop from the stack
	2. If the stack is empty (top is $Z_0$), we switch mode $m$ to off, and push $0$ to the stack.

The PDA only accepts at the end if the top of the stack is $0$ or $Z_0$ (which means either after reading, it counted more $0$'s than $1$'s, or equal amount respectively), which satisfies the language criteria.
___

3. Construct a PDA to accept language $$L = \{w \in \{0, 1\}^* : \text{each prefix of } w \text{ is in the language defined in Problem } 2. \}$$ 
You need also write down the explicit construction. (This is actually an easy problem. First, you have to understand the language. For instance $0001100111001 \in L$, but $001110 \notin L$. why? Since $w \in L$ requires that each prefix of $w$ contains more or the same number of $0$’s than $1$’s.)  

$\delta(q_0, 0, *_1) = \{(q_1, 0*_1)\}$, where $*_1 = 0, Z_0$ `// Always push 0 (switch state to show something is read)`
$\delta(q_1, 1, 0) = \{q_1, \Lambda\}$ `// Always pop 1`
$\delta(q_1, \Lambda, Z_0) = \{q_2, *_1\}$ `// At the end, only when there are zeroes left or stack is empty will we accept`

$q_2$ = accepting state

___

4. Let $L$ be a language accepted by a PDA $M$ . Define $$\text{Prefix}(L) = \{x : \text{ there exists } y \text{ such that } xy \in L\}$$
Describe a construction of a PDA $M$' accepting $\text{Prefix}(L)$. (You only need to describe in English how $M$' works.)  

First, $M$' simulates $M$ on input $x$ with its own stack. After reading input $x$, $M'$ guesses input symbols in the alphabet symbol by symbol and continues simulating $M$, until at some point it guesses to stop. It then checks $M$, if its at an accepting state it returns yes, otherwise it aborts.

$$M' \text{ accepts on }x \iff x \in L(M') \iff \exists \;y \text{ s.t. } xy \in L(M)$$

___

5. Consider the following pseudo-C code:  
```c
int x = 0;
char d;

while (1) {
	d = getchar();
	
	// when reads EOF (end of the input)
	// get out of the while loop
	if (d == EOF) break;
	
	if (d == 'a' || d == 'b') x++;
	if (d == 'c') x--;
}

// get here after breaking the loop
// write yes to stdout
if (x == 0) putchar('y');
```

This program writes ’y’ (yes) to stdout (your screen) for some particular sequences of input characters (i.e., strings). These strings form a language $L$. Construct a PDA to accept $L$. (What we learn from this problem is that a program with one integer variable can always be simulated by a PDA.)


$\delta(q_0, *_1, *_2) = \{(q_0, *_1*_2)\}$  `// (mode 1) always push when a or b is read`
$\delta(q_0, c, *_1) = \{(q_0, \Lambda)\}$ `// if c is read, and a,b top of stack, pop`
$\delta(q_0, c, Z_0) = \{(q_1, cZ_0)\}$ `// if c is read and stack is empty, start (mode 2) to where c is push, a,b is pop`
$\delta(q_1, c, c) = \{q_1, cZ_0\}$ `// if c is read and c is top of stack and we are in mode 2, keep pushing`
$\delta(q_1, *_1, c) = \{q_1, \Lambda\}$ `// pop on a,b when in mode 2`
$\delta(*_3,EOF, Z_0) = \{q_2, Z_0\}$ `// if stack is empty at end, accept`
where $*_1 = a$ or $b$, $*_2 = a,b$ or $Z_0$, and $*_3 = q_0$ or $q_1$

$q_2$ = accepting state.

___