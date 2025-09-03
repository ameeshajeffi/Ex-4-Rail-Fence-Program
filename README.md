<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a03d37ee-7c77-4675-a5f4-428705a3e8c6" /># Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE
REG NO : 212223220007
DATE : 03/09/2025
# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
 #include <stdio.h>
 #include <string.h>
 #include <ctype.h>
 void encryptRailFence(char *message, int rails) {
 int len = strlen(message);
 char rail[rails][len];
 memset(rail, '\n', sizeof(rail));
 int row = 0, direction = 1;
 for (int i = 0; i < len; i++) {
 rail[row][i] = message[i];
 row += direction;
 if (row == rails- 1 | row == 0)
 direction =-direction;
 }
 printf("Encrypted text: ");
 for (int i = 0; i < rails; i++)
 for (int j = 0; j < len; j++)
 if (rail[i][j] != '\n')
 printf("%c", rail[i][j]);
 printf("\n");
 }
 int main() {
 char message[100];
 int rails;
 printf("Enter a Secret Message: ");
 scanf("%s", message);
 printf("Enter number of rails: ");
 scanf("%d", &rails);
 encryptRailFence(message, rails);
 return 0;
 }
```

# OUTPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/76ae7aea-cb60-42e1-8001-9e871dc92067" />

# RESULT
The program is executed successfully.
