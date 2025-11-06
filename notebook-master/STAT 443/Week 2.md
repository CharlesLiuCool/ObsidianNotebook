### **Probabilistic Modeling**

Three basic ingredients
- Sample Space $S$
- $\sigma$-field $F$: It consists of all events $E$'s
- Probability measure $\Bbb{P}(E)$

>*Motivation for Conditional Probability Measures*
>- If you know more relevant information, you should be able to estimate probabilities better
>- The probability $\Bbb{P}(E)$ can be calculated by analyzing what could possibly happen under various possible scenarios


>**Definition**
>Let $A$ and $B$ be two events with $\Bbb{P}(B) > 0$. the conditional probability of $A$ given that $B$ occurs is defined as 
>$$\Bbb{P}(A|B) := \dfrac{\Bbb{P}(A \cap B)}{\Bbb{P}(B)}, A,B \subseteq S$$

*Remark:*

- For a fixed $B \subseteq S$, let

$$\Bbb{Q}(E) := \Bbb{P}(E | B), E \subseteq B \,(\text{not necessarily required})$$

Then $\Bbb{Q}(E)$ is a (conditional) probability measure on the reduced sample space $B$ and the $\sigma$-field of events $E$, within $B$.

- If $\Bbb{P}(B) = 0$, then the conditional probability $P(\cdot | B)$ can be defined by using the Radon-Nikodym derivative from measure theory

### **The Multiplication/Product Rule**

>**Theorem**
>1. For any two events $A_1, A_1 \subseteq S$,
>$$\Bbb{P}(A_1 \cap A_2) = \Bbb{P}(A_1 | A_2) \Bbb{P}(A_2) = \Bbb{P}(A_2|A_1)\Bbb{P}(A_1)$$
>2. For any three events $A_1,A_2,A_3 \subset S$
>$$\Bbb{P}(\underbrace{A_1 \cap A_2}_B \cap A_3) = \Bbb{P}(A_3|\underbrace{A_1 \cap A_2}_B)\Bbb{P}(\underbrace{A_1\cap A_2}_B) $$
>$$= \Bbb{P}(A_3 | A_1 \cap A_2)\Bbb{P}(A_2|A_1)\Bbb{P}(A_1)$$
>3. This can be extended to multiple events

### **Total Probability Law**

>**Theorem**
>For any events $A,B \subseteq S$
>$$\Bbb{P}(B) = \Bbb{P}(A \cap B) + \Bbb{P}(A' \cap B) = \Bbb{P}(B|A)\Bbb{P}(A) + \Bbb{P}(B|A')\Bbb{P}(A')$$

>**Theorem**
>1. Events $\{A_1, A_2,...,A_k\}$ constitutes a *partition* of sample space $S$ if they are mutually exclusive and $\bigcup_{i=1}^kA_i=S$
>2. For any event $B$,
>$$\Bbb{P}(B) = \sum\limits_{i=1}^k\Bbb{P}(A_i \cap B) = \sum\limits_{i=1}^k\Bbb{P}(A_i)$$
>where $\Bbb{P}(B|A_i), i=1,...,k$, are usually "easier" to calculate


*Proof:*
Take the intersections on both sides of $S=\bigcup\limits_{i=1}^k A_i$ and we have
$$B=S\cap B = \bigcup_{i=1}^k (A_i \cap B)$$
where $A_i \cap B$ and $A_k \cap B$ are mutually exclusive, $i \neq j$. Thus
$$\Bbb{P}(B) = \sum\limits_{i=1}^k \Bbb{P}(A_i \cap B)$$
Using the multiplication rule, this becomes
$$\Bbb{P}(B) = \sum\limits_{i=1}^k \Bbb{P}(B|A_i)\Bbb{P}(A_i)$$

### **Bayes' Rule**

>**Theorem**
>Let $\{A_1,A_2,...,A_k\}$ be a partition of a sample space $S$. For any events $B \subseteq S$,
>$$\Bbb{P}(A_j|B) = \dfrac{\Bbb{P}(A_j \cap B)}{\Bbb{P}(B)} = \dfrac{\Bbb{P}(B|A_j)\Bbb{P}(A_j)}{\sum\limits_{i=1}^k\Bbb{P}(B|A_i)\Bbb{P}(A_i)},\;j = 1,...,k$$

![[4. Probability Axioms 2025-08-28 15.49.59.excalidraw|600]]

### **"Learning" via Bayes' Rule**

Let $H$ be an event of interest, and $E$ be an event representing the evidence
$$\Bbb{P}(H|E) = \dfrac{\Bbb{P}(H) \cdot \Bbb{P}(E|H)}{\Bbb{P}(E)}$$

### **Independence**

- Two events $A$ and $B$ are independent if $\Bbb{P}(A|B) = \Bbb{P}(A)$
- The Product Form: Two events $A$ and $B$ are independent is equivalent to that $\Bbb{P}(A \cap B) = \Bbb{P}(A)\Bbb{P}(B)$
- *Independence and mutually exclusive are different*. Two mutually exclusive events are in fact highly dependent
	- Consider $A \cap B = \emptyset$
	- If $A$ occurs, $B$ must not (highly related)
- If $A$ and $B$ are independent, then
$$\Bbb{P}(A \cup B) = \Bbb{P}(A) + \Bbb{P}(B) - \Bbb{P}(A \cap B) = \Bbb{P}(A) + \Bbb{P}(B) - \Bbb{P}(A)\Bbb{P}(B)$$

>**Definition** Events $A_1$, $A_2$,...,$A_n$ are mutually independent if for any subset $\{i_1,...,i_k\} \subseteq \{1,...,n\}$,
>$$\Bbb{P}(A_i \cap ... \cap A_{i_k}) = \Bbb{P}(A_{i_1} \times ... \times \Bbb{P}(A_{i_k}))$$

*Remark*
- Two events $A$ and $B$ are independent $\iff$ $A$ and $B'$ are independent. In fact, $A$ and $B$ are independent $\iff$
$$\Bbb{P}(A \cap B) = \Bbb{P}(A)\Bbb{P}(B) \iff \Bbb{P}(A) - \Bbb{P}(A \cap B) = \Bbb{P}(A) - \Bbb{P}(A)\Bbb{P}(B)$$ $$\iff \Bbb{P}(A \cap B') = \Bbb{P}(A)[1-\Bbb{P}(B)] = \Bbb{P}(A)\Bbb{P}(B)$$

- Two events $A$ and $B$ are independent $\iff$ $A'$ and $B'$ are independent
- Two events $A$ and $B$ are independent $\iff$ $f(A)$ and $g(B)$ are independent, for any Borel-measurable functions $f$ and $g$


### **The Product Rule for Ordered Pairs**

> **Count all possible pairs (O,P)**
> The first element $O$ can be selected in $n_1$ ways
> The second element $P$ can be selected in $n_2$ ways
> The pair $(O,P)$ can be selected in $n_1n_2$ ways


### **Permutations and Combinations**

Consider a set of $n$ distinct objects, and $0\le k\le n$.

>**Definition**
>- An *ordered* sequence of $k$ from the $n$ objects
>- An *unordered* subset is called a combination
>- $\binom{n}{k} = \# \text{ of all combinations of size } k \text{ from the } n \text{ objects}$


$_nP_k = k!\binom{n}{k}$

Consider a set of $n$ distinct objects, and $0 \le k \le n$

### **Multinomial Coefficient**

$$\binom{n}{r_1}\binom{n-r_1}{r_2}...\binom{n-r_1-r_2 ...r_k}{r_k} = \dfrac{n!}{r_1!r_2!...r_k!}$$