**Charles Liu**
Dr. Zhe Dang
$8/25/2025$
___

A traffic light color sequence repeats the color pattern RGY (in this order)  for any times including $0$ times, where $R$ is for red, $G$ is for green, and $Y$ is for yellow. 

Write a C-program (or Java if you never did C before) that uses exactly two Boolean variables `b1` and `b2` that, for any input word w (you type it from keyboard, ended with end-of-line) that is on alphabet $\{R,G,Y\}$,  returns yes if $w$ is a traffic light color sequence; return no if not.

___

1. Code & Screenshot

```c
#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>
#include <stdbool.h>
#include <string.h>

bool x1 = false;
bool x2 = false;

int main(void) {
    char str[100];
    printf("Enter a string: ");
    scanf("%99s", str);
    while (str[0] != '\0') {
        if (!x1 && !x2) {
            if (str[0] == 'R' || str[0] == 'r') {
                x1 = false;
                x2 = true;
            }
            else {
                x1 = true;
                x2 = true;
            }
        }
        else if (!x1 && x2){
            if (str[0] == 'G' || str[0] == 'g') {
                x1 = true;
                x2 = false;
            }
            else {
                x1 = true;
                x2 = true;
            }
        }
        else if (x1 && !x2) {
            if (str[0] == 'Y' || str[0] == 'y') {
                x1 = false;
                x2 = false;
            }
            else {
                x1 = true;
                x2 = true;
            }
        }
        else {
            x1 = true;
            x2 = true;
        }
        // shift all characters one position to the left
        // delete first character
        memmove(str, str + 1, strlen(str))
    }

    if (!x1 && !x2) {
        printf("yes\n");
    } else {
        printf("no\n");
    }

    return 0;
}
```

![[HW 0 Screenshot.png]]

___

2. If I require that the sequence shall repeat $RGY$ for at least three times, how may Boolean variables shall I use (still two?)? Please state your reasoning.

We need $4$ boolean variables. We need two bits to represent the four state transitions between empty to R, R to G, G to Y, and Y back to empty as seen in the first example. We need two more to keep track of how many times $RGY$ was repeated. Two bits can store up to the number four, and we need a counter to track if at least $3$ $RGY$'s were shown.

___