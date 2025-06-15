# Structs and Unions

## Overview
Structs group related variables into a single compound type, enabling the creation of more complex data structures. Unions store different data types in the same memory location, sharing space among their members.

## Detailed Explanation
- **Struct Declaration**: Use the `struct` keyword followed by member declarations. Optionally use `typedef` to simplify usage.
- **Initialization**: Provide values in braces following the same order as member definitions.
- **Access**: Use the dot operator `.` for struct variables and `->` for pointers to structs.
- **Unions**: Members overlap in memory. Only one member can hold a valid value at a time, useful for interpreting the same bytes in multiple ways.

## Code Examples
```c
#include <stdio.h>

typedef struct {
    int id;
    char name[20];
} Person;

int main(void) {
    Person p = {1, "Alice"};
    printf("%d %s\n", p.id, p.name);
    return 0;
}
```

**Union example**:
```c
union Value {
    int i;
    float f;
};

int main(void) {
    union Value v;
    v.i = 42;
    printf("i=%d\n", v.i);
    v.f = 3.14f;              // same memory as v.i
    printf("f=%f\n", v.f);
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Misinterpreting union data**: Reading a member that wasn't the last written causes nonsense values.
2. **Padding and alignment**: Structs may contain padding bytes, affecting size and binary layouts.

## Best Practices
- Use `typedef` to create clear type names for structs.
- Initialize all members to avoid garbage data, especially in unions.

## Mini Exercise
Define a `struct Point` with `x` and `y` coordinates. Write a function that prints a `Point` given a pointer to it.
