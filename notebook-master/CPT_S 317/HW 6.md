**Charles Liu**
Dr. Zhe Dang
$10/12/2025$

___

1. Show that there is an algorithm to decide whether, given a regular language $L$, there is a word that ends with $a$ in $L$.

Define $\text{End}(L,a) = \{w \in L: w \text{ ends with }a\}$

*Claim:* $\text{End}(L,a)$ is regular
1. Consider $L = \emptyset$, $\text{End(L,a)}$ is $\emptyset$ which is regular
2. Consider $L = \{ \wedge \}$, we know that doesn't end in $a$ so $\text{End}(L,a)$ is $\emptyset$ which is regular
3. Consider $L = \{b\}$,  where $b$ could equal $a$ or not. If $b=a$, we know $\text{End}(L,b) = \{a\}$ which is regular. Likewise, if $b \neq a$, $\text{End}(L,b) = \emptyset$ which is regular.
4. Consider arbitrary regular languages $L_1$ and $L_2$. If $\text{End}(L_1, a)$ and $\text{End}(L_2, a)$ are regular languages, then:
	1. Consider $L = L_1 \cup L_2$. We know $\text{End}(L,a) = \text{End}(L_1, a) \cup \text{End}(L_2, a)$ is a union of regular languages which is regular.
	2. Consider $L = L_1L_2$. Consider if $L_2 \neq \Lambda$. That means the ending of $L$ depends on $L_2$, so $\text{End}(L_1L_2, a) = L_1\text{End}(L_2,a)$, which is the concatenation of regular languages and thus regular. Next consider if $L_2 = \Lambda$. Then the ending depends on $L_1$, so $\text{End}(L_1L_2, a) = \text{End}(L_1,a)$ which is also regular.
	3. Consider $L = L_1^*$. We know that the ending depends on $L_1$ and the prefix is just some power of $L_1$, so $\text{End}(L,a) = L_1^*\text{End}(L_1,a)$, which is regular.

There is a word that ends in $a$ in $L$ if and only if
$$\text{End}(L,a) \neq \emptyset$$
We can use the DFS algorithm to find the emptiness algorithm to check if the accepting state is reachable from starting state, so an algorithm exists.

___

2. Show that we have an algorithm to check: given two FAs $M_1$ and $M_2$, whether there exists a word $x$ such that $x$ is accepted by $M_1$ but not accepted by $M_2$, or $x$ is accepted by $M_2$ but not accepted by $M_1$

We define $L = \{x: (x \in L(M_1) \wedge x \notin L(M_2)) \lor (x \in L(M_2) \wedge x \notin L(M_1)\}$

*Claim:* $L$ is regular
We notice $L = (L(M_1) \cap \overline{L(M_2)}) \cup (L(M_2) \cap \overline{L(M_1)})$

By Kleene theorem, since $L(M_1)$ and $L(M_2)$ are regular, the intersection and complement of them preserve regularity, so $L$ is regular.

So it is equivalent for the question's formulation to build an algorithm that checks $L\neq\emptyset$, which can be built with a DFS algorithm from starting to accepting states. Thus, an algorithm exists.

___

3. Show that $L^r = \{x^R : x \in L\}$ is regular if $L$ is regular. ($x^R$ is the reverse of $x$, e.g., $aab^R = baa$)

**Theorem.** $L^r$ is regular
*Proof:*
Suppose $L$ is regular.
We can construct $M$ which is the finite automata that accepts $L$. We define a new NFA $M'$ which has the same states as $M$ except the accepting states become the starting states, and the starting state becomes an accepting state. We add a transition to $M'$ between states if the same transition exists in $M$ between those same states, except that transition is reversed (e.g. let $p,q$ be states in $M$, and $p \to q$ which takes $a$ be a transition in $M$, then in $M'$ we add $q \to p$ which takes $a$).

Notice that for any $x = a_1a_2...a_n \in L(M)$, then $x$ is accepted by $M$, which means $x^r = a_na_{n-1}...a_1$ must be accepted by $M'$ and $x^r \in L(M')$.

We can use subset construction to turn NFA $M'$ into a DFA. Thus, if $L$ is regular, then $L(M') = L^r$ is regular.

___

4. Show that $\text{Prefix}(L) = \{x: \text{ for some }y, xy \in L\}$ is regular if $L$ is regular.

**Theorem.** $\text{Prefix}(L)$ must be regular if $L$ is regular.
*Proof:*
Assume $L$ is regular. Let FA $M$ accepting regular language $L$. We will construct FA $M'$ to accept $\text{Prefix}(L)$. $M'$ runs on input $x$ as follows. For each symbol $M'$ reads, it simulates $M$ on the same symbol. At the end of $x$, $M'$ guesses symbol by symbol a word called $y$, and lets $M$ run on the guessed $y$. $M'$ says yes on $x$ if $M$ says yes on $xy$. Clearly $M'$ accepts $\text{Prefix}(L)$. Thus, $\text{Prefix}(L)$ must be regular.


___

5. Show that $\text{Half}(L) = \{x : \text{ for some }y, xy \in L \text{ and } |x| = |y|\}$ is regular if $L$ is regular.

**Theorem.** $\text{Half}(L)$ must be regular if $L$ is regular.
*Proof:*
Let $M$ be the FA accepting regular language $L$. We will construct FA $M'$ to accept $\text{Prefix}(L)$. $M'$ runs on input $x$ as follows. For each symbol $M'$ reads, it simulates two copies of $M$, $M_1$ and $M_2$ in parallel. First copy $M_1$ runs on $x$, second copy on a guessed $y$. $M_2$ starts with the guessed state $q$. At the end of $x$, $M'$ says yes on $x$ if $M_1$ ends up state with state $q$ and $M_2$ ends up with an accepting state. Clearly $L(M') = \text{Half}(L)$. Thus, $\text{Half}(L)$ must be regular if $L$ is regular.

___