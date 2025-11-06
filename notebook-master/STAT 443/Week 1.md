### **Sample Space**

- *Sample space* $S := \{\text{all possible outcomes }\omega \text{ of an underlying experiment}\}$

### **Continuous Sample Space**

- A randomly selected car battery is tested and the time of failure is recorded. Then
$$S = \{t : t \ge 0\} = \{t \,|\, t \ge 0\} = [0, +\infty)$$

- A randomly selected cell phone call with call duration $l$ at time $t$ is recorded. Then
$$S = \{(l,t): l \ge 0, t \ge 0\} = [0, +\infty) \times [0, +\infty)$$

- In general, $S = \Bbb{R}^d$, where $R = (-\infty, +\infty)$, or $S$ could be a space of certain functions or a space of certain sets.

### **Events**

>**Definition**
>Any subset $E$ of a sample space $S$ is called an *event*, and this is denoted as $E \subseteq S$.

- *Elementary Event:* Exactly one outcome $\{ \omega \} \subseteq S$
- *Impossible event:* Empty set $\emptyset \subseteq S$.
- *Sure event:* Sample space $S (\subseteq S)$ itself

### **Elementary and Composite Events**

> **Composite Events via Set Operations**
> - *Union $E_1 \cup E_2$*: $E_1$ or $E_2$ occurs.
> - *Intersection $E_1 \cap E_2$*: both $E_1$ and $E_2$ occur
> - *Complement $E'$*: $E$ does not occur
> - *Mutually exclusive*: $E_1 \cap E_2 = \emptyset$
> - One can take unions or intersections finitely or infinitely many times

### **Probabilistic Structure**

Probability $\Bbb{P}(E)$: Likelihood of the random event $E$, $E \subseteq S$,
$\Bbb{P}(\cdot): E \to [0,1]$

> **Basic Axioms of Probability Measures**
> - $0 \le  \Bbb{P}(E) \le 1$ for all $E \subseteq S$
> - $\Bbb{P}(S) = 1$
> - If events $E_1, E_2, ...,E_k,...,$ are mutually exclusive,
>  $$\Bbb{P}(\bigcup_{i=1}^\infty E_i) = \sum_{i=1}^\infty \Bbb{P}(E_i)$$

Note that $3$ implies that for any finite $k$,
$$\Bbb{P}(\bigcup_{i=1}^kE_i) = \sum_{i=1}^k\Bbb{P}(E_i)$$

>**More Properties**
>1. $\Bbb{P}(A') = 1 - \Bbb{P}(A)$
>2. $\Bbb{P}(\emptyset) = 0$
>3. For any events $B$ and $C$, $$\Bbb{P}(B \cup C) = \Bbb{P}(B) + \Bbb{P}(C) - \Bbb{P}(B \cap C)$$