**Charles Liu**
Dr. Zhe Dang
CPT_S 317

___

1. Give an example (i.e., a word in the language represented by regular expression) and a counter example (i.e., a word not in the language represented by regular expression) to the following regular expressions: $0(10 + 0)^∗11$ and $(0 + 110)^∗1(01 + 1)^∗$.  

$0(10 + 0)^∗11$
A word in the language: $011$
A word not in the language: $010$

$(0 + 110)^∗1(01 + 1)^∗$
A word in the language: $011$
A word not in the language: $000$

___

2. Find a regular expression for each of the following languages on $\{0, 1\}$:  

*(1).* all strings containing more than two $0$’s,  

$$(0+1)^*0(0+1)^*0(0+1)^*0(0+1)^*$$

*(2).* all strings that do not contain $01$,

$$1^*0^*$$

*(3).* all strings contain both $1011$ and $0111$ as substrings,

Consider the four cases:
a) $1011$ and $0111$ in that order
$$(0+1)^*1011(0+1)^*0111(0+1)^*$$
b) $0111$ and $1011$ in that order
$$(0+1)^*0111(0+1)^*1011(0+1)^*$$
c) $10111$ (contains both)
$$(0+1)^*10111(0+1)^*$$
d) $0111011$ (also contains both)
$$(0+1)^*0111011(0+1)^*$$

Therefore a regular expression for the language is
$$\begin{align}(0+1)^*101&1(0+1)^*0111(0+1)^* + (0+1)^*0111(0+1)^*1011(0+1)^* \\ &+ (0+1)^*10111(0+1)^* + (0+1)^*0111011(0+1)^* \end{align}$$

*(4).* all strings that do not end with $01$.  

Consider the cases:
a) empty string
$$\{ \wedge \}$$
b) $0$ string
$$ \{ 0 \}$$
c) $1$ string
$$\{1\}$$
d) ends with $00$
$$(0+1)^*00$$
e) ends with $10$
$$(0+1)^*10$$
f) ends with $11$
$$(0+1)^*11$$

Therefore a regular expression for the language is
$$\wedge + 1 + (0+1)^*(00 + 10 + 11)$$

___

3. Show that, for any languages $L_1$ and $L_2$, we have  

*(1).* $L_1L_1^∗ = L_1^*L_1L_1^*$

> *Proof:*
> To prove this, we prove $L_1L_1^* \subseteq L_1^*L_1L_1^*$ and $L_1^*L_1L_1^* \subseteq L_1L_1^*$
> 
> (1) $L_1L_1^* \subseteq L_1^*L_1L_1^*$
> Consider all $x\in L_1L_1^*$. Notice that $x$ can be written in the form $\wedge L_1L_1^*$. Since $\wedge \in L_1^*$, $x\in L_1^*L_1L_1^*$, and $L_1L_1^* \subseteq L_1^*L_1L_1^*$.
> 
> (2) $L_1^*L_1L_1^* \subseteq L_1L_1^*$
> Consider all $y \in L_1^*L_1L_1^*$. By the definition of Kleene-stars, we can rewrite $y$ as 
> $$\begin{align}(\bigcup\limits_{k\ge 0} L_1^k) L_1L_1^* &= (\wedge + \bigcup\limits_{k \ge 1} L_1^k) L_1L_1^* \\ &= L_1L_1^* + \bigcup\limits_{k \ge 1} L_1^kL_1L_1^* \\ &= L_1L_1^* + L_1\bigcup\limits_{k \ge 0} L_1^kL_1L_1^* \\ &= L_1L_1^* + L_1L_1^*L_1L_1^* \end{align}$$
> Notice that since 
> $$L_1^*L_1L_1^* = (\bigcup\limits_{i \ge 0}L_1^i)L_1 (\bigcup\limits_{j \ge 0} L_1^j) = \bigcup\limits_{i \ge 0} \bigcup\limits_{j \ge 0} L_1^{i+j+1} = L_1L_1^* \subset L_1^*$$ we can see that $$L_1L_1^*L_1L_1^* \subset L_1L_1^*$$
> and
> $$L_1^*L_1L_1^* = L_1L_1^* + L_1L_1^*L_1L_1^* \subseteq L_1L_1^*$$
>

*(2).* $(L_1^* L_2)^*L_1^* = (L_1+L_2)^*$

>*Proof:*
>$(L_1^*L_2)^*L_1^* = \bigcup_{i \ge 0} (L_1^* L_2)^i \bigcup_{j \ge 0} (L_1)^j$
>
>(1) $(L_1^* L_2)^*L_1^* \subseteq (L_1+L_2)^*$
> 
> Define $S = (L_1^* L_2)^*L_1^*$. Notice that since $L_1^*L_2 \subseteq (L_1+L_2)^*$,
> $$S = (L_1^* L_2)^*L_1^* \subseteq ((L_1+L_2)^*)^*(L_1+L_2)^* = (L_1+L_2)^*$$ 
>
>(2) $(L_1+L_2)^* \subseteq (L_1^* L_2)^*L_1^*$
>Consider all $x \in (L_1+L_2)^*$. Note that we can write $$x = L_1^*L_2^*L_1^*L_2^*...$$ which is equivalent to
>$$(L_1^*L_2^*)^*L_1^*$$
>Decomposing with the Kleene-Star definition, we get
>$$(L_1^*L_2^*)^*L_1^* = \bigcup\limits_{k \ge 0}(L_1^*\bigcup\limits_{j \ge 0}L_2^j)^kL_1^* = \bigcup\limits_{k \ge 0}(\bigcup\limits_{j \ge 0}L_1^*L_2^j)^kL_1^* \subseteq \bigcup\limits_{k \ge 0}(\bigcup\limits_{j \ge 0}L_1^*(\wedge \cdot L_2)^j)^kL_1^*$$
>Note that since $\wedge \subset L_1^*$,
>$$\bigcup\limits_{k \ge 0}(\bigcup\limits_{j \ge 0}L_1^*(\wedge \cdot L_2)^j)^kL_1^* \subseteq \bigcup\limits_{k \ge 0}(\bigcup\limits_{j \ge 0}L_1^*(L_1^* \cdot L_2)^j)^kL_1^* = \bigcup\limits_{k \ge 0}(\bigcup\limits_{j \ge 0}(L_1^* \cdot L_2)^j)^kL_1^* = (L_1^*L_2)^*L_1^*$$
>Note the penultimate equality exists as $(L_1^*L_2)^*$ allows for arbitrary prefixes of $L_1^*$ so $L_1^*$ can be incorporated.
>Thus,
> $$(L_1+L_2)^* \subseteq (L_1^* L_2)^*L_1^*$$

4. Show me (through an example) why this is not true: for any languages $L_1$ and $L_2$, we have $L_1^* + (L_1^*L_2)^* = (L_1+L_2)^*$

$L_1 = \{a\}, L_2 = \{b\}$
$ba \in (L_1+L_2)^*$, but $ba \notin L_1^* + (L_1^*L_2)^*$ since $b$ not in $L_1^*$ but a string in $L_1^*$ is a required prefix anytime $b \in L_2$ appears.

___

5. Any pets in your house? I have a $10$ gal fish tank. You may not want to keep more than three fishes in such a small tank, so I choose to maintain a population of exactly $3$ (no more, no less, and don’t ask me why). Unfortunately, every day, exactly one fish dies and I immediately buy a new one from a local fish store and put it in the tank by the end of the day. This happens until someday later no fish dies and I have always the same three fish in my tank. Here are some rules about the tank:  

(1). At most these two kinds of fish in the tank: damsels and clowns,  
(2). Since damsels are pretty aggressive, if the tank has at least one  
clown, then there is no more than one damsel in the tank.  

At the end of each day, my tank is in one of the following possible configurations:  
A: three damsels,  
B: three clowns,  
C: $2$ clowns and $1$ damsel.  

From day one to day $n$, I may observe a sequence (with length n) of these  
configurations, which is a word on alphabet $\{A, B, C\}$. Write a regular ex-  
pression that represents all the possible observed sequences for all n.

First define the behavior
If there is currently $3$ damsels (letter $A$), then once one fish dies and is replaced I can only end up with $3$ damsels again ($A$) as I can't replace it with a clown (as damsels are too aggressive).

If there is currently $3$ clowns (letter $B$), then once one fishes dies and is replaced, you could end up with $3$ clowns again ($B$) or $2$ clowns and $1$ damsel ($C$).

If there is currently $2$ clowns and $1$ damsel, you could end up with $3$ clowns ($B$) on the next day or $2$ clowns and $1$ damsel ($C$) again.

To summarize, either you stay within states $B$ and $C$, or achieve $A$ where you can only have three damsels in the tank forever.

Thus, the expression is $(B+C)^* + A^*$
___