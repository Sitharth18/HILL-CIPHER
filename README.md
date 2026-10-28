# HILL CIPHER

EX. NO: 3 
## NAME:SITHARTH B S
## REG NO:212224110048
## AIM:
 
To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:

STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM 
```

#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char text[100];
    int key[3][3], i, j, k, sum;

    printf("Enter plaintext: ");
    scanf("%s", text);

    printf("Enter 3x3 key matrix:\n");
    for (i = 0; i < 3; i++)
        for (j = 0; j < 3; j++)
            scanf("%d", &key[i][j]);

    int len = strlen(text);

    while (len % 3 != 0)
        text[len++] = 'X';
    text[len] = '\0';

    printf("Ciphertext: ");

    for (i = 0; i < len; i += 3) {
        int p[3];

        for (j = 0; j < 3; j++)
            p[j] = toupper(text[i + j]) - 'A';

        for (j = 0; j < 3; j++) {
            sum = 0;
            for (k = 0; k < 3; k++)
                sum += key[j][k] * p[k];

            printf("%c", (sum % 26) + 'A');
        }
    }

    return 0;
}
```
## OUTPUT
<img width="1917" height="930" alt="image" src="https://github.com/user-attachments/assets/787a19db-14d9-444e-99ab-b6fc32fcd606" />


## RESULT
The program is executed successfully.

