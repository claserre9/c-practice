# Arrays and Strings

## Overview
Arrays store sequences of elements with the same type. Strings in C are arrays of characters terminated by a null byte (`\0`). Knowing how to manipulate arrays and strings is essential for data processing.

## Detailed Explanation
- **Fixed-size Arrays**: Declared with a length, e.g., `int nums[5];`. The size is determined at compile time.
- **Initialization**: Provide values inside braces, `{1,2,3}`. Uninitialized elements default to zero at global scope.
- **String Literals**: Double-quoted sequences automatically include the null terminator.
- **Character Pointers**: `char *msg = "hello";` points to a string literal in read-only memory.

## Code Examples
```c
#include <stdio.h>
#include <string.h>

int main(void) {
    int numbers[3] = {1, 2, 3};
    printf("first=%d\n", numbers[0]);

    char word[] = "cat";          // array with 4 bytes: 'c','a','t','\0'
    printf("word=%s length=%zu\n", word, strlen(word));

    char copy[10];
    strcpy(copy, word);           // copy contents into another array
    printf("copy=%s\n", copy);
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Out-of-bounds access** leads to undefined behavior and possible crashes.
2. **Missing null terminator** when manipulating strings manually results in unpredictable outputs.

## Best Practices
- Keep track of array sizes; use constants or `sizeof` to avoid overflow.
- Use library functions like `strncpy` for safer string handling.

## Mini Exercise
Create a program that reads a word into a char array and prints it reversed. Ensure you don't read past the array's end.
