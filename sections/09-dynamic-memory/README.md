# Dynamic Memory

## Overview
Dynamic memory allocation lets you request memory at runtime. The standard library provides `malloc`, `calloc`, `realloc`, and `free` to manage heap memory. Proper handling avoids leaks and corruption.

## Detailed Explanation
- **malloc**: Allocates a block of memory of specified size; contents are uninitialized.
- **calloc**: Like `malloc` but initializes memory to zero and takes element count and size as arguments.
- **realloc**: Changes the size of an existing allocation, preserving data up to the smaller of old and new sizes.
- **free**: Releases previously allocated memory back to the system.
- **Memory Management**: Failing to free memory results in leaks; double-freeing leads to undefined behavior.

## Code Examples
```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
    int *arr = malloc(3 * sizeof(int));
    if (!arr) return 1;            // always check for allocation failure
    arr[0] = 1; arr[1] = 2; arr[2] = 3;

    int *bigger = realloc(arr, 5 * sizeof(int));
    if (!bigger) { free(arr); return 1; }
    arr = bigger;
    arr[3] = 4; arr[4] = 5;

    for (int i = 0; i < 5; i++)
        printf("%d ", arr[i]);
    printf("\n");

    free(arr);                     // release memory when done
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Memory leaks** occur when allocated blocks are not freed.
2. **Using freed memory** (dangling pointers) can lead to crashes or corruption.

## Best Practices
- Set pointers to `NULL` after calling `free` to avoid accidental reuse.
- Prefer `calloc` when you need zero-initialized memory.

## Mini Exercise
Allocate an array of 10 integers using `malloc`. Fill it with values from 1 to 10, print them, then free the memory.
