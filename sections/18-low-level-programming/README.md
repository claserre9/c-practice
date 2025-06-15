# Low-Level Programming

## Overview
Low-level programming involves direct interaction with hardware through registers, memory-mapped I/O, and sometimes inline assembly. C provides constructs to approach this level while still offering structured programming.

## Detailed Explanation
- **Registers**: Some compilers allow register-specific keywords or inline assembly to access CPU registers.
- **Memory-Mapped I/O**: Peripheral devices expose memory addresses. Writing to those addresses controls hardware. Use volatile pointers to prevent unwanted optimization.
- **Inline Assembly**: The `asm` keyword (or `__asm__`) inserts assembly instructions into C code for performance-critical sections or special hardware instructions.
- **Portability**: Low-level code is often platform-specific and may not compile on different architectures.

## Code Examples
```c
#include <stdint.h>

#define LED_REG (*(volatile uint32_t*)0x40021018)

int main(void) {
    LED_REG = 0x1;   // turn on LED mapped to this address
    asm volatile("nop");  // inline assembly: no operation
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Incorrect addresses** in memory-mapped I/O can crash the system or corrupt hardware state.
2. **Overly aggressive compiler optimizations** may remove necessary reads/writes; use `volatile` to prevent this.

## Best Practices
- Document platform-specific assumptions clearly.
- Limit inline assembly to small, critical sections to maintain readability and portability.

## Mini Exercise
Research your target platform's memory map and write a short snippet that toggles a GPIO register (pseudo-code is acceptable if hardware isn't accessible).
