---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Big O Simplification Rules

## Description

Big O expressions are simplified to reflect dominant growth behaviour.

### Rules

1. Ignore constants
    - O(2n) → O(n)
    - O(13n²) → O(n²)
    - O(500) → O(1)
2. Drop non-dominant terms
    - O(n + 10) → O(n)
    - O(n² + n) → O(n²)
    - O(n² + 5n + 8) → O(n²)
3. Nested loops multiply
    - O(n) inside O(n) → O(n²)
4. Consecutive operations add
    - O(n) + O(n²) → O(n²)

## Examples



## Resources

