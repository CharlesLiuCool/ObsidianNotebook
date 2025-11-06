**Charles Liu**
Dr. Zhe Dang
8/22/2025

___

1. Consider the following two languages on the alphabet $\sum = \{a,b\}$:

$L_1$, the set of all words $w$ on the alphabet such that $w$ contains at least three $a$'s
$L_2$, the set of all words $w$ on the alphabet such that $w$ contains the same number of $a$'s and $b$'s

Now, I have a robot $M$ holding two flowers, *red* and *blue*, and, at each second, shows exactly one of the two. When the *red* is observed, this event is called $a$; when the *blue* is observed, this event is called $b$. (The programs below may use some interrupt mechanism as I showed in class)

(1) Please program the robot such that the set of all its observable behaviors is exactly $L_1$;

*Robot:*
```cpp
int counter = 0
while (at each 0.5 second) {
	if (at each 1 second) {
		if (interrupt happens) {
			show red flower (event a)
			counter++	
		}
		else {
			show blue flower (event b)
		}
	}
	else {
		if (interrupt happens && counter > 3) break;
	}
}
exit nicely
```

2.  Please program the robot such that the set of all its observable behaviors is exactly $L_2$

```cpp
int counter = 0;
while (at each 0.5 second) {
	if (at each 1 second) {
		if (interrupt happens) {
			show red flower
			counter++;
		}
		else {
			show blue flower
			counter--;
		}
	}
	else {
		if (interrupt happens && counter == 0) break;
	}
}
exit nicely
```


3. Please argue intuitively why you only need a fixed and finite amount memory for the program in (1) while you have to use an unbounded amount of memory for the program in (2)

In the first program, you only need one two-bit boolean variable to represent the number of flowers, whereas in the second algorithm you need unbounded bits as each letter in the language (possibly infinite) can have variable state (a or b). Specifically, at a minimum for some word of length $n$, you would need at minimum a $\log_2(n)$ bits to store its contents, but as $n\to\infty$, this also approaches infinity.

4. Because of the arguments established in (3), we are ready to conclude that $L_2$ is more complex than $L_1$. Indeed, this is true. However this conclusion does not imply that every word in $L_2$ is more complex than every word in $L_1$. For instance, consider the following two words:
$$w_1 = aaababaababaaabbaab \in L_1$$
$$w_2 = aaaaaaaaabbbbbbbbb \in L_2$$
It is “clear” that $w_1$ is more complex than $w_2$, actually. In other words, we  
may need a completely new method in measuring the complexity of a single  
word (herein, I am not interested in measuring the complexity of a languages  
as in $(3)$). Please suggest a way to measure the complexity of a word.

One way to measure a complexity is the length of the shortest program that can produce a word (Kolmogrov Complexity). For a "simple" word like $w_2 = aaaaaaaaabbbbbbbbb \in L_2$, there would be a very simple program. Similarly, another word with repeated structure would also have a simple program. In contrast, a word with a lot of varied structure like $w_1 = aaababaababaaabbaab \in L_1$ would be way more complex.
___