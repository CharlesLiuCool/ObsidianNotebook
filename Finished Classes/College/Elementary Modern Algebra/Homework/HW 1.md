**Charles Liu**
Elementary Modern Algebra - Dr. Ben Clarke
January 18th 2025
___

1. Given the sets below, perform the following operations:  


$${A = \{0, 1, 2\},\;B = \{1, 2, 3\},\;C = \{0, 2, 4, 5\}}$$

*(a)* ${A \cap B \cap C}$  
By associativity,
${A \cap B \cap C = (A \cap B) \cap C = \{1,2\}\cap \{0, 2, 4, 5\} = \{2\}}$

*(b)* ${(A \cup B) − (B \cup C)}$  
${(A \cup B) − (B \cup C) = \{0,1,2,3\} - \{0,1,2,3,4,5\} = \{0\}}$

*(c)* ${(B \cap A) \cup (A \cap C)}$
${(B \cap A) \cup (A \cap C)= \{1,2\} \cup \{0,2\} = \{0,1,2\}}$

*(d)* ${B \times C}$ 
${\begin{align} B \times C = \{&(1,0), (1,2), (1,4), (1,5), (2,0), (2,2), (2,4), (2,5), (3,0), (3,2), \\ &(3,4), (3,5) \} \end{align}}$  

___

2. Given the sets below, determine if the claims are true or false. Justify your response  
$${X = \{0, 1, 2, 3, 4\}, Y = \{1, 3, 5, 7\}, Z = \{x \in \mathbb{R}\,|\,x > 0\} }$$

*(a)* ${(X \cup \emptyset) \subseteq Z}$  
False.

Since ${0 \in X}$ but ${0 \notin Z}$, ${(X \cup \emptyset) = X \not\subseteq Z}$.

*(b)* ${X \cap Y \neq \emptyset}$
True.
 ${X \cap Y = \{1,3\} \neq \emptyset}$
 
*(c)* ${|X \cap Z| = 4}$
True.
${X \cap Z = \{1,2,3,4\}}$, which means ${|X \cap Z| = |\{1,2,3,4\}| = 4}$.

*(d)* ${Y \cap Z \subseteq Z}$ 
True.
In general, for an element ${a \in Y \cap Z}$, ${a \in Z}$. Thus, ${Y.\cap Z \subseteq Z}$.

*(e)* ${3 \in X \cap Y \cap Z}$
True.
Since ${3 \in X}$, ${3 \in Y}$, and ${3 \in Z}$, ${3 \in X \cap Y \cap Z}$.

___

3. Let ${n}$ be a positive integer, and let ${A_i}$ be an arbitrary subset of ${X}$ for each ${i \in Z}$.  
Prove DeMorgan’s laws:  

*(a)* ${X - \bigcap_{i=1}^n A_i = \bigcup_{i=1}^n (X - A_i)}$

**Theorem.** ${X - \bigcap_{i=1}^n A_i = \bigcup_{i=1}^n (X - A_i)}$
*Proof.*
For any set ${D \subseteq X}$, let ${D^c = X - D}$. 
Let ${n}$ be a positive integer, and let ${A_i}$ be an arbitrary subset of ${X}$ for each ${i \in Z}$. It suffices to show ${(\bigcap_{i=1}^n A_i)^c = \bigcup_{i=1}^n (A_i)^c}$.

*Lemma 1.* ${(\bigcap_{i=1}^n A_i)^c \subseteq \bigcup_{i=1}^n (A_i)^c}$
*Proof.*
Let ${y \in (\bigcap_{i=1}^n A_i)^c}$. We want to show ${y \in \bigcup_{i=1}^n (A_i)^c}$. Since  ${y \in (\bigcap_{i=1}^n A_i)^c}$, we can see that ${y \notin \bigcap_{i=1}^n A_i}$. Therefore, ${y \notin A_1}$ or ${y \notin A_2}$, or ... ${y \notin A_n}$. Thus, ${y \in A_1\,^c}$ or ${y \in A_2\,^c}$, or ... ${y \notin A_n\,^c}$. By definition of union, ${y \in \bigcup_{i=1}^n (A_i)^c}$. Thus, ${(\bigcap_{i=1}^n A_i)^c \subseteq \bigcup_{i=1}^n (A_i)^c}$.

*Lemma 2.* ${\bigcup_{i=1}^n (A_i)^c \subseteq (\bigcap_{i=1}^n A_i)^c}$
*Proof.*
Let ${z \in \bigcup_{i=1}^n (A_i)^c}$. We want to show ${z \in (\bigcap_{i=1}^n A_i)^c}$. Since ${z \in \bigcup_{i=1}^n (A_i)^c}$, ${z \in A_1\,^c}$ or ${z \in A_2\,^c}$, or ... ${z \in A_n\,^c}$. So ${z \notin A_1}$ or ${z \notin A_2}$ or ... ${z \notin A_n}$. So we can see that, ${z \notin (\bigcap_{i=1}^n A_i)}$ so ${z \in (\bigcap_{i=1}^n A_i)^c}$. Thus, ${\bigcup_{i=1}^n (A_i)^c \subseteq (\bigcap_{i=1}^n A_i)^c}$.

Because of Lemma 1 and Lemma 2,
$${\left(\bigcap_{i=1}^n A_i\right)^c = \bigcup_{i=1}^n (A_i)^c}$$.


*(b)* ${X - \bigcup_{i=1}^n A_i = \bigcap_{i=1}^n (X - A_i)}$

**Theorem.** ${X - \bigcup_{i=1}^n A_i = \bigcap_{i=1}^n (X - A_i)}$
*Proof.*
For any ${D \subseteq X}$ ,let ${D^c = X - D}$. It suffices to show ${\left(\bigcup_{i=1}^n A_i\right)^c = \bigcap_{i=1}^n A_i^c }$. By part ${(a)}$, we know ${(\bigcap_{i=1}^n B_i)^c = \bigcup_{i=1}^n (B_i)^c}$ for any ${B_i \subseteq X}$ where ${i = 1,2, \ldots n}$.
By taking the complement of both sides, we can find that ${\bigcap_{i=1}^n B_i = (\bigcup_{i=1}^n (B_i)^c)^c}$.
Set ${B_i = (A_i)^c}$. Then ${(B_i)^c = ({A_i^c})^c = A_i}$ for ${i = 1,2, ...n}$.

So the above equation becomes

$${\bigcap_{i=1}^n A_i^c = \left(\bigcup_{i=1}^n A_i\right)^c}$$
___

4. Prove or provide a counter example to the following claims about set operations:  

*(a)* The union of two sets is commutative.  
**Theorem.** The union of two sets is commutative.
*Proof.*
Suppose we have two sets ${A}$ and ${B}$. Suppose there is an element ${x}$ which is in ${A \cup B}$. By definition of union, it must be in sets ${A}$ or ${B}$. This means ${x}$ is also in ${B \cup A}$, which means ${(A \cup B) \subseteq (B \cup A)}$
Likewise, suppose we have an element ${y}$ in ${B \cup A}$. Since it is in ${B}$ or ${A}$, it must be in ${A \cup B}$. Therefore, ${B \cup A \subseteq A \cup B}$
Since ${A \cup B \subseteq B \cup A}$ and ${B \cup A \subseteq A \cup B}$, we can see that ${A \cup B = B\cup A}$, so the union of two sets is commutative.


*(b)* The union of two sets is associative.  
**Theorem.** The union of two sets is associative.
*Proof.*
Suppose we have three sets ${A, B, C}$. Let ${x}$  be an element in ${(A \cup B)\cup C}$. By definition of union, it must be in one ore more of the sets ${A, B}$ and ${C}$. Therefore, it must also be in ${A \cup (B \cup C)}$, which means ${(A \cup B) \cup C \subseteq A \cup (B \cup C)}$.
Similarly, let ${y}$ be any element in ${A \cup (B \cup C)}$. By definition of union, it must be in one or more of the sets ${A, B}$ and ${C}$. Therefore, it must also be in ${(A \cup B) \cup C}$, which means ${A \cup (B \cup C) \subseteq (A \cup B) \cup C}$. 
Since ${(A \cup B) \cup C \subseteq A \cup (B \cup C)}$ and ${A \cup (B \cup C) \subseteq (A \cup B) \cup C}$, ${(A \cup B) \cup C = A \cup (B \cup C)}$, so the union of two sets is associative.

*(c)* The intersection of two sets is commutative.  
**Theorem.** The intersection of two sets is commutative.
*Proof.*
Suppose we have two sets ${A}$ and ${B}$. Let ${x}$ be an element in ${A \cap B}$. By the definition of intersection, ${x}$ must be in both ${A}$ and ${B}$. Thus, it must also be in ${B \cap A}$. Therefore, ${A \cap B \subseteq B \cap A}$.
Likewise, let ${y}$ denote any element in ${B \cap A}$. By definition of intersection, ${y \in B}$ and ${y \in A}$, so it must also be in ${A \cap B}$. This means ${B \cap A \subseteq A \cap B}$.
Since ${A \cap B \subseteq B \cap A}$ and ${B \cap A \subseteq A \cap B}$, ${A \cap B = B \cap A}$. Thus, the intersection of two sets is commutative.

*(d)* The intersection of two sets is associative.  
**Theorem.** The intersection of two sets is associative.
*Proof.*
Suppose we have three sets ${A, B, C}$. Let ${x}$ be an element in ${(A \cap B) \cap C}$. By definition of intersection, ${x}$ must be in ${A}$, ${B}$, and ${C}$. This means it is also in ${A \cap (B \cap C)}$, so ${(A \cap B) \cap C \subseteq A \cap (B \cap C)}$.
Similarly, let ${y}$ be an element in  ${A \cap (B \cap C)}$. By definition of intersection, ${x}$ must be in ${A}$, ${B}$, and ${C}$. This means it is also in ${(A \cap B) \cap C}$, so ${A \cap (B \cap C) \subseteq (A \cap B) \cap C}$.
Since ${(A \cap B) \cap C \subseteq A \cap (B \cap C)}$ and ${(A \cap B) \cap C}$, so ${A \cap (B \cap C) \subseteq (A \cap B) \cap C}$, ${(A \cap B) \cap C = A \cap (B \cap C)}$, so intersection is associative.

*(e)* The Cartesian product of two sets is commutative. 
**Theorem.** The Cartesian product of two sets is *not* commutative.
*Proof.*
Suppose ${A = \{0,1\}}$ and ${B = \{2,3\}}$.
${A \times B = \{(0,2), (0,3), (1,2), (1,3)\} \neq B \times A = \{(2,0), (2,1), (3,0), (3,1)\}}$
Thus, the Cartesian products between two sets are not commutative.

*(f)* The Cartesian product of two sets is associative.
**Theorem.** The Cartesian product of sets is *not* associative.
*Proof.*
Suppose there are three sets ${A, B, C}$, where ${A = \{0,1\}}$, ${B = \{2,3\}}$, and ${C = \{4,5\}}$.
Then ${\begin{align} (A \times B) \times C &= \{(0,2),(0,3),(1,2),(1,3)\} \times \{4,5\} \\ &= \{(0,2,4), (0,3,4), (1,2,4), (1,3,4), (0,2,5), (0,3,5), (1,2,5), (1,3,5)\} \end{align}}$

In contrast, ${A \times (B \times C) = \{0,1\} \times (\{(2,4),(2,5),(3,4),(3,5)\}}$

Since ${(A \times B) \times C \neq A \times (B \times C)}$, the Cartesian product of sets is *not* associative.
___