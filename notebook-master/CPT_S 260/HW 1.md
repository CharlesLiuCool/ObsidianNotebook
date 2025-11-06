**Charles Liu**
Dr. Abhishek Moitra
$8/29/2025$

___

### **Part 1: Basic**

1. Describe the steps for transforming a program written in a high-level language such as C into a representation that is directly executed by a computer.  

>The high-level language, which is more understandable to humans, is processed into an intermediary called assembly which is a textual representation of the instructions. This assembly is then converted to bits and encoded as instructions..

2. List the main components of a computer system and describe each component briefly.  

>- CPU: does computation, includes the Arithmetic Logic Unit (ALU), control unit, and registers
>- Motherboard: Main circuit board holding all the internal components of hardware
>- Main Memory: dynamic memory that holds data and programs currently running (RAM)
>- Secondary Memory: Permanent storage (slower access, hard disk, CD, etc.)
>- I/O Devices: Used for entering/displaying data in the computer

___

### **Part 2: Performance Evaluation**

1. ($5, 5, 10$ points) Consider three different processors $P_1$, $P_2$, $P_3$ executing the same set of instructions. $P_1$ has a $2$ GHz clock rate and an average cycles per instruction (CPI) of $1.5$. $P_2$ runs at $2.5$ GHz and has a CPI of $1.2$. $P_3$ has a $3$ GHz clock rate and a CPI of $2.4$.  

*a.* Which processor has the highest performance in terms of instructions per second?  

>$\text{CPU Time} = \text{Instruction Count} \times \text{CPI}/\text{Clock Rate}$
$\implies \text{Instruction Count}/\text{CPU Time} = \text{Clock Rate}/\text{CPI}$
>
For $P_1$
$\text{Instructions}/\text{second} = 2 \text{ GHz}/ 1.5 = 4/3 = 1.\bar{3} \text{ GIPS}$
>
For $P_2$
$\text{Instructions}/\text{second} = 2.5/1.2 = 25/12 = 2.08\bar{3} \text{ GIPS}$
>
For $P_3$
$\text{Instructions}/\text{second} = 3/2.4 = 5/4 = 1.25 \text{ GIPS}$
>
So $P_2$ has the highest performance in instructions per second.

*b.* If each processor executes a program in $4$ seconds, find the number of cycles and the number of instructions for each processor.

>$\text{Clock Cycles} = \text{Clock Rate} \times \text{Time}$
>
$\text{Number of instructions} = \dfrac{\text{Cycles}}{\text{CPI}}$
>Note: GHz $= 10^9$Hz $= 10^9$  cycles per seconds
>
For $P_1$
Number of cycles = $(2 \times 10^9) \times 4= 8 \times 10^9$
Number of instructions = $(8 \times 10^9)/ 1.5= 16/3 = 5.\bar{3} \times 10^9$
>
For $P_2$
Number of cycles = $(2.5 \times 10^9) \times 4= 10 \times 10^9 = 10^{10}$
Number of instructions = $10^{10}/1.2 = 8.\bar{3} \times 10^9$
>
For $P_3$
Number of cycles = $3 \times 10^9 \times 4 = 12\times 10^9 = 1.2 \times 10^{10}$
Number of instructions = $(1.2 \times 10^{10}) / 2.4 = 5\times 10^9$

*c.* We would like to reduce the execution time by $20\%$. This will, however, increase the CPI by $25\%$ for each processor. What clock rate do we need to obtain this amount of time reduction? You may show full work for one processor and write your answers for others.  

>Let $f$ = old clock rate, $f'$ = new clock rate.
>
$0.8 \times \text{CPU Time} = \dfrac{0.8 \times \text{Instruction Count} \times \text{CPI}}{f} = \dfrac{\text{Instruction Count} \times (1.25 \times \text{CPI})}{f'}$
>
So $\dfrac{0.8}{f} = \dfrac{1.25}{f'}$
>
$\implies f' = \dfrac{1.25}{0.8}f = 1.5625f$
>
For $P_1$
$f' = 1.5625 \times 2 = 3.125 \text{ GHz}$
>
For $P_2$
$f' = 1.5625 \times 2.5 = 3.90625 \text{ GHz}$
>
For $P_3$
$f' = 1.5625 \times 3 = 4.6875 \text{ GHz}$


2. ($10, 5, 5$ points) Consider two processors $P_1$ and $P_2$ with four types of instructions as listed in Table $1$. Assume that a program with a dynamic instruction count of $10^6$ instructions such that the instructions are divided into the classes as follows: $20\%$ class A, $10\%$ class B, $50\%$ class C, and $20\%$ class D. 

*a.* What is the overall CPI for each implementation $P_1$ and $P_2$?  

>For $P_1$
$\text{CPI} = 0.2 \times 1 + 0.1 \times 2 + 0.5 \times 3 + 0.2 \times 3 = 2.5$
>
For $P_2$
$\text{CPI} = 0.2 \times 2 + 0.1 \times 4 + 0.5 \times 2 + 0.2 \times 3 = 2.4$

*b.* Which implementation ($P_1$ or $P_2$) is faster?  

>We can calculate the $\dfrac{\text{instructions}}{\text{second}} = \dfrac{\text{clock}}{\text{CPI}}$ for both:
>
>For $P_1: 2.5/2.5 = 1$
>For $P_2: 3.0/2.4 = 1.25$
>
>So $P_2$ is $1.25\times$ faster since it has higher instructions per second.

*c.* Find the clock cycles required for both processors to execute these instructions.  

>$\text{Clock Cycles} = \text{CPI} \times \text{Instruction Count}$
>
For $P_1$
$\text{Clock Cycles} = 2.5 \times 10^6 \text{ cycles}$
>
For $P_2$
$\text{Clock Cycles} = 2.4 \times 10^6 \text{ cycles}$

*Table 1. Clock per instruction for each class of instruction*

| CPU/CPI     | Class A | Class B | Class C | Class D |
| ----------- | ------- | ------- | ------- | ------- |
| $P_1(2.5 \text{GHz})$  | $1$       | $2$       | $3$       | $3$       |
| $P_2(3.0 \text{GHz})$  | $2$       | $4$       | $2$       | $3$       | 


3. ($10, 10$ points) Let us assume that a processor can execute four classes of instructions with their CPIs listed in the table below. Additionally, the table also shows the percentage of each instruction class for a set of applications typically executed on the program. Assume that the clock rate for the processor is $1$ GHz. We are currently in the process of designing a newer version of the processor and we have access to resources to improve the CPI of at most one class of instructions. Given this information,  

*a.* Which instruction class would you optimize to minimize the overall CPU time in the new processor?  

| Instruction Class | CPI | Percentage (%) |
|-------------------|-----|----------------|
| A                 |  $3$  | $15$             |
| B                 |  $1$  | $40$             |
| C                 |  $2$  | $30$             |
| D                 |  $4$  | $15$             |


>Consider how much each would be optimized:
>
>$A: 0.15 \times (3-1) = 0.3$
>$B: 0.4 \times (1-1) = 0$
>$C: 0.3 \times (2-1)  = 0.3$
>$D: 0.15 \times (4-1) = 0.45$
>
>I would improve instruction class $D$, since it has greatest room for optimization ($0.45$).

*b.* What will be the new CPI for that instruction class? Note that the minimum CPI for any instruction type is $1$.  

>$\text{New CPI} = 1$

___

### **Part 3: Amdahl’s Law**

1. ($10$ points) Suppose that we can improve the floating-point instruction performance of a machine by a factor of $10$ (the same floating-point instructions run 10 times faster on this new machine). What percent of the instructions must be floating point to achieve a speedup of at least 4?  

>$T_1$ can be optimized
>$T_2$ can't be optimized
>
$$T_\text{old} = T_1 + T_2$$
$$T_\text{improved} = \dfrac{T_1}{\text{Improvement Factor}} + T_2$$
>
$$\implies \text{speedup} = \dfrac{T_\text{old}}{T_\text{improved}} = \dfrac{T_1+T_2}{\frac{T_1}{\text{Improvement Factor}} + T_2}$$
>
We want:
$\text{fraction of instructions that are floating point} = p = \dfrac{T_1}{T_1+T_2}$
>
Note that $1-p = \dfrac{T_2}{T_1 + T_2}$
>
$$\text{speedup} = \dfrac{T_\text{old}}{T_\text{improved}} = \dfrac{T_1+T_2}{\frac{T_1}{10} + T_2} = \dfrac{1}{\frac{T_1/10 + T_2}{T_1+T_2}} = \dfrac{1}{\frac{p}{10} + 1-p}\ge 4$$
$$\implies p/10 + 1 - p \le 1/4$$
$$\implies - \frac{9}{10}p \le - \frac{3}{4}$$
$$\implies p \ge 5/6$$
>
So the percent of instructions required is at least $83.\bar{3}\%$ to achieve a speedup of at least $4$.


2. ($20$ points) Assume that a given program consists of two types of instructions: Class $A$ and Class $B$. The program consists of $70\%$ class $A$ instructions and $30\%$ class $B$ instructions. We have a new processor architecture that can run class A instructions $8$ times faster. However, the new processor architecture results in two times slow down for class $B$ instructions. Specifically, if each class $B$ instruction previously took $2$ cycles, it now takes $4$ cycles. Given this information, what is the overall speed-up for our program in the new processor architecture?

> $$T_\text{old} = 0.7 \times T_A + 0.3 \times T_B$$
> $$T_\text{improved} = 0.7 \times \frac{T_A}{8} + 0.3 \times T_B \times 2$$
> 
> Suppose $T_\text{old} = 0.7 + 0.3 = 1$
> Then $T_\text{improved} = 0.7/8 + 0.3 \times 2 = 0.6875$
> 
> $$\text{speedup} = \dfrac{T_\text{old}}{T_\text{improved}} = \dfrac{0.7 \times T_A + 0.3 \times T_B}{0.7 \times \frac{T_A}{8} + 0.3 \times T_B \times 2} = \dfrac{1}{0.6875} = 1.\overline{45}$$
> 
> Thus, the program speeds up by around $1.455\times$.


___