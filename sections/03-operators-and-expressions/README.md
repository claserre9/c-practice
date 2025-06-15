# Operators and Expressions

## Overview
Operators in C perform computations on values and variables. Expressions combine operators with operands to produce new results. Understanding precedence and associativity ensures expressions evaluate as expected.

## Detailed Explanation
- **Arithmetic Operators**: `+`, `-`, `*`, `/`, `%` for numeric calculations.
- **Logical Operators**: `&&`, `||`, and `!` evaluate to 0 or 1, enabling complex conditional logic.
- **Bitwise Operators**: `&`, `|`, `^`, `~`, `<<`, and `>>` operate on bits within integers.
- **Precedence and Associativity**: Determine the order in which operators are applied. For example, `*` has higher precedence than `+`.
- **Parentheses**: Use parentheses to clarify evaluation order and improve readability.

## Code Examples
```c
#include <stdio.h>

int main(void) {
    int a = 5, b = 2;
    int sum = a + b;        // 7
    int product = a * b;    // 10
    int bit = a & b;        // bitwise AND -> 0

    printf("Sum: %d\n", sum);
    printf("Product: %d\n", product);
    printf("Bitwise AND: %d\n", bit);

    int result = a + b * 3;     // b*3 computed first
    int result2 = (a + b) * 3;  // parentheses change the order
    printf("result=%d, result2=%d\n", result, result2);
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Division by zero** leads to undefined behavior.
2. **Mixing signed and unsigned** may cause unexpected results in comparisons or arithmetic.

## Best Practices
- Use parentheses to make complex expressions explicit.
- Enable compiler warnings to catch suspicious operations.

## Mini Exercise
Write a program that takes two integers and outputs their average using arithmetic operators. Ensure the result is correct when both numbers are odd.
