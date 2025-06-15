# Compilation and Linking

## Overview
Compilation transforms source code into object files, and linking combines those objects into an executable. Understanding this process helps diagnose build errors and manage large projects.

## Detailed Explanation
- **Preprocessing**: Handles `#include` and `#define` directives, producing expanded source code.
- **Compilation**: Converts preprocessed code into machine-specific object files (`.o` or `.obj`).
- **Linking**: Resolves references between object files and libraries, producing the final executable or library.
- **Static vs. Dynamic Linking**: Static linking copies library code into the executable, while dynamic linking references shared libraries at runtime.

## Code Examples
```bash
# Compile without linking (produces main.o)
gcc -c main.c

# Link object file into executable
gcc main.o -o program

# All-in-one compile and link
gcc main.c -o program
```
A program split across multiple files:
```c
// main.c
#include "util.h"
int main(void) {
    say_hello();
    return 0;
}

// util.c
#include <stdio.h>
#include "util.h"
void say_hello(void) {
    printf("Hello!\n");
}
```
Compile and link:
```bash
gcc -c main.c util.c
gcc main.o util.o -o program
```

## Common Pitfalls & Warnings
1. **Missing prototypes** can lead to implicit function declarations (C89) or errors.
2. **Linker errors** occur when object files or libraries are omitted from the command line.

## Best Practices
- Use header files to declare functions and share them across source files.
- Keep compilation commands in a build system (Makefile, CMake) for consistency.

## Mini Exercise
Create two source files with one function each. Compile them separately, then link them together to produce an executable that calls both functions.
