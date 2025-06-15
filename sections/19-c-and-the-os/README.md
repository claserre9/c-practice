# C and the OS

## Overview
Interacting with the operating system allows programs to perform tasks like creating processes, managing signals, and using system calls. C is well-suited for OS-level programming because many kernels expose C APIs.

## Detailed Explanation
- **System Calls**: Functions like `open`, `read`, and `write` interface directly with the kernel. They return `-1` and set `errno` on error.
- **Processes**: `fork` creates a new process by duplicating the current one. `exec` replaces the process image with a new program.
- **Signals**: Asynchronous notifications like `SIGINT` can be caught with `signal` or `sigaction` to perform cleanup or custom handling.
- **File Descriptors**: Integers representing open files; used by many system calls for I/O.

## Code Examples
```c
#include <stdio.h>
#include <unistd.h>
#include <sys/wait.h>

int main(void) {
    pid_t pid = fork();
    if (pid == 0) {
        printf("Child process\n");
    } else {
        wait(NULL);
        printf("Parent process\n");
    }
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Forgetting to handle `fork` failure** can lead to unexpected behavior if system resources are low.
2. **Ignoring return values** from system calls may cause subtle bugs and resource leaks.

## Best Practices
- Check all system call results and handle errors gracefully.
- Use `sigaction` instead of the older `signal` function for reliable signal handling.

## Mini Exercise
Write a program that spawns a child process with `fork`. The child should print its PID, and the parent should print the child's PID after it finishes.
