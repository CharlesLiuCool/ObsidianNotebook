**Charles Liu**
Dr. Abhishek Moitra
$10/21/2025$

___

1. Translate the following MIPS code into C. Assume that the variables $f, g, h, i$, and $j$ are assigned to registers $\$s0, \$s1, \$s2, \$s3$, and $\$s4$, respectively. Also assume that the base address for arrays $A$, and $B$ are stored in $\$s6, \$s7$, respectively.  
$$sll\;\$t0, \$s0, 2$$
$$add\;\$t0, \$s6, \$t0$$  
$$sll\;\$t1, \$s1, 2$$ 
$$add\;$t1, $s7, $t1$$
$$lw\;\$s0, 0(\$t0)$$
$$addi\;\$t2, \$t0, 4$$  
$$lw\;\$t0, 0(\$t2)$$
$$add\;$t0, \$t0, \$s0$$  
$$sw\;$t0, 0($t1)$$

```c
int *t0 = A + f;
int *t1 = B + g;
f = *t0;
int *t2 = t0 + 1;
temp0 = *t2;
temp0 = temp0 + f;
*t1 = temp0;
```

___

2. Assume that our MIPS processor has six $32$ bit registers and eight memory locations. Each memory location holds $32$ bits of data. The naming convention for the registers and the memory are shown in the table below.  

**Table 1: Register values**  

| Register | Initial  Value | `I1` | `I2` | `I3` | `I4` | `I5` | `I6` | `I7` |
| -------- | -------------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| `R1`     | $4$            | $4$  | $4$  | $4$  | $4$  | $4$  | $4$  | $4$  |
| `R2`     | $16$           | $16$ | $16$ | $16$ | $16$ | $16$ | $16$ | $16$ |
| `R3`     | $12$           | $10$ | $10$ | $10$ | $10$ | $10$ | $10$ | $10$ |
| `R4`     | $20$           | $20$ | $10$ | $10$ | $10$ | $10$ | $10$ | $10$ |
| `R5`     | $12$           | $12$ | $12$ | $12$ | $12$ | $12$ | $12$ | $12$ |
| `R6`     | $14$           | $14$ | $14$ | $14$ | $14$ | $14$ | $14$ | $14$     |


**Table 2: Memory values**  

| Address | Initial Value | `I1` | `I2` | `I3` | `I4` | `I5` | `I6` | `I7` |
| ------- | ------------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| $0$     | $10$          | $10$ | $10$ | $10$ | $10$ | $10$ | $10$ | $10$     |
| $4$     | $10$          | $10$ | $10$ | $10$ | $10$ | $10$ | $10$ | $10$     |
| $8$     | $18$          | $18$ | $18$ | $18$ | $18$ | $18$ | $18$ |  $18$    |
| $12$    | $30$          | $30$ | $30$ | $30$ | $30$ | $30$ | $30$ | $30$     |
| $16$    | $50$          | $50$ | $50$ | $50$ | $50$ | $50$ | $14$ | $14$     |
| $20$    | $24$          | $24$ | $24$ | $24$ | $24$ | $24$ | $24$ | $24$     |
| $24$    | $16$          | $16$ | $16$ | $16$ | $16$ | $16$ | $16$ | $16$     |
| $28$    | $0$           | $0$  | $0$  | $0$  | $0$  | $0$  | $0$  | $0$     | 

*a.* Now, let us assume that an array $A$ with $3$ integer (word) elements is stored starting from memory address zero and another array $B$ with $4$ integer (word) elements is at stored starting from memory address $16$. That is, address of $A[0]$ is $0$, while the address of $B[0]$ is $16$. With this information, fill the register value and memory tables for the following sequence of instructions. `I1`, `I2`, etc. denote the instruction number while LABEL denotes the target for the branch, if taken.  

`I1` : $\text{lw}\,R3, -4(R1)$  
`I2` : $\text{lw}\,R4, 0(R1)$
`I3` : $\text{beq}\, R3, R4, \text{Label}$ 
`I4` : $\text{sw} R5, 0(R2)$  
`I5` : $j \text{ Exit}$  
Label `I6` : $\text{sw } R6, 0(R2)$  
Exit `I7` : . . .  


*b.* What is the equivalent C code for the five instructions from part (a).

```cpp
int R3 = A[0];
int R4 = A[1]

if (R3 == R4) {
	B[0] = R6
} else {
	B[0] = R5
}
```

___

3. Translate the following loop into C. The integer ‘i’ is held in $\$t1$, $\$s2$ is used to hold an integer called result, and $\$s0$ holds the base address for an integer array MemArray.  

$$\text{addi } \$t1, \$\text{zero}, 0$$
$$\text{LOOP}: \text{lw }\$s1 , 0(\$s0)$$  
$$\text{add } \$s2, \$s2, \$s1$$  
$$\text{addi } \$s0, \$s0, 4$$ 
$$\text{addi } \$t1, \$t1, 1$$ 
$$\text{slti } \$t2, \$t1, 100$$  
$$\text{bne } \$t2, \$\text{zero}, \text{LOOP}$$  

```c
int i = 0;
int result = 0;
for (int i = 0; i < 100; i++) {
	int s1 = MemArray[i];
	result += s1;
}
```


___

4.  

*a.* Provide the type and assembly language instruction for the following binary value using the MIPS reference data sheet:  

$$(0000 00\;10000\;10000\;10000\;00000\;100000)_{(2)}$$

`opcode`:
$000000$
This means it is $R$-type

`rs` (source register $1$):
$10000_2 = 16_{10}$

$\$s0$

`rt` (source register $2$):
$10000$

$\$s0$

`rd` (destination register)
$10000$

$\$s0$

`shamt`
$00000$
No shift

`funct`
$1000000$
$\text{add}$

We get a $R$-type instruction:
$$\text{add }\$s0, \$s0, \$s0$$



*b.* Provide the type and hexadecimal representation of following instruction:  
$$\text{sw } \$t1, 32(\$t2)$$

`opcode`:
$\text{sw}$ corresponds to $43$, so its opcode is $101011$

It is $I$-type instruction.

`rs` (base register):
This is $\$t2$ which corresponds to $10$, which is $01010$

`rt` (data register):
This is $\$t1$ which corresponds to $9$, which is $01001$

`immediate`:
The offset is $32$, which is $0000\;0000\;0010\;0000$

Together, we get the following binary
$$101011\;01010\;01001\;0000000000100000$$

We convert each four bits into hexidecimal.

$1010 \to A$
$1101 \to D$
$0100 \to 4$
$1001 \to 9$
$0000 \to 0$
$0000 \to 0$
$0010 \to 2$
$0000 \to 0$

We get the following hexidecimal for the $I$-type instruction:
$$0\text{xAD490020}$$

___

5. Implement the following code in MIPS assembly. You may use the simulator to test out the code.  
Assume variables ‘a’ and ‘b’ are stored in $s0 and $s1 respectively. Also assume that the base  
addresses of arrays A and B are stored in registers $s2 and $s3, respectively.  
```c
a = A[0];  
b = B[1];  
if (a != b)  
	a = a + b;  
else  
	a = a - b;  
B[0] = a;
```

```mips
lw $t0, 0($s0)
lw $t1, 4($s1)
bne $t0, $t1, COND
sub $t0$, $t0$, $t1$
j END
COND:
	add $t0, $t0, $t1
END:
	sw $t0, 0($s1)

```

___