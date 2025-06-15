# Bitwise Operations

## Overview
Bitwise operators manipulate individual bits within integers. They are critical for low-level programming such as device drivers, compression, and cryptography.

## Detailed Explanation
- **AND (`&`)** and **OR (`|`)** combine bits; XOR (`^`) toggles bits, while NOT (`~`) inverts them.
- **Shifts**: `<<` shifts bits left (multiplying by powers of two), and `>>` shifts bits right (dividing or sign-extending depending on type).
- **Bit Masks**: Use masks to isolate or modify specific bits, often with enums or constant definitions.
- **Bitfields**: Struct members that occupy specific bits, useful for compact storage.

## Code Examples
```c
#include <stdio.h>

int main(void) {
    unsigned char flags = 0;
    const unsigned char FLAG_A = 1 << 0;  // 00000001
    const unsigned char FLAG_B = 1 << 1;  // 00000010

    flags |= FLAG_A; // set bit 0
    flags |= FLAG_B; // set bit 1
    printf("flags=%02X\n", flags);

    flags &= ~FLAG_A; // clear bit 0
    printf("flags=%02X\n", flags);
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Shifting by a value >= bit width** is undefined behavior.
2. **Using signed integers for bitwise operations** may yield unexpected sign extension.

## Best Practices
- Prefer unsigned types for predictable bitwise behavior.
- Use hexadecimal or binary literals to clarify bit patterns.

## Mini Exercise
Implement a function that returns `1` if a given integer has exactly one bit set (a power of two) and `0` otherwise.
