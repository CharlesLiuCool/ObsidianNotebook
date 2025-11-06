**Charles Liu**
Dr. Haijun Li
$8/29/2025$

___

13. When an experiment is performed, one and only one of the events $A_1,A_2,$ or $A_3$ will occur. Find $P(A_1), P(A_2)$, and $P(A_3)$ under each of the following assumptions:

>*Lemma* $P(A_1) + P(A_2) + P(A_3) = 1$ in the given experiment.
> 
> Since only one of the events occurs at once, 
> $$A_1 \cap A_2 \cap A_3 = \emptyset$$
> and these events are mutually exclusive.
> 
> By the additive axiom of probability,
> $$(1)\;\;\;\sum\limits_{i=1}^3 P(A_i) = P(A_1) + P(A_2) + P(A_3) = P( \bigcup\limits_{i=1}^3 A_i) = P(A_1 \cup A_2 \cup A_3)$$
> 
> Since $A_1 \cup A_2 \cup A_3$ are the only events in the sample space and one must occur at once, they consist of the whole sample space (suppose $S$ is sample space, $S = A_1 \cup A_2 \cup A_3$). We can use the normalization axiom of probability to see that
> $$(2)\;\;\;P(A_1 \cup A_2 \cup A_3) = P(S) = 1$$
> 
> Combining $(1)$ and $(2)$ derived from the second and third axioms of probability, we get
> $$P(A_1) + P(A_2) + P(A_3) = 1$$

*a)* $P(A_1) = P(A_2) = P(A_3)$


It is given that $P(A_1) = P(A_2) = P(A_3)$. Combined with the above Lemma, we find
$$P(A_1) + P(A_1) + P(A_1) = 3P(A_1) = 1$$

Thus,
$$P(A_1) = P(A_2) = P(A_3) = \frac{1}{3}$$
*b)* $P(A_1) = P(A_2)$ and $P(A_3) = \frac{1}{2}$

It is given that $P(A_1) = P(A_2)$ and $P(A_3) = \frac{1}{2}$. Combined with the above Lemma, we find
$$P(A_1) + P(A_2) + P(A_3) = 2P(A_1) + \frac{1}{2} = 1$$

We can then find that
$$P(A_1) = \frac{1}{4}$$

Thus,
$$P(A_1) = P(A_2) = \frac{1}{4} \text{ and } P(A_3) = \frac{1}{2}$$

*c)* $P(A_1) = 2P(A_2) = 3P(A_3)$

It is given that $P(A_1) = 2P(A_2) = 3P(A_3)$. Combined with the above Lemma, we find
$$P(A_1) + P(A_2) + P(A_3) = 1$$

Substitute $P(A_1) = 3P(A_3)$ and $P(A_2) = \frac{3}{2} P(A_3)$

We can then find that
$$3P(A_3) + \frac{3}{2}P(A_3) + P(A_3) = \frac{11}{2} P(A_3) = 1$$
so,
$$P(A_3) = \frac{2}{11}, P(A_1) = 3P(A_3) = \frac{6}{11}, \text{ and }P(A_2) = \frac{3}{2}P(A_3) = \frac{3}{11}$$

___

15. Two part-time teachers are hired by the mathematics department and each is assigned at random to teach a single course in trigonometry, algebra, or calculus. List the outcomes in the sample space and find the probability that they will teach different courses. Assume that more than one section of each course is offered.

Define ${T = }$ trigonometry, ${A = }$ algebra, and $C =$ calculus. Also notice the fact that since the two teachers are different people, the order of class assignment matters (e.g. assigning $T$ to teacher A and $C$ to teacher B is different from assigning $C$ to teacher A and $T$ to teacher B)

*Sample Space:* $TT$, $AA$, $CC$, $TA$, $AT$, $TC$, $CT$, $AC$, $CA$
Notice that out of the $9$ possible arrangements of courses, $6$ result in the two teachers teaching different courses.
Thus, the probability is $\frac{6}{9} = \frac{2}{3}$.

___

19. Let $P(A) = P(B) = 1/3$ and $P(A \cap B) = 1/10$. Find the following:

*a)* $P(B')$

$$P(B') = 1-P(B) = 1 - 1/3 = \frac{2}{3}$$

*b)* $P(A \cup B')$

$$\begin{align} &P(A \cup B') \\ &= P(A) + P(B') - P(A \cap B') \\ &= P(A) + 1-P(B) - (P(A) - P(A \cap B)) \\ &= 1 - P(B) + P(A \cap B) \\ &= 1 - 1/3 + 1/10  \\ &= 23/30 \\&\approx{0.777} \end{align}$$

*c)* $P(B \cap A')$

$$P(B\cap A') = P(B) - P(B \cap A) = \frac{1}{3}-\frac{1}{10} = \frac{7}{30} \approx 0.233$$

*d)* $P(A' \cup B')$

Using DeMorgan's Law,
$$P(A' \cup B') = 1 - P(A \cap B) = 1 - \frac{1}{10} = \frac{9}{10} = 0.9$$

___

23. A certain family owns two television sets, one color and one black-and-white. Let $A$ be the event the color set is on and $B$ the event the black-and-white set is on. If $P(A) = 0.4$ and $P(B) = 0.3$, and $P(A \cup B) = 0.5$, find the probability of each event:

*a)* both are on

$P(A \cap B) = P(A) + P(B) - P(A\cup B) = 0.4 + 0.3 - 0.5 = 0.2$

*b)* the color set is on and the other is off

$P(A \cap B') = P(A) - P(A\cap B) = 0.4 - 0.2 = 0.2$

*c)* exactly one set is on

$\begin{align} &P(A \cap B' \cup A' \cap B) = P(A \cap B') + P(A' \cap B) \\ &= P(A) - P(A\cap B) + P(B) - P(A \cap B) \\ &= P(A) + P(B) - 2P(A \cap B) \\ &= 0.4 + 0.3 - 2 \times 0.2 = 0.4 \end{align}$

*d)* neither set is on

$P(A' \cap B') = 1 - P(A \cup B) = 1 - 0.5 = 0.5$

___

27. A bag contains five blue balls and three red balls. A boy draws a ball, and then draws another without replacement. Compute the following probabilities:

*a)* $P(\text{2 blue balls})$
$$\begin{align}P(\text{2 blue balls}) &= P(\text{1st ball is blue}) P(\text{2nd ball is blue } | \text{ 1st ball is blue}) \\ \\ &= \frac{5}{8}\cdot\frac{4}{7} = \frac{5}{14} \approx 0.357\end{align}$$

*b)* $P(\text{1 blue and 1 red})$
$$\begin{align} &P(\text{1 blue and 1 red}) \\ \\ &= P(\text{1st ball is blue})P(\text{2nd ball is red } | \text{ 1st ball is blue}) \\ &+ P(\text{1st ball is red})P(\text{2nd ball is blue } | \text{ 1st ball is red}) \\ \\&= \frac{5}{8}\cdot\frac{3}{7}  +\frac{3}{8}\cdot\frac{5}{7} = \frac{30}{56} \approx 0.536 \end{align}$$

*c)* $P(\text{at least 1 blue})$

$$\begin{align} &P(\text{at least 1 blue}) \\ \\ &= P(\text{1st ball is blue} \cup \text{2nd ball is blue})\\ \\ &= P(\text{1st ball is blue}) + P(\text{2nd ball is blue}) - P(\text{both are blue}) \\ \\ & = P(\text{1st ball is blue}) + (P(\text{2nd ball is blue } |\text{ 1st is blue})P(\text{1st is blue}) \\ &+ P(\text{2nd ball is blue } |\text{ 1st is not blue})P(\text{1st is not blue}))  - P(\text{both are blue})  \\ \\ &= \frac{5}{8} + \frac{5}{8}\cdot\frac{4}{7} + \frac{3}{8}\cdot\frac{5}{7} - \frac{5}{8} \cdot \frac{4}{7} \\ \\ &= \frac{50}{56} \approx 0.893 \end{align}$$

*d)* $P(\text{2 red balls})$

$$\begin{align} P(\text{2 red balls}) &= P(\text{1st ball is red}) P(\text{2nd ball is red } | \text{ 1st ball is red}) \\ \\ &= \frac{3}{8}\cdot\frac{2}{7} = \frac{3}{28} \approx 0.107\end{align}$$

___

30. Two cards are drawn from a deck of cards without replacement

> Define:
> $H_1:$ the event of the $1$st card being a heart
> $H_2:$ the event of the $2$nd card being a heart


*a)* What is the probability that the second card is a heart, given that the first card is a heart?

After the first heart is chosen, there is $12$ hearts left of $51$ cards.

So, $$P(H_2|H_1) = \frac{12}{51} \approx 0.235$$

*b)* What is the probability that both cards are hearts, given that at least one is a heart?

$$\begin{align}&P(H_1 \cap H_2|H_1 \cup H_2) \\ \\ &= \frac{P(H_1 \cap H_2 \cap H_1 \cup H_2)}{P(H_1 \cup H_2)} \\ \\ &= \frac{P(H_1\cap H_2)}{P(H_1 \cup H_2)} \\ \\ &= \frac{P(H_1 \cap H_2)}{P(H_1) + P(H_2) - P(H_1 \cap H_2)}  \\ \\ &= \frac{P(H_2|H_1)P(H_1)}{P(H_1) + P(H_2 | H_1)P(H_1) + P(H_2 | H_1')P(H_1') - P(H_2 | H_1)P(H_2)} \\ \\ &= \frac{P(H_2|H_1)P(H_1)}{P(H_1)  + P(H_2 | H_1')P(H_1')} \\ \\ &= \frac{\frac{12}{51}\cdot\frac{1}{4}}{\frac{1}{4} + \frac{13}{51} \cdot \frac{3}{4}} = \frac{12/51}{1 + 3\cdot13/51} = \frac{12/51}{90/51} = \frac{12}{90} = \frac{2}{15} \approx 0.133\end{align}$$


___

31. A box contains five green balls, three black balls, and seven red balls. Two balls are selected at random without replacement from the box. What is the probability that:
 
*a)* both balls are red?

$$P(\text{both balls are red}) = \frac{7}{15} \cdot \frac{6}{14} = \frac{2}{10} = 0.2$$

*b)* both balls are the same color?

$\begin{align} &P(\text{both balls are red}) + P(\text{both balls are black}) + P(\text{both balls are green}) \\ \\ &= \frac{7}{15} \cdot \frac{6}{14} + \frac{3}{15}\cdot\frac{2}{14} + \frac{5}{15}\cdot\frac{4}{14} = \frac{68}{210} \approx 0.324\end{align}$

___

34.  A pocket contains three coins, one of which had heads on both sides, while the other two are normal. A coin is chosen at random from a pocket and tossed three times.

*a)* Find the probability of obtaining three heads.

$$\begin{align}&P(\text{three heads}) \\ \\ &= P(\text{normal coin})P(\text{three heads}|\text{normal coin}) \\ &+ P(\text{double-headed coin})P(\text{three heads}|\text{double-headed coin}) \\ \\ &= \frac{2}{3} \cdot \frac{1}{2} \cdot \frac{1}{2} \cdot \frac{1}{2} + \frac{1}{3}= \frac{5}{12} \approx 0.417 \end{align}$$

*b)* If a head turns up all three times, what is the probability that this is the two-headed coin.

$$\begin{align}&P(\text{double-headed coin} | \text{three heads}) \\ \\ &= \tfrac{P(\text{double-headed coin})P(\text{three heads}|\text{double-headed coin})}{P(\text{normal coin})P(\text{three heads}|\text{normal coin}) + P(\text{double-headed coin})P(\text{three heads}|\text{double-headed coin})} \\ \\ & = \frac{1/3}{5/12} = \frac{4}{5} = 0.8\end{align}$$

___

35. In a bolt factory, machines $1$, $2$, and $3$ respectively produce $20\%$, $30\%$, and $50\%$, of the total output. Of their respective outputs, $5\%$, $3\%$, and $2\%$ are defective. A bolt is selected at random.

*a)* What is the probability that it is defective?
$$\begin{align}P(\text{defective}) &= \sum\limits_{i=1}^3 P(\text{bolt is from machine } i) P(\text{defective } | \text{ bolt is from machine } i)\\ \\ &=0.2 \cdot 0.05 + 0.3 \cdot 0.03 + 0.5 \cdot 0.02 \\ \\ &=0.01 + 0.009+0.01=0.029\end{align}$$


*b)* Given that it is defective, what is the probability that it was made by machine $1$?

$$\begin{align}&P(\text{bolt is from machine 1 } | \text{ defective}) \\ \\ &= \frac{P(\text{bolt is from machine 1|defective})P(\text{defective})}{\sum\limits_{i=1}^3P(\text{ bolt is from machine } i \text{ and defective})} \\ \\ &= \frac{0.2\times0.05}{0.2\times0.05 + 0.3 \times 0.03 + 0.5 \times 0.02} \approx 0.345\end{align}$$

___

36. Drawer $A$ contains five pennies and three dimes, while drawer $B$ contains three pennies and seven dimes. A drawer is selected at random, and a coin is selected at random from that drawer.

*a)* Find the probability of selecting a dime.

$\begin{align} &P(\text{dime}) \\ \\ &= P(\text{dime }|\text{ Drawer A})P(\text{Drawer A}) + P(\text{dime }|\text{ Drawer B})P(\text{Drawer B}) \\ \\ &= \frac{3}{8}\cdot\frac{1}{2} + \frac{7}{10}\cdot\frac{1}{2} \approx 0.538 \end{align}$

*b)* Suppose a dime is obtained. What is the probability that it came from drawer $B$?

$P(\text{Drawer B } | \text{ dime}) = \frac{P(\text{dime }|\text{ Drawer B})P(\text{Drawer B})}{P(\text{dime)}} =\frac{7/10\cdot1/2}{3/8\cdot1/2 + 7/10\cdot1/2} \approx 0.651$

___