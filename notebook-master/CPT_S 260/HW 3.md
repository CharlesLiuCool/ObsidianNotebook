**Charles Liu**
Dr. Abhishek Moitra
$9/16/2025$

___

### **Float Numbers Conversion and Arithmetic**

1. Consider these two decimal numbers: $-112.25, +183.625$.  

*a)* Show the two numbers in the normalized form.  

$-1.1225 \times 10^2$
$1.83625 \times 10^2$

*b)* Convert the numbers into binary representation.  

$|-112_{10}| = 112_{10}$

$112_{10} \to 1110000_2$

$0.25_{10} \to 0.01_2$
$0.25 \times 2 = 0.5$
$0.5 \times 1 = 1$

>$112.25_{10} = 1110000.01_2 = 1.11000001_2 \times 2^{6}$

$183_{10} \to 10110111$
$0.625 \to 0.101$

$0.625 \times 2 = 1.25$
$0.25 \times 2 = 0.5$
$0.5 \times 2 = 1$

>$183.625_{10} = 10110111.101_2 = 1.0110111101_2 \times 2 ^{7}$

*c)* Using the IEEE $754$ single precision representation, show step by step procedure for addition of these numbers.  


$$\begin{align}&-1.11000001_2 \times 2^{6} + 1.0110111101_2 \times 2 ^{7} \\ &= -0.111000001_2 \times 2^{7} + 1.0100111101_2 \times 2 ^{7} \\ &= \\
&\;\;\;\;\;1.0100111101_2 \times 2^7\\ &\;\;-0.1110000010_2 \times 2^7\\ &\;\;\;\_\_\_\_\_\_\_\_\_\_\_\_\_\_\ \\ &= 0.1000111011_2 \times 2^7 \\ \\ &= 1.000111011_2 \times 2^6\end{align}$$

Note the bias in IEEE $754$ single precision representation is $127$

- Signed Bit: $0$
- Exponent: $6 + 127 = 133_{10} = 10000101_{2}$
- Fraction: $0001\;1101\;1000\;0000\;0000\;0000\;000$

The IEEE $754$ representation of the addition of $-112.25$ and $183.625$ is
$$0\;|\;10000101|\;0001\;1101\;1000\;0000\;0000\;0000\;000$$

*d)* Show the first number in the IEEE $754$ double precision format.  

Bias is $1023$

Consider $-112.25$
- signed bit is $1$
- exponent is $6 + 1023 = 1029 = 10000000101$
- fraction is $1100\;0001\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000$

So, in IEEE $754$ double-precision representation, this is
$$1 \;|\;10000000101\;| \;\underbrace{1100\;0001\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000\;0000}_{52 \text{ bits}}$$

___

2. IEEE $754-2008$ contains a half precision that is only $16$ bits wide. The leftmost bit is still the sign bit, the exponent is $5$ bits wide and has a bias of $15$, and the fractional part is $10$ bits long. A hidden $1$ is assumed. Write down the bit pattern to represent ( $-1.5625 \cdot 10^{-1}$ ) assuming a version of this format, which uses an excess-16 format to store the exponent. Comment on how the range and accuracy of this $16$-bit floating point format compares to the single precision IEEE $754$ standard.

 $-1.5625 \cdot 10^{-1} = -0.15625_{10}$

Take the magnitude
$|-0.15625_{10}| = 0.15625_{10}$

Convert to binary
$0.15625 \times 2 = 0.3125$
$0.3125 \times 2 = 0.625$
$0.625 \times 2 = 1.25$
$0.25 \times 2 = 0.5$
$0.5 \times 2 = 1$

So we get $0.15625_{10} = 0.00101_2 = 1.01 \times 2^{-3}$

The bias here is $15$, so
Signed Bit $= 1$
Exponent $=$ $-3_{10} + 15_{10} = 12_{10} = 01100$
Fraction $= 01000000$

$$1 \;|\; 01100\;|\;01000000$$

Commentary:

The range and accuracy of this $16$-bit format is way worse, offering only $5$ exponent bits compared to the $11$ in IEEE $754$ single-precision representation, and only $10$ fractional bits compared to $23$ bits.

That means in the $16$-bit format, it can only handle a range of around $\log_{10}(2^{2^{5}}) \approx 10^{\pm 10}$, whereas in IEEE $754$ single-precision representation it can extend to about $\log_{10}(2^{2^{11}}) \approx 10^{\pm 38}$, a HUGE gap.

Likewise for the fraction, $16$-bit can only handle $\log_{10}(2^{10}) \approx 3$ decimal places of precision whereas the IEEE $754$ can do around $\log_{10}(2^{23}) \approx 7$ decimal places.

___

3. Consider the decimal number ($-21.625$). Write down binary representation of this number using the IEEE $754$ single precision format. Clearly specify “Sign”, “Exponent” and “Mantissa/Fraction” fields of the single precision representation. Specify whether the number can be exactly represented by the single precision format or not.  


$|-21.625_{10}| = 21.625_{10}$

$21_{10} = 10101_2$

$0.625 \times 2 = 1.25$
$0.25 \times 2 = 0.5$
$0.5 \times 2 = 1$

$0.625_{10} = 0.101_2$

$21.625_{10} = 10101.101_2 = 1.0101101_2 \times 2^{4}$

Recall bias is $127$

Signed bit: $1$ (since $-21.625$ is negative)
Exponent: $4_{10} + 127_{10} = 131_{10} = 10000011_2$ 
Mantissa/Fraction: $0101\;1010\;0000\;0000\;0000\;000$

Thus, the IEEE$754$ single representation of $-21.625_{10}$ is
$$\underbrace{1}_{\text{Sign}} \;|\;\underbrace{1000\;0011}_{\text{Exponent}} \;|\; \underbrace{0101\;1010\;0000\;0000\;0000\;000}_{\text{Fraction/Mantissa}}$$

The number can be fully represented in single precision format.

___

### **MIPS Instruction Code**  
Consider the following C code snippet:  
```cpp
int a, b, c, d, e, f, g, h, result;  
result = (a + b) - (c + d) + (e - f) + g - h;  
```

All variables are $32$-bit ($4$-byte) integers stored in contiguous memory locations.  

**Part A: Memory Addressing**  

Let the global pointer register (\$gp) store the base address of the memory region. Assume byte-addressable memory.

*Q$1$*: What are the addresses of variables $a,b,c,d,e,f,g,h$?

$a \to 0(\$gp)$
$b \to 4(\$gp)$
$c \to 8(\$gp)$
$d \to 12(\$gp)$
$e \to 16(\$gp)$
$f \to 20(\$gp)$
$g \to 24(\$gp)$
$h \to 28(\$gp)$

*Q$2$*: Suppose the output variable result is stored immediately after $h$. What will be its address?

$32(\$gp)$

*Q$3$*: How many memory load (lw) and memory store (sw) instructions are required for this code?

$8$ lw and  $1$ sw for a total of $9$ of those instructions.

**Part B: Assembly Translation**

Write the MIPS assembly code that implements the expression. Use load and store operations relative to the (\$gp). Store the final result back to memory address reserved for result.

```nasm
lw $s0, 0($gp)
lw $s1, 4($gp)
lw $s2, 8($gp)
lw $s3, 12($gp)
lw $s4, 16($gp)
lw $s5, 20($gp)
lw $s6, 24($gp)
lw $s7, 28($gp)

add $t0, $s0, $s1
add $t1, $s2, $s3
sub $t2, $s4, $s5
sub $t3, $s6, $s7
sub $t4, $t0, $t1
add $t5, $t4, $t2
add $t6, $t5, $t3

sw $t6, 32($gp)
```


___

### **Extra Credit Questions**

1. Compare the number of memory accesses to the number of ALU operations. 

There are more memory accesses ($9$) than ALU operations ($7$).

2. Why is minimizing memory loads/stores important for performance on real hardware?

Memory accesses are usually slower than ALU operations and require more lines in assembly, so we want to cut down on those by optimizing register usage to improve performance.

___