---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
  - lang/js
  - lang/ts
---
# JavaScript Built-ins - Complexity

## Description

Time complexity characteristics of common JavaScript built-in structures and methods.

## Examples

### Objects

- Insert → O(1)
- Remove → O(1)
- Search → O(n)
- Access → O(1)
- Object.keys → O(n)
- Object.values → O(n)
- Object.entries → O(n)
- hasOwnProperty → O(1)

### Arrays

- Insert at end (push) → O(1)
- Remove from end (pop) → O(1)
- Insert/remove at start (shift/unshift) → O(n)
- Search → O(n)
- Access by index → O(1)
- concat → O(n)
- slice → O(n)
- splice → O(n)
- sort → O(n log n)
- forEach / map / filter / reduce → O(n)

## Resources

