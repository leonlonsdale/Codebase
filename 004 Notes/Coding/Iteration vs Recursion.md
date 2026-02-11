---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Iteration vs Recursion

## Description

Algorithms can be implemented using iteration or recursion.

### Iteration

Uses loops to repeat operations until a condition is met.

Characteristics:

- Explicit loop control
- Typically constant stack usage

### Recursion

A function calls itself to solve smaller instances of the same problem.

Characteristics:

- Base case required
- Uses call stack
- Can introduce additional space complexity

Choice of approach may affect performance and readability.

## Examples

Recursive factorial:

```py
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

## Resources

