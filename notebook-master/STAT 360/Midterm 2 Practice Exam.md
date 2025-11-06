
___

1. CI for proportion. The article “An Evaluation of Football Helmets Under Impact Conditions” (American Journal of Sports Medicine, $1984: 233$-$237$) reports that when each football helmet in a random sample of $37$ suspension type helmets was subjected to a certain impact test, $24$ showed damage. Let $p$ denote the proportion of all helmets of this type that would show damage when tested in the prescribed manner.  

A. Calculate a $99\%$ CI for $p$.  

$\hat{p} = \frac{24}{37} = \bar{0.648}$
$z = 2.58$

$\text{M.O.E.} = z\cdot\sqrt{\frac{p_0(1-p_0)}{n}} = 2.58\sqrt{\frac{\overline{0.648}(1-\overline{0.648})}{37}} = 0.202$ 

The confidence interval is
$$0.649 \pm 0.202$$

B. Interpret the interval from part A in the context of this problem.  

We are $99\%$ confident the true damage proportion of football helmets under impact lies in:
$$0.649 \pm 0.202$$

C. What sample size would be required for the width of a $99\%$ CI to be at most $0.10$?  

Each section $0.05$

$\text{M.O.E.} = z\cdot\sqrt{\frac{0.25}{n}} = 2.58\sqrt{\frac{0.25}{n}} \le 0.05$ 

$n \ge 666$

___

2. CI for mean. The maximum shock force of a certain type of steel cable can withstand is being investigated. A sample of $58$ cables are tested resulting in a mean of $\bar{x} = 864.1N$ and a sample standard deviation of $s=62.7N$  

A. Determine the $95\%$ confidence interval for the true mean maximum shock force for all steel cables.  

$\text{M.O.E.} = 2.009 \times (62.7/\sqrt{58}) = 122.892$

$864.1 \pm 16.54$

B. Interpret the interval from part A in the context of this problem. 

We are $95\%$ sure the true mean of maximum shock force for all steal cables lies between the interval of 

$$864.1 \pm 16.54 \text{ Newtons}$$

C. If the sample size increase to $108$, how would the confidence interval change?  

There would be more degrees of freedom, which means the t-value gets slightly smaller. The standard error, which is divided by square root of sample size, would also decrease to that effect.

___

3. Sampling distribution. Assume that the weight of a randomly selected person is normally distributed with a mean of $75$kg and standard deviation of $10$kg.  

A. What is the probability that the mean weight of four people will be between  
$72.5$kg and $87.8$ kg?  

$87.8-75 = 12.8$

$72.5 - 75 = -2.5$

sample standard deviation
$s = \frac{\sigma}{n} = \frac{10}{\sqrt{4}} = 10/2 = 5$

$12.8/5 = 2.56$
$-2.5/5 = -0.5$

We need to find the probability of $0.5<z<2.56$
$$0.99477 - 0.30854 = 0.686$$

B. An elevator has a max capacity of $8$ persons or $558$kg. In an elevator with $8$ persons, what is the probability that the weight limit will be exceeded?
(Assume the weights of the people on the elevator are independent random  
variables.)  

$75 \times 8 = 600$
$\frac{75-69.75}{\frac{10}{\sqrt{8}}} =$

The probability that it will exceed is $93.smth$.

___

4. Have you ever been frustrated because you could not get a container of some sort to release the last bit of its contents? The article “Shake, Rattle, and Squeeze: How Much Is Left in That Container?” (Consumer Reports, May $2009$: $8$) reported on an investigation of this issue for various consumer products. Suppose five $6.0$ oz tubes of toothpaste of a particular brand are randomly selected and squeezed until no more toothpaste will come out. Then each tube is cut open and the amount remaining is weighed, resulting in the following data (consistent with what the cited article reported): $.53, .65, .46, .50, .37$. 
Does it appear that the true average amount left is less than $10\%$ of the advertised net contents?  

*A.* Carry out a test of the appropriate hypotheses using a significance level of $.05$. Would your conclusion change if a significance level of $.01$ had been used?  

$H_0: tp \ge 0.6$
$H_A: tp < 0.6$

$\dfrac{0.53 + 0.65 + 0.46 + 0.5 + 0.37}{5} = 0.502$

$\sqrt{\dfrac{(0.502-0.53)^2 + (0.502-0.65)^2 + (0.502-0.46)^2 + (0.502 - 0.5)^2 + (0.502-0.37)^2}{4}} = 0.1023$

$0.1023/\sqrt{5} = 0.0457$

$df = 4$

$t = -2.132$

$\dfrac{0.502 - 0.6}{0.0457} = -2.142$

>Because our test-statistic $t=-2.14$ is inside the rejection region $t < 2.132$, we reject the null hypothesis that there is at least $0.6$ oz left ($10\%$) in the toothpaste tube.

If instead we take $99\%$ confidence interval

$t = -3.747$

>Because our test-statistic $t=-2.142$ is inside the rejection region $t < 3.747$, we fail to reject the null hypothesis that there is at least $0.6$ oz left ($10\%$) in the toothpaste tube.


*B.* Describe in context type I and II errors, and say which error might have been made in reaching a conclusion.  

Type 1:
This is where we reject the null hypothesis when it is actually true. This would be us saying there is more than 0.6 oz left in the bottle when in reality usually there is less than 0.6 oz left.

Type 2:
This where we fail to reject the null hypothesis when the null hypothesis is false. This would be us saying we don't have enough evidence to say there is more than $0.6$ oz left in the bottle, when in reality usually there is.

At $5\%$ significance level, we might have made a type $1$ error, where we rejected it when in reality it might have less than 0.6oz usually.

At $1\%$ significance level, we might have made type $2$, failing to reject when in reality there is at least $0.6$oz in the bottle

5. CI and hypothesis test for proportion. Is robot better than human? Suppose that in an experiment to determine whether the use of robots to weave computer cables is feasible, a robot was used to assemble $500$ cables. The cables were examined and there were $15$ defectives. It is known that human assemblers have a defect rate of $.035 (3.5\%)$.  

A. Estimate the true average defective rate for the robot assemblers.  

$15/500 = 0.03$

B. Construct a $95\%$ confidence interval for the defective rate for the robot assemblers. Give your answer to 3 decimal places.  

$t = 1.96$

$\text{M.O.E.} = 1.96 \times \sqrt{\dfrac{0.03(1-0.03)}{500}} = 0.013$

$(0.015, 0.045)$

C. Would a $90\%$ confidence interval be wider than your answer in B?  

No, $90\%$ is less confidence, and has a lower $z$-value. It would thus be narrower.

D. Suppose that we want to test about if the robot assembler is better than human.  
State the null and alterative hypotheses.  

$H_0: p \le 0.035$
$H_A: p > 0.035$

E. Calculate the test statistic.

$\dfrac{0.03-0.035}{\sqrt{\frac{0.035(1-0.035)}{500}}} = -0.608$

F. Find a p-value corresponding to the test.  

$p = P(x<Z) = 0.272$

G. Make a conclusion and interpret in the context. Use $\alpha=0.05$.  

Since the p-value of the sample, $p=0.272$, is greater than $\alpha = 0.05$, we fail to reject the null hypothesis. This means we don't have enough evidence to claim robots are better than humans at assembly.



___

### **True or False**

6. In a one-sample t-test, the test statistic follows a t-distribution only when the population standard deviation is unknown.  

>True

7. The p-value for a two-sided t-test is the probability of observing a test statistic as extreme or more extreme in one tail only.  

>False

9. The sampling distribution of the sample mean becomes approximately normal as the sample size increases, regardless of the population distribution.  

>True

10. In a one-sample t-test, increasing the sample size makes the t-distribution approach the standard normal distribution.  

>True

11. The standard error of the sample mean is calculated as $s/\sqrt{n}$, where $s$ is the sample standard deviation.

>True

12. When testing a proportion, the standard error is based on the hypothesized proportion $p_0$, not the sample proportion.  

>True

13. In the sampling distribution of the sample mean, the mean of the sampling distribution equals the population mean.  

>True

14. A smaller p-value always indicates a larger effect size.  

>False

15. When conducting a one-sample t-test, the null hypothesis always states that the population mean equals zero.

>False