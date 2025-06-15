# Pointers and Memory

## Overview
Pointers store memory addresses. They enable dynamic data structures, arrays, and inter-function communication via references. Mastering pointers is essential to effective C programming.

## Detailed Explanation
- **Pointer Basics**: Declared with `*`, e.g., `int *ptr;`. The `&` operator yields the address of a variable, while `*` dereferences a pointer to access the value it points to.
- **NULL Pointers**: A pointer that doesn't reference valid memory should be set to `NULL` to avoid accidental access.
- **Pointer Arithmetic**: Adding 1 to an `int*` moves the pointer by `sizeof(int)` bytes. This is useful for iterating over arrays.
- **Memory Layout**: Understanding stack vs. heap helps avoid dangling pointers and memory leaks.

## Code Examples
```c
#include <stdio.h>

int main(void) {
    int value = 42;
    int *ptr = &value;          // ptr holds the address of value

    printf("value=%d\n", *ptr); // dereference to get the value

    *ptr = 100;                 // modify value via the pointer
    printf("value=%d\n", value);

    int arr[3] = {1,2,3};
    int *p = arr;               // arrays decay to pointers
    printf("second element=%d\n", *(p + 1));
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Dereferencing an uninitialized pointer** leads to undefined behavior.
2. **Pointer arithmetic on incompatible types** can corrupt memory or crash the program.

## Best Practices
- Always initialize pointers before use.
- Use `const` with pointers to data that shouldn't be modified.

## Mini Exercise
Write a program that swaps two integers using a function with pointer parameters.
