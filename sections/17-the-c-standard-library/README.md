# The C Standard Library

## Overview
C's standard library (`libc`) provides numerous headers offering functions for strings, memory management, math, and time handling. Familiarity with these libraries reduces the need for custom solutions.

## Detailed Explanation
- **string.h**: Functions like `strlen`, `strcpy`, `strchr`, and `strcmp` operate on null-terminated strings.
- **stdlib.h**: Offers memory allocation (`malloc`, `free`), conversion (`atoi`, `strtol`), and process control (`exit`, `system`).
- **math.h**: Provides mathematical functions such as `sin`, `sqrt`, and `pow` (link with `-lm`).
- **time.h**: Work with calendar time using `time`, `localtime`, and `strftime`.
- **Compiler Behavior**: Some functions may be implemented as macros; include their respective headers to avoid warnings.

## Code Examples
```c
#include <stdio.h>
#include <string.h>
#include <math.h>

int main(void) {
    char msg[] = "hello";
    printf("length=%zu\n", strlen(msg));

    double root = sqrt(16.0);     // math.h
    printf("sqrt=%f\n", root);
    return 0;
}
```
Compile with:
```bash
gcc main.c -lm -o main
```

## Common Pitfalls & Warnings
1. **Forgetting to link with `-lm`** when using math functions results in linker errors.
2. **Using string functions without enough buffer space** leads to overflows.

## Best Practices
- Prefer standard library functions over custom implementations for reliability.
- Consult documentation for platform-specific nuances or thread safety.

## Mini Exercise
Write a program that prints the current year using `time.h` functions.
