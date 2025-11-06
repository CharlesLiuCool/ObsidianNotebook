**Charles Liu**
Dr. Zhe Dang
$9/18/2025$

___

1. Let $L_1$ and $L_2$ be two regular languages. They are specified by the  
following regular expressions: $L_1 = 0(0 + 11)^*$ and $L_2 = 0^*11^*$.  
*(1).* Draw a DFA accepting $L_1$.

![[HW 3 2025-09-18 16.05.49.excalidraw |center]]

*(2).* Draw a DFA accepting $L_2$.

![[HW 3 2025-09-18 16.12.29.excalidraw |center | 300]]

*(3).* Draw a DFA accepting $L_1 \cap L_2$. 

![[HW 3 2025-09-19 20.39.11.excalidraw|center|500]]

*(4).* What is the regular expression for $L_1 \cap L_2$?  


$00^*11(11)^*$

___

2. A natural number can be encoded as a unary string. For instance, $5=$ the string of $aaaaa$. Therefore, we may treat a set of numbers as a language over a unary alphabet (that contains only one symbol, e.g., a). Write down the regular expression for the following sets of numbers: 

*(1).* all the $n$ such that $n \bmod 3 = 1$.

$a(aaa)^*$

*(2).* all the $n$ such that $n \bmod 3 = 0$ or $n \bmod 4 = 2$.  

$(aaa)^* + aa(aaaa)^*$

___

3. Show that deterministic FAs are closed under complement. That is, for any deterministic FA $M$, there is a deterministic FA $M'$ such that $L(M') = \Sigma^* - L(M)$, assuming that both $M$ and $M'$ have the same alphabet.  

>**Theorem** (Closed under complement)
>Given a deterministic finite automata $M$, there exists a deterministic finite automata $M'$ where
>$$L(M') = \Sigma^* - L(M)$$
>and $M$ and $M'$ both have alphabet $\Sigma$

>*Proof:*
> 
>*Construction*
>Let $q_1,...,q_n,...q_{n+k}$ be the states in a deterministic finite automata $M$, where $q_{n+j}$, $j= 0,...,k$, $k \in \Bbb{N}$ are the accepting states.
>1. For each state $q_i$, $i = 1,...,n-1$, turn $q_i$ into an accepting state.
>2. For each $q_{n+j}$ state, $j = 0,...,k$, turn $q_{n+j}$ into non-accepting states.
>3. Create a new "crash state", denote it $c$
>4. At every state $q_i$, $i = 1,...,n+k$, for every letter in alphabet $\Sigma$ where no transition exists from $q_i$ to another existing state with that letter, add a transition from $q_i$ to $c$.
>
>*Analysis*
>*Claim* A word $w \in \Sigma^*$ is rejected by $M$ if and only if $w$ is accepted by $M'$. 
>"$\Rightarrow$"
>Consider a word $w \in \Sigma^*$ that is rejected by $M$. Since it is rejected, it either ended at some non-accepting state $q_1,...,q_n$ in $M$ or at some arbitrary state $q_r$, $r \in \{1,...,n+k\}$ took an invalid transition and crashed.
>Case $1$: Ended at non-accepting state
>If the word when processed in the finite automata ends at a non-accepting state in $M$, it must end at an accepting state in $M'$ by $M'$'s construction (step $1$)
>Case $2$: Crash transition
>If it took some invalid transition in $M$ on state $q_r$, then by the construction of $M'$ (step $4$), a transition must be available to the crash state $c$ which is accepting.
> 
> Thus, $M$' must accept $w$.
>
>"$\Leftarrow$"
>Consider a word $w \in \Sigma^*$  that is accepted by $M'$. Since it is accepted by $M'$, it either ended an accepting state (a state in $q_1,...,q_n$ or $c$).
>Case $1$: Ended in $q_1,...,q_n$
>Suppose $w$ ends in $q_1,...,q_n$. These states are non-accepting in $M$, so $w$ must end up being rejected by $M$.
>Case $2$: Ended in crash state
>By the construction of the crash state, if $w$ ends in the crash state, it must've crashed in the original finite automata $M$ and therefore must've been rejected.

___

4. According to your proof of Problem 3, draw a deterministic finite automaton that accepts the complement of $(00 + 1)^*$. And also find a regular expression for the language accepted by $M'$.  

![[HW 3 2025-09-22 16.30.20.excalidraw|center]]

$$1^*0(01^*0)^*(1(0+1)^*+(01^*0)^*)$$

___

5. Let $L$ be a regular language on $\Sigma$ and $\Sigma' \subset \Sigma$. The result of dropping symbols in $\Sigma'$ from a word w is denoted by $w-\Sigma'$. For instance, $aaabacba^{-\{b\}}$ is $aaaaca$. Define $L-\Sigma' = \{w - \Sigma': w \in L\}$. That is, $L−\Sigma'$ is the result of dropping symbols in $\Sigma'$ from each word in $L$. Show that if $L$ is a regular language, then $L−\Sigma'$ is also a regular language. (Hint: use structural induction)

>**Theorem** (Dropping Symbols from Regular Language is Still Regular)
>Let $L$ be a regular language on $\Sigma$ and $\Sigma' \subset \Sigma$. $$L^{-\Sigma'} = \{w - \Sigma': w \in L\}$$ is also regular.

>*Proof:*
>We prove using structural induction.
>4. Take $L = \emptyset$. $L^{-\Sigma}$ must also be $\emptyset$ for arbitrary $\Sigma$, and is thus regular.
>5. Take $L = \{\Lambda\}$. $L^{-\Sigma}$ must be $\Lambda$ for arbitrary $\Sigma$, and is thus regular.
>6. Take $L = \{a\}$. If $a \in \Sigma$, $L^{-\Sigma} = \emptyset$ and is regular. If $a \notin \Sigma$, $L^{-\Sigma} = L = \{a\}$ which is regular.
>7. Assume $L_1^{-\Sigma}$ and $L_2^{-\Sigma}$ are regular
>	4.1. Take $L = L_1 \cup L_2$. We know $L^{-\Sigma} = L_1^{-\Sigma} \cup L_2^{-\Sigma}$, and union of regular is still regular so $L$ must be regular.
>	4.2. Take $L = L_1L_2$. We know $L^{-\Sigma} = L_1^{-\Sigma} L_2^{-\Sigma}$, and concatenation of regular is still regular so $L$ must be regular.
>	4.3 Take $L = L_1^*$. By definition, $L^{-\Sigma} = (L_1^*)^{-\Sigma} = (\bigcup_{i=0}^\infty (L_1)^i)^{-\Sigma} = \bigcup_{i=0}^\infty (L_1^{-\Sigma})^i$ which is the arbitrary union of regular languages, and must be regular.
>	
>Thus, by structural induction, $L^{-\Sigma}$ must be regular.

___