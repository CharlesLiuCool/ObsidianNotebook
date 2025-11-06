**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $10/12/2025$

___

### **Question 1:**
A recent survey of $100$ randomly selected college students found that X of them said they regularly skip breakfast. Generate your random value for X here [BreakfastSkipper](https://ywang-wsu-2025.shinyapps.io/BreakfastSkipper/ "Link").

1. Compute the sample proportion of students who skip breakfast.

Using Breakfast Skipper, $X = 28$

Thus, the sample proportion is $\frac{28}{100} = \fbox{0.28}$

2. Construct a $95\%$ Confidence Interval for the true proportion of all college students who skip breakfast.

We first find the standard error
$$SE = \sqrt{\frac{\hat{p}(1-\hat{p})}{n}} = \sqrt{\frac{0.28 \times (1 - 0.28)}{100}} = \sqrt{\frac{0.2016}{100}} = \sqrt{0.002016} \approx 0.0449$$

We then find the margin of error ($z = 1.96$ for $95\%$  confidence)

$$MoE = z \times SE = 1.96 \times 0.0449 \approx 0.088$$

We find
$$\hat{p} \pm MoE = 0.28 \pm 0.088$$
So the $95\%$ confidence interval is
$$\fbox{(0.192, 0.368)}$$

3. Interpret your interval in part B in the context of this problem.

We are $95\%$ sure the true population proportion of college students that regularly skip breakfast lies in the interval of $(0.192,0.368)$

4. Go to Quiz and use your confidence interval to answer the question for HW$6$ Extra Credit.

$\boxed{\text{Yes}}$

5. A nutritionist claims that $30\%$ of college students skip breakfast. Based on your interval, does the data support or refute this claim at the $95\%$ confidence level? Explain your reasoning.

My data *supports* this claim. $30\%$ is within the $95\%$ confidence interval of $(0.192,0.368)$.

### **Question 2:**

Would the width of a confidence interval (for the population proportion) increase, decrease, or remain the same as a result of each of the following changes?

1. The sample size is doubled, from $400$ to $800$.

$\boxed{\text{Decrease}}$, more sample means more confidence.

2. The population size is doubled, from $25$ million to $50$ million.

$\boxed{\text{Remain the same}}$, population size doesn't matter unless the sample is a high percentage of the population.

3. The level of confidence is increased from 90% to 95%.

$\boxed{\text{Increase}}$, this allows for more margin of error.

___

### **Question 3:**
A city council wants to estimate the proportion of households that regularly recycle. How many samples should they collect at least such that the margin of error of the $95\%$ confidence interval is no more than $0.04$?

We know 
$$MoE = z\sqrt{\frac{\hat{p}(1- \hat{p})}{n}}$$

and for $95\%$ confidence, $z = 0.95$

We take $\hat{p} = 0.5$ to maximize the below inequality

$1.96 \times \sqrt{\frac{0.5(1 - 0.5)}{n}} \le 0.04$

and find

$$1.96 \times \sqrt{\frac{0.25}{n}} \le 0.04$$

We can calculate that $n \ge 600.25$, so the city council needs $\boxed{601}$ samples.

___