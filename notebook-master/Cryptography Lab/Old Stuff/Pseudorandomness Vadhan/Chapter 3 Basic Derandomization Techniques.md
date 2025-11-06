>**MaxCut**
>Given a graph $G = (V,E)$, we want to find a partition $S$,$T$.
>- $S \cup T = V$
>- $S \cap T = \emptyset$
>and $|\text{cut}(S,T)|$ is maximized where $\text{cut}(S,T) = \{\{u,v\} \in E\;|\;u \in S, v \in T\}$

![[Chapter 3 Basic Derandomization Techniques 2025-09-04 11.10.15.excalidraw]]

We want to approximate the MaxCut of a given graph! How would we do that?

First consider the simple random approach

For clarity, we label $V = [N]$

>**MaxCut Approximation - Random Approach**
> *Algorithm:*
> Input: A graph $G = ([N],E)$ with no self-loops
> 
> 1. For every $i = 1,2,...,N$
> 	1. Flip a random coin, define $r_i = 1$ if heads and $r_i = 0$
> 	2. If $r_i$ is $1$, assign vertex $\{i\}$ to $S$
> 	3. Else ($r_i$ is $0$), assign vertex $\{i\}$ to $T$
> 2. Output $(S,T)$

*Analysis*

Can we make this deterministic?

Let's consider the dumbest deterministic approach

>**MaxCut - Brute Force Deterministic**
>*Algorithm*
>Input: A graph $G = ([N],E)$ with no self-loops
> 
> 1. Define `counter` = $\{0\}^N$, `MaxCut` = $0$
> 2. For every $i = 1,2,...,N$, set $
> 3. Set `MaxCut` = $\max\{|cut(S,T)|,\text{MaxCut}\}$

>**MaxCut - Conditional Expectations Derandomization**

>**MaxCut - Pairwise Independence Derandomization**