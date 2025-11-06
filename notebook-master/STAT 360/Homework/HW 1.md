**ID:**  $011870073$
**Name:**  Charles Liu
**Professor:** Dr. Yuan Wang
**Class:** STAT $360$
**Date:** $8/23/2025$

---

### **Data**

A random sample of $10$ students from STAT $360$ class were selected and had their height given below. (unit: inch)

$$71, 74, 71, 69, 63, 65, 65, 74, 71, 76$$

____

### **Questions**

1. What is the possible target population?

It is the number of students in the STAT $360$ class, which could be anything $\fbox{greater than or equal to 10}$.

2. What is the sample and what is the sample size?

The sample is the $\fbox{10 students and their heights}$
$$71, 74, 71, 69, 63, 65, 65, 74, 71, 76$$

The sample size is $\fbox{10}$.

3. What is the variable of interest? Is it categorical or numerical?

The variable of interest is $\fbox{height in inches}$, which is $\fbox{numerical}$.

4. Compute the sample mean.

The sample mean is 
$$\dfrac{71 + 74 + 71 + 69 + 63 + 65 + 65 + 74 + 71 + 76}{10} = \fbox{69.90}$$

5. Compute the sample median.

First we sort the data
$$63, 65, 65, 69, 71, 71, 71, 74, 74, 76$$

The sample median is the average of the two middle values, which is $\fbox{71}$

6. Compute the $10\%$ trimmed mean.

We trim the top and bottom $10\%$, leaving
$$65, 65, 69, 71, 71, 71, 74, 74$$

The $10\%$ trimmed mean is 
$$\dfrac{65 + 65 + 69 + 71 + 71 + 71 + 74 + 74}{8} = \fbox{70}$$

7. Fill in the following table and compute the sample standard deviation $s$

| $x$   | $x - \bar{x}$         | $(x-\bar{x})^2$ |
|-------|-----------------------|-----------------|
| $63$  | $63-69.9=-6.9$        | $47.61$         |
| $65$  | $65-69.9=-4.9$        | $24.01$         |
| $65$  | $65-69.9=-4.9$        | $24.01$         |
| $69$  | $69-69.9=-0.9$        | $0.81$          |
| $71$  | $71-69.9=1.1$         | $1.21$          |
| $71$  | $71-69.9=1.1$         | $1.21$          |
| $71$  | $71-69.9=1.1$         | $1.21$          |
| $74$  | $74-69.9=4.1$         | $16.81$         |
| $74$  | $74-69.9=4.1$         | $16.81$         |
| $76$  | $76-69.9=6.1$         | $37.21$         |
| **$\sum$** |                   | **$170.9$**     |

$s = \sqrt{\dfrac{\sum\limits_{i=1}^n (x_i - \bar{x})^2}{n-1}} = \sqrt{\dfrac{170.9}{9}} = \sqrt{18.9\bar{8}} \approx \fbox{4.36}$

8. Compute the first quartile Q$1$, the third quartile Q$3$, and the IQR.  

Consider the sorted data
$$63, 65, 65, 69, 71, 71, 71, 74, 74, 76$$

The values at the $25$th and $75$th percentile are

$$63, 65, {\underline{\color{green}65}}, 69, 71, 71, 71, {\underline{\color{green}74}}, 74, 76$$

So:
Quartile $1$ (Q$1$) = $\fbox{65}$
Quartile $3$ (Q$3$) = $\fbox{74}$
IQR = Q$3$ - Q$1$ = $74 - 65$ = $\fbox{9}$

9. Construct a boxplot for the sample. Be specific with the whisker line

![[HW 1 2025-08-23 19.47.58.excalidraw]]

10. Using the boxplot convention, identify all the outliers if there is any.

Outlier is defined as:
any value below Q$1 - 1.5$IQR
any value above Q$3 + 1.5$IQR
Recall: IQR = $9$

Q$1 - 1.5$IQR = $65 - 1.5 \times 9 = 51.5$
Q$3 + 1.5$IQR = $74 + 1.5 \times 9 = 87.5$

So this threshold is any value outside
$[51.5,87.5]$

There is no such value, so there is $\fbox{no outliers}$.

___