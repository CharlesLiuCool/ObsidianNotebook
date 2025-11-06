1. Construct a $\Lambda$-NFA accepting language $((ab^*a + ba)^* + a^*b)^*$

![[HW 5 2025-10-02 11.37.36.excalidraw]]

2. According to the proof of the Kleene's Theorem find a regular expression for $L(M)$ where $M$ is a DFA given as below:

![[HW 5 2025-10-02 11.23.25.excalidraw|center]]

$R_{ij}^0$:
- $R_{11}^0 = a + \Lambda$
- $R_{12}^0 = b$
- $R_{21}^0 = b$
- $R_{22}^0 = c + \Lambda$

$R_{ij}^1$:
- $R_{11}^1 = a^*$
- $R_{12}^1 = R_{11}^0(R_{11}^0)^*R_{12}^0 + R_{12}^0 = a^*b$
- $R_{21}^1 = ba^*$

$R_22^1 = R_{21}^0(R_{11}^0)^*R_{12}^0 + R_{22}^0 = ba^*b + c + \Lambda$ 

$R_{12}^2 = R_{12}^1 (R_{22}^1)^* R_{22}^1 + R_{12}^1 = a^*b(ba^*b + c + \Lambda)^*(ba^*b + c + \Lambda) + a^*b$

3. Show that $L = \{0^n1^m: n \ge 1, m \ge 1, n \le m\}$ is not regular.

>**Theorem.**
$L = \{0^n1^m: n \ge 1, m \ge 1, n \le m\}$ is not regular

>*Proof:*
>Assume that $L$ is regular. Let $n$ be the number in the Pumping Lemma. Pick $z = 0^n1^n \in L$ and $|z| = 2n > n$.
>Suppose that we wrote $z$ into
>$$z = uvw$$
>such that $|uv| \le n$, $|v| \ge 1$.
>$uv$ must contain $0$'s only. We take $i = 2$ Then $uv^2w = uw$. Let $|v| = t \ge 1$. Since,
>$$uv^2w = 0^{n+t}1^n$$
> which has more $0$'s than $1$'s, $uv^2w \notin L$, a contradiction.

4. Show that $L = \{xx^Rx : x \in (a+b)^*\}$ is not regular ($x^R$ is the reverse of $x$,  e.g. $aab^R = baa$)

>**Theorem.**
$L = \{xx^Rx: x \in (a+b)^* \}$ is not regular

>*Proof:*
>Assume that $L$ is regular. Let $n$ be the number in the Pumping Lemma. Pick $x = a^n$, so $z = a^{3n} \in L$ and $|z| = 3n > n$.
>Suppose that we wrote $z$ into
>$$z = uvw$$
>such that $|uv| \le n$, $|v| \ge 1$.
>Notice that if we take $i$ where $|uv^iw|$ is not divisible by $3$, then $uv^iw \notin L$ as it can't be split into $x$, $x^r$, $x$ (as $|x| = |x^r|$).

5. Which of the following languages are regular? Prove your answer.

*(1).* $\{0^m1^n0^{m+n}: m \ge 1, n \ge 1\}$

>**Theorem.**
$L = \{0^m1^n0^{m+n}: m \ge 1, n \ge 1\}$ is not regular

>*Proof:*
>Assume that $L$ is regular. Let $n$ be the number in the Pumping Lemma. Pick $z = 0^n1^n0^{2n} \in L$ and $|z| = 4n > n$.
>Suppose that we wrote $z$ into
>$$z = uvw$$
>such that $|uv| \le n$, $|v| \ge 1$.
>$uv$ must contain $0$'s only, and $v = 0^k$ for some $k \ge 1$. We take $i = 0$. Then $uv^0w = 0^{n-k}1^{n}0^{2n}$. If $uv^0w \in L$, then $n + n-k = 2n -k = 2n$, but $k \ge 1$, a contradiction. Thus, $uv^0w \notin L$ and $L$ is not regular.

*(2).* $\{0^m0^n0^{m+n}: m \ge 1, n \ge 1\}$

>**Theorem.**
$L = \{0^m0^n0^{m+n}: m \ge 1, n \ge 1\}$ is regular

>*Proof:*
>Notice for every word $w \in L$, $w = 0000(00)^*$ which is the concatenation and Kleene star of $0$. These operations preserve regularity, so $L$ must be regular.

*(3).* $\{xwx^R: x \in (0+1)^*, w \in (0+1)^*\}$

>**Theorem.**
$L = \{ xwx^R: x \in (0+1)^*, w \in (0+1)^* \}$ is a regular language

>*Proof:*
>Notice that for all words $\ell \in L$, we can write
$$\ell = (0+1)^* (0+1)^* ((0+1)^*)^r = (0+1)^*$$
>$(0+1)^*$ is regular as Kleene-star and union operation preserve regularity.

*(4):* $\{0^n1^m: n \ge 1, m \ge 1, n > m\}$

>**Theorem**
>$\{0^n1^m: n \ge 1, m \ge 1, n > m\}$ is not regular.

>*Proof:*
>Assume that $L$ is regular. Let $n$ be the number in the Pumping Lemma. Pick $z = 0^{n+1}1^n \in L$ and $|z| = 2n > n$.
>Suppose that we wrote $z$ into
>$$z = uvw$$
>such that $|uv| \le n$, $|v| \ge 1$.
>$uv$ must contain $0$'s only, and $v = 0^k$ for some $k \ge 1$. We take $i = 0$. Then $uv^0w = 0^{n+1-k}1^{n}$. If $uv^0w \in L$, then $n +1-k > n$, but $k \ge 1$, a contradiction. Thus, $uv^0w \notin L$ and $L$ is not regular.

6. For the finite automaton below, find a minimal-state finite automaton accepting the same language.


![[HW 5 2025-10-04 21.10.45.excalidraw]]

![[HW 5 2025-10-04 11.37.39.excalidraw]]

![[HW 5 2025-10-02 11.32.24.excalidraw]]