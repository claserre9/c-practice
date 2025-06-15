# Functions

## Overview
Functions encapsulate reusable blocks of code. In C, you declare functions with a return type, name, and parameter list. Using functions promotes modularity and simplifies maintenance.

## Detailed Explanation
- **Declaration vs. Definition**: A declaration (prototype) informs the compiler about a function's name and parameters, usually placed in a header. The definition contains the actual code.
- **Parameters**: Passed by value, meaning the function receives copies of arguments. Pointers are used for pass-by-reference behavior.
- **Recursion**: A function that calls itself. Each call pushes a new frame on the call stack until a base condition stops the recursion.

## Code Examples
```c
#include <stdio.h>

// Function prototype
double square(double x);

int main(void) {
    printf("4 squared = %.2f\n", square(4));
    return 0;
}

// Function definition
double square(double x) {
    return x * x; // multiplies the argument by itself
}
```

**Recursive example**:
```c
int factorial(int n) {
    if (n <= 1) return 1;      // base case
    return n * factorial(n-1); // recursive call
}
```

## Common Pitfalls & Warnings
1. **Mismatched declarations/definitions**: Parameter types or return types must match exactly.
2. **Infinite recursion** if the base case is missing or wrong.

## Best Practices
- Keep functions short and focused on one task.
- Provide clear prototypes in header files for external linkage.

## Mini Exercise
Implement a function `int sum(int a, int b)` that returns the sum of two integers. Write a `main` function that tests it with a few values.
