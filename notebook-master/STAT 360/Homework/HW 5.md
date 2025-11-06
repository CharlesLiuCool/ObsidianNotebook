**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $9/7/2025$

___

*Q1.* What is the sampling distribution of a statistic? 

$A.$ The distribution of the entire population.  
$B.$ The distribution of the data values in a single sample.  
$\boxed{C.}$ The distribution of the statistic (e.g., sample mean) over all possible random samples of the same size.  
$D.$ The normal distribution with mean zero and variance one.  

Answer: \_\_$\underline{C}$\_\_

___

*Q2.* Which of the following is true about the expected value (mean) of the sampling distribution of the sample mean $\bar{X}$?  
$A.$ It is always larger than the population mean.  
$\boxed{B.}$ It equals the population mean μ.  
$C.$ It is equal to zero.  
$D.$ It cannot be determined without knowing the sample size.  

Answer: \_\_$\underline{B}$\_\_

___

*Q3.* If we increase the sample size $n$, what happens to the standard deviation of the sample mean $\bar{X}$?  

$A.$ It increases.  
$\boxed{B.}$ It decreases.  
$C.$ It stays the same.  
$D.$ It becomes exactly zero.  

Answer: \_\_$\underline{B}$\_\_
___

*Q4*. The Central Limit Theorem says that:  
$A.$ For any sample size, the population distribution becomes normal.  
$\boxed{B.}$ As the sample size increases, the sampling distribution of the sample mean approaches a normal distribution, regardless of the population distribution.  
$C.$ The population mean is always equal to the sample mean.  
$D.$ The sample variance always equals the population variance.

Answer: \_\_$\underline{B}$\_\_

___

*Q5.* A cereal company claims that the average weight of their cereal boxes is $500$ grams. A consumer group suspects the true mean is less. They take a random sample of $36$ boxes, finding a sample mean of $497$ grams with known population standard deviation $12$ grams.  

*a)* What is the sampling distribution of the sample mean?  

The standard deviation of the normal distribution is $\frac{\sigma}{\sqrt{n}} =\frac{12}{6} = 2$
The mean of the normal distribution is $500$ (same as population mean).
So it is $N(500,2)$

*b)* What is the probability of observing a sample mean of 497 grams or lower, if the true mean is $500$ grams?  


$\frac{497-500}{2} = -1.5$

$P(Z < -1.5) = 0.0668$. 

*c)* Based on your answer, comment on whether the claim seems reasonable.  

This is pretty low but greater than the $5\%$ tail bound tolerance rate ($2.5\%$ per tail) we normally take so if we choose that traditional tolerance rate, this cereal result is possible.

*Q6.* A survey claims that $45\%$ of households in a city subscribe to at least one streaming service. You take a random sample of $n=200$ households, and in your sample, $52\%$ subscribe to a streaming service.  

*a)* Define the sampling distribution of the sample proportion $\hat{p}$ .  

$p = 0.45$ is the estimated mean
$\sqrt{\frac{\hat{p}(1-p)}{n}} = \sqrt{\frac{0.45\cdot0.55}{200}} \approx 0.0352$ is the standard error

$\hat{p} \sim N(0.45, 0.0352)$

*b)* What is the expected value (mean) and standard deviation of $\hat{p}$ under the assumption that the true proportion is $0.45$? 

$0.45$, $0.0352$

*c)* Based on the sampling distribution, explain whether observing $52\%$ in your sample provides strong evidence against the survey claim that the true proportion is $45\%$.

$\frac{0.52-0.45}{0.0352} = 1.989$

$P(z \ge 1.989) = 0.0233$ which is less than $0.025$, so we say that there is strong evidence against the true proportion being $0.45\%$

___