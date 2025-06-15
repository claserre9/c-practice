# Introduction to C

## Overview
C is a powerful systems programming language created in the early 1970s. It offers low-level memory access, a straightforward syntax, and widespread compiler support. Learning C provides a strong foundation for understanding how software interacts with hardware. This section guides you through installing a C compiler and writing your first program.

## Detailed Explanation
- **Installing a Compiler**: On Linux, install `gcc` via your package manager (e.g., `sudo apt install build-essential`). Windows users can use MinGW or the MSVC toolchain, while macOS users often rely on Xcode's command-line tools.
- **Hello World Program**: A minimal C program defines a `main` function returning `int`. Within `main`, `printf` outputs text. The compiler translates your code to an executable that runs on your operating system.
- **Compilation Process**: The typical workflow is `compile` (source code to object files) then `link` (combine objects into an executable). Tools like `gcc` handle both steps.
- **Why It Matters**: Understanding how to compile and run code is the first step toward exploring C's capabilities, including direct memory manipulation and performance-focused development.

## Code Examples
```c
#include <stdio.h>

int main(void) {
    // Prints a greeting to the console
    printf("Hello, World!\n");
    return 0;               // Signals successful execution
}
```
To compile and run with `gcc`:
```bash
gcc hello.c -o hello
./hello
```

## Common Pitfalls & Warnings
1. **Missing `#include <stdio.h>`**: Without including this header, the compiler doesn't know about `printf`, leading to warnings or errors.
2. **Mismatched braces**: Each opening `{` must have a matching `}`. Unbalanced braces lead to compilation errors.

## Best Practices
- Always return an `int` from `main` to indicate success or failure.
- Use `-Wall` with `gcc` to enable warnings, catching mistakes early.

## Mini Exercise
Create a file `greet.c` that prints your own custom greeting. Compile it with `gcc` and run the resulting executable.
