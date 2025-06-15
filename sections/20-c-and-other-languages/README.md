# C and Other Languages

## Overview
C often needs to interoperate with languages like Python, Rust, or Java through foreign function interfaces (FFI). Understanding how to expose C functions and data structures enables seamless integration.

## Detailed Explanation
- **Shared Libraries**: Compile C code with `-fPIC` and `-shared` to create shared objects (`.so` or `.dll`) that other languages can load.
- **Header Files**: Provide a clean C API with `extern "C"` when used from C++ to avoid name mangling.
- **Python Example**: The `ctypes` module can load a shared library and call C functions.
- **Rust Example**: Use `extern "C"` blocks in Rust to declare C functions and link to them.

## Code Examples
C library:
```c
// mylib.c
#include <stdio.h>
void hello(void) { printf("Hello from C!\n"); }
```
Compile:
```bash
gcc -fPIC -shared mylib.c -o libmylib.so
```
Python usage:
```python
from ctypes import CDLL
lib = CDLL('./libmylib.so')
lib.hello()
```

## Common Pitfalls & Warnings
1. **Mismatch in calling conventions** can cause crashes when crossing language boundaries.
2. **Memory ownership** must be clear—who allocates and who frees? Document this in the API.

## Best Practices
- Keep the C API simple and use plain data types for maximum compatibility.
- Provide clear build instructions for creating shared libraries on different platforms.

## Mini Exercise
Create a simple C library that returns the length of a string. Load it in Python using `ctypes` and print the result.
