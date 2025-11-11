**Charles Liu**
Dr. Zhe Dang
$11/10/2025$

___

1. Given a grammar $G$  
$$S \to aaB|bbA|AB|aabb$$ 
$$A \to BA|aB|a$$  
$$B \to AB|bA|b$$
Construct a PDA accepting $L(G)$.

$\delta(q_0, \Lambda, Z_0) = \{(q_1, SZ_0)\}$

$\delta(q_1, *_1, *_1) = \{(q_1, \Lambda)\}, *_1 = a,b$
$\delta(q_1,\Lambda,S) = \{(q_1,aaB), (q_1,bbA), (q_1,AB),(q_1,aabb)\}$
$\delta(q_1, \Lambda, A) = \{(q_1, BA), (q_1, aB), (q_1, a)\}$
$\delta(q_1, \Lambda, B) = \{(q_1, AB), (q_1, bA), (q_1, b)\}$
$\delta(q_1, \Lambda, Z_0) = \{(q_2, Z_0)\}$

Accepting state = $q_2$

___

2. Recall that the following PDA M accepting language $$L = \{w \in \{0, 1\}∗: w = w^r\}: M = \langle Q, \Sigma, \Gamma, \delta, q_0, Z_0, A \rangle$$
where $Q = {q_0, q_\text{even}, q_\text{odd}, q_2}, Σ = \{0, 1\}, Γ = \{0, 1, Z0\}, A = \{q_2\}$.
Moves are:  

$\delta(q_0, *_1, *_2) = \{(q_0, *_1*_2)\}$ with $∗_1 = 0$, $1$, $∗_2 = 0, 1,$  
$\delta(q_0, \Lambda, 1) = \{(q_\text{even}, 1), (q_\text{odd}, 1)\}$ 
$\delta(q_0, Λ, 0) = \{(q_\text{even}, 0), (q_\text{odd}, 0)\}$  
$\delta(q_\text{odd}, ∗_1, ∗_2) = \{(q_\text{even}, ∗_2)\}$ with $∗_1 = 0, 1,$ $*_2 = 0, 1$ 
$δ(q_\text{even}, 1, 1) = {(q_\text{even}, \Lambda)}$
$δ(q_\text{even}, 0, 0) = {(q_\text{even}, \Lambda)}$
$δ(q_\text{even}, \Lambda, Z_0) = \{(q_2, \Lambda)\}$ (empty-stack acceptance)
$δ(q_0, \Lambda, Z_0) = \{(q_2, \Lambda)\}$ (make sure that $\Lambda$ is accepted)  

Translate $M$ into a grammar $G$. 

$$S \to 0S0\;|\;1S1\;|\;\Lambda\;|\;0\;|\;1\;$$

___

3. Let $L_1$ and $L_2$ be two regular languages. Show that $$L_3 = \{xx^r : x \in L_1 \text{ and } x^r \in L_2\}$$ is a context-free language.  

Since $L_1$ and $L_2$ are regular, we can find a DFA $M_1$ and $M_2$ that accepts them respectively. We can construct PDA $M_3$ such that $L(M_3) = L_3$. First, it runs $M_1$ symbol by symbol on the input, pushing each on the stack. At some moment, it guesses to switch, and starts simulating $M_2$ on the rest symbol by symbol, popping the stack if the symbol matches the top. At the end, it checks if the top of the stack is $Z_0$, and if it is, $M_3$ accepts. Clearly, $L(M_3) = L_3$
___

4. Show that $L = \{a^{2m}b^{3m}c^{4m} : m \ge 0\}$ is not a context free language.

We use Pumping Lemma for Context Free Languages.

*Proof:*
Assume $L$ is a context free language. Let $n$ be the number in the Pumping Lemma. Pick a $z = a^{2n}b^{3n}c^{4n}$ with $|z| = 9n \ge n$ in $L$. We know that for each possible way to write $z = uvwxy$ such that $|vwx| \le n$, $vx \ge 1$, $vwx$ can only contain at most two kinds of symbols. We take $i = 2$, and see that
$$uvvwxxy \notin L$$
since the three symbol's count proportions ($a:b:c$ corresponds to $2:3:4$) are off-balance.
___