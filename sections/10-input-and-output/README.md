# Input and Output

## Overview
The C standard library provides `stdio.h` for reading from and writing to streams, including files and the console. Functions like `scanf` and `printf` process formatted input and output.

## Detailed Explanation
- **printf**: Formats data using conversion specifiers (`%d`, `%s`, `%f`) and prints to `stdout`.
- **scanf**: Reads formatted input from `stdin`. Pass addresses of variables so that values can be stored.
- **File Handling**: `fopen` opens a file and returns a `FILE*`. Use `fread`, `fwrite`, and `fclose` for file operations.
- **Buffering**: Standard streams are usually buffered, meaning output may not appear immediately until flushed.

## Code Examples
```c
#include <stdio.h>

int main(void) {
    int age;
    printf("Enter your age: ");
    scanf("%d", &age);      // note the & for address
    printf("You are %d years old\n", age);

    FILE *f = fopen("data.txt", "w");
    if (f) {
        fprintf(f, "Age=%d\n", age);
        fclose(f);
    }
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Forgetting to check `fopen` return value** may lead to crashes when using a null pointer.
2. **Mismatched format specifiers** in `scanf` or `printf` cause undefined behavior.

## Best Practices
- Validate all I/O operations (check return values).
- Use `fgets` for string input to prevent buffer overflow.

## Mini Exercise
Write a program that asks the user for a filename, opens it, and counts the number of lines using `fgets`.
