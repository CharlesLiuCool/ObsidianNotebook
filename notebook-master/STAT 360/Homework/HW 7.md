**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $10/19/2025$

___

### **Question 1.**
A campus clinic advertises that the average wait time for students is 15  
minutes. You suspect the true average wait time may be longer.


*a)* Report your sample size, sample mean and sample standard deviation.  

Sample size: $n = \fbox{36}$
Sample mean: $\bar{x} = \fbox{16.4382}$
Sample standard deviation: $s = \fbox{6.08137}$

*b)* State the null and alternative hypotheses.  
Let $\mu$ be the true mean wait time at the clinic.
$\boxed{H_0: \mu \le 15}$
$\boxed{H_A: \mu > 15}$

*c)* Calculate the test statistic  

We find
$$t = \dfrac{\bar{x} - \mu_0}{s/\sqrt{n}} = \dfrac{16.4832 - 15}{6.08137/6} \approx \fbox{1.463}$$

*d)* Define the rejection region at $\alpha=0.05$.  

First, we notice the test is right-tailed

We then solve the degrees of freedom
$$df = n-1 = 36-1 = 35$$

$t_{0.05,35} = 1.690$

So a the region is
$$\boxed{t > 1.690}$$

*e)* Based on $\alpha = 0.05$, state your decision (reject $H_0$ or fail to reject $H_0$).  

Since $1.463 < 1.690$, we $\boxed{\text{fail to reject } H_0}$.

*f)* Make a decision about the test (reject $H_0$ or fail to reject $H_0$) and write one sentence interpreting your conclusion in context.  

Since the $t$-statistic of the sample,$1.463$, is outside the rejection region $t > 1.690$, we $\boxed{\text{fail to reject } H_0}$.

This means we do not have enough evidence to claim the clinic wait time is significantly longer than $15$ minutes.


*g)* Find the $p$-value corresponding to the test and based on which make a decision about the test. (The decision should be the same with e).)

$p = P(T > 1.463) \text{ with }df = 35$
Putting this in a $t$-table calculator, we get
$$\boxed{p = 0.152}$$
Since $p=0.152>0.05$, we $\boxed{\text{fail to reject } H_0}$

___

### **Question 2**

A student health survey reports that the average amount of coffee  
consumed by college students is $2.0$ cups per day. You want to test whether the average coffee consumption at your university differs from this national average.

*a)* Report your sample size, sample mean and sample standard deviation.  

Sample size: $n = \fbox{40}$
Sample mean: $\bar{x} = \fbox{2.26169}$
Sample standard deviation: $s = \fbox{0.75723}$

*b)* State the null and alternative hypotheses.  
Let $\mu$ be the true mean wait time at the clinic.
$\boxed{H_0: \mu = 2.0}$
$\boxed{H_A: \mu \neq 2.0}$

*c)* Calculate the test statistic  

We find
$$t = \dfrac{\bar{x} - \mu_0}{s/\sqrt{n}} = \dfrac{2.26169 - 2}{0.75723/\sqrt{40}} \approx \fbox{2.186}$$

*d)* Define the rejection region at $\alpha=0.05$.  

First, we notice the test is two-tailed

We then solve the degrees of freedom
$$df = n-1 = 40-1 = 39$$

$t_{0.05,39} = 2.023$

So the rejection region is
$$\boxed{|t| > 2.023}$$

*e)* Based on $\alpha = 0.05$, state your decision (reject $H_0$ or fail to reject $H_0$).  

Since $2.186 > 2.023$, we $\boxed{\text{reject } H_0}$.

*f)* Make a decision about the test (reject $H_0$ or fail to reject $H_0$) and write one sentence interpreting your conclusion in context.  

Since the $t$-statistic of the sample, $2.186$, is within the rejection region $|t| > 2.023$, we $\boxed{\text{reject } H_0}$. 

This means we have significant evidence to claim that the average amount of coffee consumed per day by college students in your university is not $2.0$, the national average.


*g)* Find the $p$-value corresponding to the test and based on which make a decision about the test. (The decision should be the same with e).)

$p = P(T > 2.186) \text{ with }df = 39$
Putting this in a $t$-table calculator, we get
$$\boxed{p = 0.035}$$
Since $p=0.035<0.05$, we $\boxed{\text{reject } H_0}$

___

### **Question 3.**

Suppose a researcher is testing whether a new drug lowers blood pressure more than the standard treatment.  

*a)* What does a Type II error mean in this context?  

It means the researcher fails to conclude the new drug lowers  blood pressure more than standard treatment even though it does lower blood pressure.

*b)* The power of a test is defined as  
(i) the probability of making a Type I error  
(ii) the probability of making a Type II error  
$\boxed{(\text{iii})\text{ the probability of correctly rejecting a false null hypothesis}}$  
(iv) the probability that the sample mean equals the population mean 

*c)* Which of the following changes would increase the power of the test?  
(i) Using a smaller sample size  
(ii) Using a smaller significance level ($\alpha$)  
$\boxed{(\text{iii}) \text{ Increasing the sample size }}$
(iv) Increasing the population standard deviation

___