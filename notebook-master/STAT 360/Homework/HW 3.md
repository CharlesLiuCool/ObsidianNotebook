**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $9/7/2025$

___

### **Counting Technique**

1. A student must choose one course from each of the following categories: Statistics ($5$ options), Computer Science ($6$ options), and Biology ($4$ options). How many different schedules are possible?

$5 \times 6 \times 4 = \fbox{120}$

2. A password consists of $4$ characters. The first two are lowercase English letters, and the last two are digits ($0–9$).

*A.* How many possible passwords are there?
	The first four can be any of the $26$ characters in the alphabet, the last two can be any of the $10$ digits.
	$26^2 \times 10^2 \approx \boxed{67,600}$
		
*B.* How many possible passwords if no letter or digit may be repeated?
	$P_{26,2} \times P_{10,2} = \frac{26!}{24!} \times \frac{10!}{8!} = (26\times25)\times(10\times9) = \boxed{58,500}$
	

3. Four graduate students and four undergraduates sit in a row of 8 seats.

*A.* How many ways can they sit?

If  the seating order is distinct, it is $8! = \fbox{40,320}$

If undergraduates/graduates seating order doesn't matter, it is $\binom{8}{4} = \frac{8!}{4!4!} = \fbox{70}$

*B.* How many ways can they sit if all graduate students must sit together?

There are $5$ different ways the four graduate students can sit together in the row. Considering the leftmost person, they can sit at the first, second, third, fourth or fifth position. Any more to the left, and the $4$ people don't fit.

Now considering the undergraduates, if each of their seating order is distinct, there are $4!$ ways left for them to fill up the remaining $4$ seats. Likewise, for the graduates, there are $4!$ ways

This results in $5 \times 4! \times 4! = \fbox{2,880}$

If the undergraduates seating orders aren't distinct, and likewise with the graduates, then they are fixed to the seats already after the graduate students have sat and thus don't contribute any more ways of seating. This means there are only $\fbox{5}$ ways.

___

### **Bayes' Theorem**

4. A new diagnostic test is designed to detect a certain disease. In the general population, $2\%$ of people have the disease. The test correctly identifies $95\%$ of diseased individuals as positive. The test correctly classifies $97\%$ of healthy individuals as negative.

*A.* What is the probability that a randomly chosen person will test positive?
Let $A$ be the event someone will test positive
Let $B$ be the event someone is actually infected

Since $2\%$ of people have the disease, $$P(B) = 0.02$$
Therefore, $$P(\bar{B}) = 1 - 0.02 = 0.98$$
since having and not having the disease is both mutually exclusive and exhaustive

Since the test correctly identifies $95\%$ of diseased individuals as positive, $$P(A|B) = 0.95$$

Since the test correctly classifies $97\%$ of healthy individuals as negative, $P(\bar{A}|\bar{B}) = 0.97$.
As testing negative and testing positive is mutually exclusive and exhaustive under the condition someone is healthy, $$P(A|\bar{B}) = 1 - P(\bar{A} | \bar{B}) = 0.03$$


$P(A) = P(A|B)P(B) + P(A|\bar{B})P(\bar{B}) = 0.95 \times 0.02 + 0.03 \times0.98 = 0.0484\approx 0.05$

Thus, the probability a randomly chosen person will test positive is approximately $\fbox{0.05}$

*B.* If a person tests positive, what is the probability they actually have the disease?

$P(B|A) = \frac{P(A|B)P(B)}{P(A)} = \frac{0.95 \times 0.02}{0.0484} \approx \fbox{0.39}$

___

*Extra Credit:* A department has $12$ faculty members. A committee of $4$ is to be chosen. How many different committees are possible if two specific faculty members refuse to serve together?

There are three cases, one which none of the two "difficult" faculty are chose, one where the first one (say, person A) is chosen, and one where the second one (say, person B) is chosen.

Consider the first case. Out of the ten normal people, there are $\binom{10}{4} = \frac{10!}{4!6!} = 210$ different ways.

Now consider if person $A$ is in the committee. There is $10$ remaining people that can join the committee, and three spots left, for a total of $\binom{10}{3} = \frac{10!}{3!7!} = 120$ different ways

Person $B$ is similar to the situation with person $A$, also having $120$ ways

Thus the total amount of ways is $$210+120+120 = \fbox{450}$$

Note that we can add like this since each of the three cases are mutually exclusive and consist of all the possibilities of committees.
___