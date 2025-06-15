# Modular Programming

## Overview
Large programs benefit from separating code into multiple files. Header files expose function prototypes and type definitions, while source files contain implementations. This modular structure improves organization and maintainability.

## Detailed Explanation
- **Headers (.h)**: Contain declarations for functions, structs, and macros that other files need to use.
- **Source Files (.c)**: Implement the functions declared in headers.
- **Separate Compilation**: Compile each source file individually, then link the resulting objects.
- **Encapsulation**: By exposing only necessary details in headers, you can change the implementation without affecting dependent code.

## Code Examples
```c
// math_utils.h
#ifndef MATH_UTILS_H
#define MATH_UTILS_H
int add(int a, int b);
#endif

// math_utils.c
#include "math_utils.h"
int add(int a, int b) { return a + b; }

// main.c
#include <stdio.h>
#include "math_utils.h"
int main(void) {
    printf("2+3=%d\n", add(2,3));
    return 0;
}
```
Compile separately:
```bash
gcc -c main.c math_utils.c
gcc main.o math_utils.o -o app
```

## Common Pitfalls & Warnings
1. **Multiple definitions** occur if a function is defined in more than one file or included incorrectly.
2. **Missing header guards** can cause duplicate declarations when a header is included multiple times.

## Best Practices
- Use `#ifndef`, `#define`, and `#endif` to guard headers.
- Keep each source file focused on a specific module or feature.

## Mini Exercise
Split a small program into two source files and one header. Make sure the header has an include guard and that the program compiles successfully.
