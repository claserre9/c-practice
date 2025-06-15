# Debugging and Profiling

## Overview
Effective debugging tools like `gdb` and profilers such as `valgrind` or `perf` help locate bugs and performance issues. Sanitizers catch memory errors and undefined behavior at runtime.

## Detailed Explanation
- **gdb**: The GNU Debugger allows you to set breakpoints, inspect variables, and step through code line by line.
- **valgrind**: Detects memory leaks, invalid accesses, and other memory-related bugs.
- **perf**: A Linux tool for profiling CPU usage and identifying slow functions.
- **Sanitizers**: Compile with `-fsanitize=address` or `-fsanitize=undefined` to detect common programming errors.

## Code Examples
Compile with debugging symbols:
```bash
gcc -g main.c -o main
```
Run gdb:
```bash
gdb ./main
(gdb) break main
(gdb) run
```
Use valgrind:
```bash
valgrind ./main
```

## Common Pitfalls & Warnings
1. **Optimized builds** may rearrange code, making debugging harder. Compile without `-O2` when debugging.
2. **Ignoring warning messages** can let bugs slip through. Use `-Wall -Wextra`.

## Best Practices
- Reproduce bugs consistently before using the debugger.
- Profile release builds to get realistic performance numbers.

## Mini Exercise
Compile a small program with `-fsanitize=address` and intentionally access memory out of bounds to see the sanitizer report.
