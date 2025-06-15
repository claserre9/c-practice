# Control Flow

## Overview
Control flow statements guide the execution path of a program. C provides conditional statements (`if`, `switch`) and loops (`for`, `while`, `do-while`) to repeat or skip code segments. Understanding these constructs allows you to build complex logic.

## Detailed Explanation
- **if/else**: Evaluates a condition; executes a block if true, optionally another block if false.
- **switch**: Selects a code path based on an integer or enumeration value. `break` prevents fall-through.
- **Loops**: `for` loops are common when you know iteration counts, while `while`/`do-while` loops continue until a condition changes.
- **goto**: Jumps to a labeled statement. Rarely needed but available for certain low-level tasks.

## Code Examples
```c
#include <stdio.h>

int main(void) {
    int num = 3;

    if (num > 0) {
        printf("Positive\n");
    } else {
        printf("Non-positive\n");
    }

    switch (num) {
        case 1: printf("One\n"); break;
        case 2: printf("Two\n"); break;
        default: printf("Other\n");
    }

    for (int i = 0; i < 3; i++) {
        printf("i=%d\n", i);
    }

    int j = 0;
    while (j < 3) {
        printf("j=%d\n", j);
        j++;
    }
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Forgetting `break` in `switch` cases** causes unintended fall-through.
2. **Infinite loops** happen when the loop condition never becomes false.

## Best Practices
- Keep loop bodies small and focused.
- Use `switch` with enumerations for readability and compiler checking.

## Mini Exercise
Write a program that prints the numbers 1 through 10 using a `while` loop, but skips multiples of 3 using `continue`.
