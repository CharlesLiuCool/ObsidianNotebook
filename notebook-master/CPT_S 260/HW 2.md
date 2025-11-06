**Charles Liu**
Dr. Abhishek Moitra
$9/4/2025$

___

1. ($10$ points) What is the difference between unsigned numbers and signed numbers in binary? Explain $2$’s complement numbers using a simple example. 

Unsigned numbers is all the numbers representable with some amount of bits greater than or equal to $0$. For instance $1000$ would represent decimal value $8$. However, signed numbers considers both negative and positive values representable with some amount of bits. For instance, $1000$ in $2$'s complement represents $-8$ if under $4$-bit width.

___

2. ($20$ points) Convert the decimal number $(1405)_{10}$ to its equivalent binary and hexadecimal. What is the minimum number of bits that you need for each base? (You can show decimal numbers using $d$: $1405d = (1405)_{10}$), and $h$ for hexadecimal numbers, and $b$ for binary numbers). Extend the sign of this number and convert it to a $16$-bit binary.

$1405/2 = 702\;R\;1$
$702/2 = 351\;R\;0$
$351/2 = 175\;R\;1$
$175/2 = 87\;R\;1$
$87/2 = 43\;R\;1$
$43/2 = 21\;R\;1$
$21/2 = 10\;R\;1$
$10/2 = 5\;R\;0$
$5/2 = 2\;R\;1$
$2/2 = 1\;R\;0$
$1/2 = 0\;R\;1$

So the decimal $1405_d$ in binary is the concatenation of the remainders, or
$$10101111101_b$$

For the hexadecimal, we look at groups of $4$ bits and append $0$ to the front as necessary, getting the following three groups: $0101|0111|1101$

Checking the lookup table:
$0101 \to 5$
$0111 \to 7$
$1101 \to D$

Therefore, we get that $1405_{10}$ in hex is
$$57D_h$$

We count that for binary, we need a minimum of $11$ bits, whereas in hexidecimal, we only need $3$.

The extension of the binary to $16$ bits is
$$0000010101111101_b$$

___

3. ($10$ points) Show $(−1405)_{10}$ as a $2$’s complement signed number.

First take the magnitude of $-1405_{10}$ and convert it to binary.
$|-1405_{10}| = 1405_{10}$
in $16$-bit binary, that is $0000010101111101_b$

Invert the expression.
$0000010101111101_b \to 1111101010000010_b$

Add $1$
$1111101010000010_b \to 1111101010000011_b$

So we get $-1405_{10}$ in two's complement is
$$1111101010000011_b$$

4. ($10$ points) Show the steps of each addition in $8$-bit binary format. Check if there is overflow for operation.  
*a.* $(-30) + (+12)$

Step 1: Convert $-30$ to two's complement
Magnitude: $|-30| = 30$
Binary Conversion: 
$30/2 = 15\;R\;0$
$15/2 = 7\;R\;1$
$7/2 = 3\;R\;1$
$3/2 = 1\;R\;1$
$1/2 = 0\;R\;1$
So, $30_{10} = 00011110_2$
Invert: $11100001_2$
Add $1$: $11100010_2$

Step 2: Convert $12$ to two's complement
Binary Conversion:
$12/2 = 6\;R\;0$
$6/2 = 3\;R\;0$
$3/2 = 1\;R\;1$
$1/2 = 0\;R\;1$
$12_{10} = 00001100_2$

Step 3: Add the two
$$(-30_{10}) + (12_{10}) =  11100010_2 + 00001100_2 = 11101110_2$$

No overflow, the most significant bit is $1+0$ which has no carry bit.

*b.* $(-98) - (64)$

This equals $(-98) + (-64)$

Step 1: Convert $-98$
Magnitude: $|-98| = 98$
Binary Conversion:
$98/2 = 49\;R\;0$
$49/2 = 24\;R\;1$
$24/2 = 12\;R\;0$
$12/2 = 6\;R\;0$
$6/2 = 3\;R\;0$
$3/2 = 1 \;R\;1$
$1/2 = 0\;R\;1$
So, $98_{10} = 01100010_2$
Invert: $10011101_2$
Add $1$: $10011110_2$

Step 2: Convert $-64$
Binary Conversion
$64_{10} = 2^6_{10} = 01000000_2$
Invert: $10111111_2$
Add $1$: $11000000$

Step 3: Subtract the two
$(-98) + (-64) = 10011110_2 + 11000000_2 = 101011110_2$

Yes, the most significant bit is $1+1$ which has a carry bit of $1$ and results in an overflow.

___