# Variables and Data Types

## Overview
Variables store data that your program manipulates. C supports several built-in types such as `int`, `char`, and `float`. You declare a variable by specifying its type followed by a name. Proper understanding of data types ensures correct memory usage and predictable results.

## Detailed Explanation
- **Primitive Types**: C offers integer types (`short`, `int`, `long`, `long long`), floating-point types (`float`, `double`), and the character type `char`.
- **Declarations**: A declaration allocates storage when placed outside functions or inside with an initializer. Example: `int count = 0;`.
- **Initialization**: Uninitialized variables have indeterminate values. Always initialize before use to avoid undefined behavior.
- **Type Qualifiers**: `signed`, `unsigned`, and `const` modify how data is interpreted. `unsigned int` stores only non-negative values.

## Code Examples
```c
#include <stdio.h>

int main(void) {
    int age = 25;          // integer variable
    float weight = 70.5f;  // floating-point variable
    char initial = 'A';    // character variable

    printf("Age: %d\n", age);
    printf("Weight: %.1f\n", weight);
    printf("Initial: %c\n", initial);
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Using uninitialized variables**: Reading an uninitialized value leads to unpredictable results.
2. **Overflow and underflow**: Storing values beyond a type's range causes wraparound or truncation.

## Best Practices
- Prefer explicit initialization, e.g., `int x = 0;`.
- Use `sizeof(type)` to verify type sizes if portability matters.

## Mini Exercise
Declare variables for your name, age, and a favorite number. Initialize them and print them using `printf`.
