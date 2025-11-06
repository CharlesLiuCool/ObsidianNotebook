**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $8/23/2025$

___

### **Data**

Among the $62$ students in the STAT $360$ class:  
- $22$ were born in the winter (December, January, or February).  
- $10$ slept more than $8$ hours a day.  
- $23$ are taller than $70$ inches.  
- $4$ students were both born in winter and slept more than $8$ hours.  
- $7$ students were both born in winter and taller than $70$ inches.  
- $6$ students both slept more than $8$ hours and were taller than $70$ inches.  
- $2$ students satisfied all three conditions: born in winter, slept more than 8 hours, and taller than $70$ inches.  

Now suppose one student is selected at random. Define the events:  

- $A_1$: the student was born in winter 
- $A_2$: the student sleeps more than $8$ hours  
- $A_3$: the student is taller than $70$ inches  

For each question below, *(i)* write the probability in terms of $A_1, A_2, A_3$, and their union, intersection, or complement, and *(ii)* compute the probability value. For example, The probability that the student is taller than $70$ inches is $P(A_3)=23/62=0.33$

___

### **Table**

|  $P(A_1)$   | $P(A_2)$ | $P(A_3)$ | $P(A_1 \cap A_2)$ |$P(A_1 \cap A_3)$ | $P(A_2 \cap A_3)$ | $P(A_1 \cap A_2 \cap A_3)$
| --- | -------- | -------- | -------- | ------ | ----- | ------ |
|  $22/62$   |  $10/62$        |  $23/62$        | $4/62$         |  $7/62$ | $6/62$ | $2/62$

___

*a.* What is the probability that a student was not born in winter?  

$P(A_1') = 1 - P(A_1) = 1 - 22/62 = \frac{40}{62} \approx \fbox{0.65}$

*b.* What is the probability that a student was born in winter or sleeps more than $8$ hours?

$P(A_1 \cup A_2) = P(A_1) +  P(A_2) - P(A_1 \cap A_2) = 22/62 + 10/62 - 4/62 = \frac{28}{62} \approx \fbox{0.45}$

*c.* What is the probability that a student sleeps more than $8$ hours but is shorter than or equal to $70$ inches?  

$P(A_2 \cap A_3') = P(A_2) - P(A_2 \cap A_3) = \frac{10}{62}- \frac{6}{62} = \frac{4}{62} \approx \fbox{0.06}$

*d.* What is the probability that a student is either taller than $70$ inches or does not sleep more than $8$ hours?

$\begin{align} &P(A_3 \cup A_2') \\ &= P(A_3) + P(A_2') - P(A_3 \cap A_2') \\ &= P(A_3)+ (1-P(A_2)) - (P(A_3)-P(A_3 \cap A_2)) \\ &= 1-P(A_2) + P(A_3 \cap A_2) \\&= 1-10/62 + 6/62 = 58/62 \approx \fbox{0.94} \end{align}$


*e.* What is the probability that a student was born in winter, or sleeps more than $8$ hours, or is taller than $70$ inches?  

$P(A_1 \cup A_2 \cup A_3)$
$= P(A_1) + P(A_2) + P(A_3) - (P(A_1 \cap A_2) + P(A_1 \cap A_3) + P(A_2 \cap A_3)) + P(A_1\cap A_2 \cap A_3)$
$= 22/62  + 10/62 + 23/62 - (4/62 + 7/62 + 6/62) + 2/62 = 40/62 \approx \fbox{0.65}$

*f.* What is the probability that a student sleeps more than $8$ hours given that the student is taller than $70$ inches?  

$P(A_2 | A_3) = \frac{P(A_2 \cap A_3)}{P(A_3)} = \frac{6/62}{23/62} = \frac{6}{23} \approx \fbox{0.26}$

*g.* Find two events that are mutually exclusive and exhaustive (provide explanation).

Two events that are mutually exclusive and exhaustive in this example are $\boxed{A_1 \text{ and } A_1'}$ (the students in STAT $360$ born in winter, and the students in STAT $360$ not born in winter respectively).

This is because $A_1 \cap A_1' = \emptyset$ and $A_1 \cup A_1' = S$ where $S$ is all the students in STAT $360$.

___