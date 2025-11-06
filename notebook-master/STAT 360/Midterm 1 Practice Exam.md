**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $9/21/2025$

___

1. To help with safety a mine conducts regular evacuation drills. The time (measured in seconds) for $29$ evacuation drills are recorded and presented here in decreasing order. 

$$\begin{align} &447, 424, 403, 402, 397, 394, 393, 392, 389, 375, 374, 373, 373, 370, 369, \\ &366, 364, 364, 363, 359, 359, 356, 356, 339, 334, 325, 325, 301, 288\end{align}$$

*a)* What is the median evacuation time?

The median evacuation time is $\fbox{369}$

*b)* What is the mean evacuation time?  


*c)* What is the variance for the evacuation time?  

$E[(x-\mu)^2] = E[x^2] - \mu^2$

*d)* What is the standard deviation for the evacuation time?  

$\frac{\sqrt{\sum\limits_{i=1}^{28} (x_i - \mu)^2}}{n-1}$

*e)* What is the value of the first quartile?  

$25$th percentile

$356$

*f)* What is the value of the third quartile?  

$390.5$

*g)* What is the value of the interquartile range?  

$390.5 - 356 = 33.5$

*h)* Using the boxplot convention, are there any outliers in the data set? If so, what are the values?  

Any value outside $1$st quartile + $1.5$ IQR or $3$rd quartile - $1.5$ IQR

___

2. A survey of computer users looked at the operating systems the users have on their home computers. Let W be the event the user is running Windows, M the user is running Mac OS X and L for Linux.  
$$\begin{align} &P(W)=0.83\\ &P(W \cap L)=0.09\\&
P(M)=0.29 \\ & P(W \cap M)=0.14 \\ & P(W \cap M \cap L)=0.02 \\ &P(L)=0.15 \\ & P(M\cap L)=0.08 \end{align}$$

*a)* What is the proportion of computer users running Windows or Linux?  
$P(W) + P(L) - P(W \cap L) = 0.83 + 0.15-0.09 = 0.89$

*b)* What is the proportion of computer users running at least one of the  
three operating systems?  

$P(W\cup L\cup M) = P(W) + P(M) + P(L) - P(W \cap M) - P(W \cap L) - P(L \cap M)$
$+ P(W \cap L \cap M)$

*c)* What is the proportion of computer users who do not run Windows but run Linux or Mac OS X?  

$P(\bar{W} \cap ( L \cup M)) = P(L \cup M)-P(W \cap M) - P(L \cap W) + P(W \cap L \cap M)$

![[Midterm 1 Practice Exam 2025-09-23 15.32.50.excalidraw]]

___

3. Three friends go out for dinner. The restaurant offers 6 different appetizers, 5 different main dishes, and 4 different desserts.  

*a)* They decide to share $2$ appetizers. If the order doesn’t matter,  
how many different appetizer combinations can they choose?

$\binom{6}{2} = \frac{6 \times 5}{2} = 15$

*b)* For the main dishes, they pick $3$ different mains and assign them to three people (each person gets one unique dish). In how many ways can this be done?  

$5P3 = 5 \times 4 \times 3 = 60$

*c)* For dessert, each of them independently chooses one dessert (they may choose the same or different desserts). How many possible dessert outcomes are there in total?  

$4 \times 4 \times 4 = 64$

___


4. A biased coin is tossed $5$ times. The probability the coin will land heads up is $73\%$  

*a)* What is the probability that exactly two tails will be observed?  
*b)* What is the probability that at least one tail is observed in the five  
tosses?  
*c)* Given at least one tail is observed, what is the probability that there will be a total of four tails observed?  

___

5. A sample of five items is drawn from a large lot in which 10% of the items are defective. Let $X$ represent the number of defective items observed in a random sample of five items. The following table gives the probabilities associated with each possible value of $X$.  

*a)* Find the $P(X=1)$.

$\binom{5}{1} 0.1 \times (0.9)^4$

*b)* Find the $P(X \le 2)$.  

$\binom{5}{0} (0.9)^5 + \binom{5}{1} 0.1 \times (0.9)^4 + \binom{5}{2} (0.1)^2 \times (0.9)^3$

*c)* Find $E(X)$.  

$np = 5 \times 0.1 = 0.5$

*d)* Find $V(X)$.  

$np(1-p) = 5 \times 0.1 \times 0.9 = 0.45$

___

6. Four companies are competing to provide fire proof foam to protect steel I-beams. Company A provides $30\%$ of the foam for testing, Company B provides $20\%$, Company C provides $15\%$, and Company D provides $35\%$ of the foam for testing. During the different tests, Company A’s foam pass $94\%$ of the tests, Company B’s foam passes $87\%$ of the tests, Company C’s foam passes $98\%$ of the tests and Company D’s foam passes $91\%$ of the tests.  

*a)* What is the probability that a randomly selected foam passes the test? 
Let $X$ be the event of tests passing
$$P(X|A)P(A) + P(X|B)P(B) + P(X|C)P(C) + P(X|D)P(D)$$
*b)* Given that a foam passes the test what is the probability it was provided by Company B?  

$$\frac{P(X|B)P(B)}{P(X|A)P(A) + P(X|B)P(B) + P(X|C)P(C) + P(X|D)P(D)}$$
___

7. Suppose that the pdf for the length of time it takes a student to finish one free answer question (in minutes) during the exam is: 

$f(x) = \begin{cases} \frac{1}{8} + \frac{3}{8}x & 0 \le x < 2 \\ 0 & \text{ otherwise} \end{cases}$

*a)* Show $f(x)$ is a density.  

$\int_{-\infty}^\infty f(x) = \int_0^2 (\frac{1}{8} + \frac{3}{8}x)dx$

*b)* What is $E(X)$?  

$\int_{-\infty}^\infty f(x)x\;dx =\int_{0}^2 \frac{1}{8}x + \frac{3}{8}x^2 \;dx = (\frac{1}{16}x^2 + \frac{1}{8}x^3)\bigg|_0^2 = \frac{1}{4} + 1 = \frac{5}{4}$

___

8. The fill volume of cans filled by a certain machine is normally distributed with mean $13.05$oz and standard deviation $0.05$oz. 

*a)* What is the probability that a randomly chosen can contains less than $13$oz?  

$P(X < 13) = P(z < -1)$

*b)* What is the probability that a randomly chosen can contains exactly $12.09$oz?  

$0$

*c)* Find the weight such that $77\%$ of cans will weigh more than this  
amount.  

Find z-score for $<23\%$

Multiply by standard deviation

___