Here's a C program to convert a decimal number into binary, hexadecimal, and octal:


#include <stdio.h>

// Function to convert decimal to binary
void decimal_to_binary(int num) {
    int binary[32];
    int i = 0;
    while (num > 0) {
        binary[i++] = num % 2;
        num = num / 2;
    }
    printf("Binary: ");
    for (int j = i - 1; j >= 0; j--) {
        printf("%d", binary[j]);
    }
    printf("\n");
}

// Function to convert decimal to hexadecimal
void decimal_to_hexadecimal(int num) {
    printf("Hexadecimal: %x\n", num);
}

// Function to convert decimal to octal
void decimal_to_octal(int num) {
    printf("Octal: %o\n", num);
}

int main() {
    int decimal_num;
    printf("Enter a decimal number: ");
    scanf("%d", &decimal_num);

    printf("Decimal: %d\n", decimal_num);
    decimal_to_binary(decimal_num);
    decimal_to_hexadecimal(decimal_num);
    decimal_to_octal(decimal_num);

    return 0;
}


Explanation:

1. The program includes three functions: decimal_to_binary, decimal_to_hexadecimal, and decimal_to_octal.
2. decimal_to_binary manually converts the decimal number to binary using an array to store the binary digits.
3. decimal_to_hexadecimal and decimal_to_octal use printf's format specifiers %x and %o to directly print the hexadecimal and octal representations.
4. In main, the user is prompted to enter a decimal number.
5. The program then calls the conversion functions to display the binary, hexadecimal, and octal representations.

Example Output:


Enter a decimal number: 10
Decimal: 10
Binary: 1010
Hexadecimal: a
Octal: 12


*Alternative Implementation Using itoa Function:*

If you want to use the itoa function for conversion:


#include <stdio.h>
#include <stdlib.h>

void decimal_conversion() {
    int decimal_num;
    char binary[33];
    char hexadecimal[9];
    char octal[9];

    printf("Enter a decimal number: ");
    scanf("%d", &decimal_num);

    printf("Decimal: %d\n", decimal_num);
    
    // Convert decimal to binary
    itoa(decimal_num, binary, 2);
    printf("Binary: %s\n", binary);
    
    // Convert decimal to hexadecimal
    itoa(decimal_num, hexadecimal, 16);
    printf("Hexadecimal: %s\n", hexadecimal);
    
    // Convert decimal to octal
    itoa(decimal_num, octal, 8);
    printf("Octal: %s\n", octal);
}

int main() {
    decimal_conversion();
    return 0;
}


Note that the itoa function is not part of the standard C library, but it's available in some compilers. For portable code, consider using the first implementation.
