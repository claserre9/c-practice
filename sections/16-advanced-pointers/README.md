# Advanced Pointers

## Overview
Beyond basic pointers, C allows pointer arithmetic, function pointers, and pointers to pointers. These features enable dynamic data structures and callback mechanisms.

## Detailed Explanation
- **Pointer Arithmetic**: Adding or subtracting integers moves a pointer by multiples of the pointed-to type size.
- **Function Pointers**: Store addresses of functions, enabling callbacks and dynamic dispatch. Syntax: `return_type (*name)(param_types)`.
- **Pointers to Pointers**: Useful for modifying pointer arguments or representing multidimensional arrays.

## Code Examples
```c
#include <stdio.h>

void greet(void) { printf("Hello\n"); }
void (*func_ptr)(void);   // function pointer

int main(void) {
    func_ptr = greet;     // assign address
    func_ptr();           // call via pointer

    int arr[3] = {1,2,3};
    int *p = arr;
    printf("second=%d\n", *(p + 1));

    int **pp;            // pointer to pointer
    int value = 5;
    int *pvalue = &value;
    pp = &pvalue;
    printf("%d\n", **pp);  // prints 5
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Incorrect function pointer signatures** lead to undefined behavior when calling.
2. **Complex pointer declarations** can be hard to read. Parentheses help clarify.

## Best Practices
- Use typedefs for complex function pointer types to improve readability.
- Keep pointer arithmetic within array bounds to avoid undefined behavior.

## Mini Exercise
Define a function pointer type for operations that take two integers and return an int. Implement add and multiply functions and use the pointer to call them interchangeably.
