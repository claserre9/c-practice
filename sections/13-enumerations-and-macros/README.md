# Enumerations and Macros

## Overview
Enumerations (`enum`) provide named integral constants, improving code readability. Macros, defined with `#define`, allow simple text substitution before compilation. Together they help manage constants and small code fragments.

## Detailed Explanation
- **Enumerations**: Define an enum type listing possible values. The compiler assigns integers starting from 0 unless specified.
- **Macros**: Use `#define` for constants or small reusable code snippets. Macros are expanded by the preprocessor and have no type checking.
- **const vs. Macros**: `const` variables obey scope and type rules, while macros are substituted literally and can cause unexpected results if not carefully parenthesized.
- **Preprocessor Tricks**: Macros can use parameters (`#define SQR(x) ((x) * (x))`) or stringification with `#`.

## Code Examples
```c
#include <stdio.h>

enum Color { RED, GREEN, BLUE };
#define MAX(a,b) ((a) > (b) ? (a) : (b))

int main(void) {
    enum Color c = GREEN;
    printf("color=%d\n", c);
    printf("max=%d\n", MAX(3,5));
    return 0;
}
```

## Common Pitfalls & Warnings
1. **Macro side effects**: If parameters have expressions with side effects, they may evaluate twice.
2. **Enum size assumptions**: The underlying type of `enum` may vary, affecting storage size.

## Best Practices
- Parenthesize macro parameters and results to avoid precedence issues.
- Prefer `const` variables over macros when type safety matters.

## Mini Exercise
Create an enum representing the days of the week and a macro that checks if a day is a weekend. Test it in a small `main` function.
