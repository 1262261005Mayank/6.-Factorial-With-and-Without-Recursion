# 6.-Factorial-With-and-Without-Recursion.
#include <stdio.h>

unsigned long long factorial_iterative(int n) {
    unsigned long long fact = 1;
    for (int i = 2; i <= n; i++) {
        fact *= i;
    }
    return fact;
}

unsigned long long factorial_recursive(int n) {
    if (n <= 1) {
        return 1;
    }
    return (unsigned long long)n * factorial_recursive(n - 1);
}

int main() {
    int n;

    printf("Enter a non-negative integer (0-20): ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Factorial is not defined for negative numbers.\n");
        return 1;
    }
    if (n > 20) {
        printf("Warning: Values above 20 may overflow unsigned long long.\n");
    }

    printf("Factorial (without recursion): %llu\n", factorial_iterative(n));
    printf("Factorial (with recursion):    %llu\n", factorial_recursive(n));

    return 0;
}
