**Charles Liu**
Dr. Zhe Dang
$9/25/2025$

___

0. Eliminate $\Lambda$-transitions in the following NFA.

![[HW 4 2025-09-25 11.12.45.excalidraw]]

NFA with $\Lambda$-transitions removed:

![[HW 4 2025-09-25 11.15.08.excalidraw]]

___

1. Translate the following NFA $M$ into a DFA $M'$ such that $L(M') = L(M)$ and provide a regular expression for $L(M)$.

![[HW 4 2025-09-25 11.31.46.excalidraw]]

![[HW 4 2025-09-25 11.33.32.excalidraw]]

Regular expression:
$$10^*(\Lambda + 11^*)$$
___

2. A `C`-program is deterministic. But I can easily expand it to be a nondeterministic program. For instance, consider the following program:  
```c
Char c;  
1. Read(c);  
2. if c == ‘a’ or c == ‘b’ then  
goto 1 or goto 3;  
3. if c == ‘a’  
goto 1;  
4. if c != ’b’  
Abort;  
5. Halt.
```

  
Tell me the regular expression for all the input sequences of characters that will make the program enter the last statement Halt.

If we read a character that's not $a$ or $b$, we crash, so $c$ can only equal $a$ or $b$.

When we get to step $2$, we must go back to step $1$ if $c$ is $a$ (since either it goes straight to step $1$, or to step $3$ and back to step $1$). When we read $b$, it could go back to step $1$ or go to step $3$, in which the if statement will be false, and then step $4$, where its false again, and then halt.

Notice that if $a$ is read, we loop back and keep reading and follow this same process starting from step $2$, but if $b$ is read, it could halt. Thus the expression is some arbitrary combination of $a$'s and $b$'s ending with $b$.

$$(a+b)^*b$$

___