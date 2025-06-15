# Error Handling

## Overview
C programs use return codes and `errno` to signal errors. Proper error handling ensures robustness by detecting and responding to failures in system calls and library functions.

## Detailed Explanation
- **Return Codes**: Many functions return `0` on success or `-1` on failure. Inspect the return value to detect errors.
- **errno**: A global variable set by system calls and some library functions to indicate the error type. Use `perror` or `strerror` to print human-readable messages.
- **Library Functions**: Some functions return error indicators, such as `NULL` pointers or negative values.
- **Cleanup**: When an error occurs, release any acquired resources before exiting.

## Code Examples
```c
#include <stdio.h>
#include <errno.h>
#include <string.h>

int main(void) {
    FILE *f = fopen("nonexistent.txt", "r");
    if (!f) {
        perror("open failed");     // prints message based on errno
        return 1;
    }
    fclose(f);
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Ignoring return values** can let errors go unnoticed until later.
2. **Using `errno` without checking the return value** may report stale errors from previous operations.

## Best Practices
- Immediately check function return values and handle errors appropriately.
- Provide helpful messages using `perror` or `strerror` to aid debugging.

## Mini Exercise
Write a program that opens a file specified on the command line. If the file can't be opened, print an error message using `perror`.
