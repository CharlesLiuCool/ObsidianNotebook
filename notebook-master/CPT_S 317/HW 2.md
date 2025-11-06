**Charles Liu**
Dr. Zhe Dang
CPT_S 317

___

1. Let $L$ be a regular language. Define $\text{End}(L, a) = \{x : x \in L\text{ and }x\text{ is ended}$$\text{ with symbol a}\}$. Show that $\text{End}(L, a)$ is a regular language.  

	1. Consider $L = \emptyset$, $\text{End(L,a)}$ is $\emptyset$ which is regular
	2. Consider $L = \{ \wedge \}$, we know that doesn't end in $a$ so $\text{End}(L,a)$ is $\emptyset$ which is regular
	3. Consider $L = \{b\}$,  where $b$ could equal $a$ or not. If $b=a$, we know $\text{End}(L,b) = \{a\}$ which is regular. Likewise, if $b \neq a$, $\text{End}(L,b) = \emptyset$ which is regular.
	4. Consider arbitrary regular languages $L_1$ and $L_2$. If $\text{End}(L_1, a)$ and $\text{End}(L_2, a)$ are regular languages, then:
		1. Consider $L = L_1 \cup L_2$. We know $\text{End}(L,a) = \text{End}(L_1, a) \cup \text{End}(L_2, a)$ is a union of regular languages which is regular.
		2. Consider $L = L_1L_2$. Consider if $L_2 \neq \Lambda$. That means the ending of $L$ depends on $L_2$, so $\text{End}(L_1L_2, a) = L_1\text{End}(L_2,a)$, which is the concatenation of regular languages and thus regular. Next consider if $L_2 = \Lambda$. Then the ending depends on $L_1$, so $\text{End}(L_1L_2, a) = \text{End}(L_1,a)$ which is also regular.
		3. Consider $L = L_1^*$. We know that the ending depends on $L_1$ and the prefix is just some power of $L_1$, so $\text{End}(L,a) = L_1^*\text{End}(L_1,a)$, which is regular.

___

2. Assume that $L$ is $((aa + bbb)^*c)^*$.  
What is a regular expression for language $\text{End}(L, a)$?

If a string is in $\text{End}(L,a)$, it has to end with $a$, but for $((aa + bbb)^*c)^*$, the string must end in $c$ or be an empty string. Thus, no strings lie in $\text{End}(L,a)$, and the regular expression is
$$\emptyset$$

___

3. For a word $x$, we use $x^r$ to denote its reverse (e.g., the reverse of $abaac$ is $caaba$). For a language $L$, we use $L^r$ to denote $\{x^r : x \in L\}$. Show that if $L$ is regular then so is $L^r$.  

	1. Consider $L = \emptyset$. We find $L^r = \emptyset$ which is also regular.
	2. Consider $L = \{ \Lambda \}$. We find $L^r  = \Lambda$ which is also regular
	3. Consider $L = \{y\}$. We find $L^r = \{ y \}$ which is also regular
	4. Consider arbitrary regular languages $L_1$ and $L_2$. 
		1. Consider $L = L_1 \cup L_2$. We find $L^r = L_1^r \cup L_2^r$ which is the union of regular languages, and thus regular.
		2. Consider $L = L_1L_2$. We find $L^r = L_2^rL_1^r$ which is the concatenation of regular languages and thus regular.
		3. Consider $L = L_1^*$. We find $L^r = (L_1^r)^*$ which is the Kleene-star of regular languages and thus regular.
___

4. Assume that $L$ is $((aa + bbb)^*c)^*bc$. What is a regular expression for language $L^r$?

$$cb(c(aa+bbb)^*)^*$$

___

5. Let $L$ be a regular language defined by the following regular expression: $((aa + bbb)^* + ca)a^*(b + c)$.  
List all the shortest words in $L$.  

The two shortest words are $b, c \in L$
___

6. Describe an algorithm that finds all shortest words in a regular language  
defined by a regular expression $r$

*Algorithm:* `ShortestWord`
*Input:* Regular Expression $r$
1. If $r = \{\emptyset\}$, output $\Lambda$.
2. If $r = \{\Lambda\}$, output $\Lambda$.
3. If $r = r_1 + r_2$ where $r_1,r_2$ are regular languages,
	1. Output  `ShortestWord`($r_1$)  if `ShortestWord`($r_1$) $\le$ `ShortestWord`($r_2$)
	2. Output `ShortestWord`($r_2$) if `ShortestWord`($r_2$) $\le$ `ShortestWord`($r_1$)
4. If $r = r_1r_2$, output `ShortestWord`($r_1$) $\cdot$ `ShortestWord`($r_2$)
5. If $r = r_1^*$, output $\Lambda$

___