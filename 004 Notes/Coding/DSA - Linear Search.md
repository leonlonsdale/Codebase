---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Linear Search

## How it works

- A simple search algorithm that checks each element sequentially.
- Stops when the target is found or the list ends.
- Works on unsorted or sorted collections.

## Pseudocode

1. For each element in the list:
    - Compare the element with the target.
    - If it matches, return the index.
2. If the end is reached without finding the target, return -1.

## Examples

```py
def linear_search(arr, target):
    for i, val in enumerate(arr):
        if val == target:
            return i
    return -1
```

## Complexity

### Time Complexity

- **Best case:** O(1) → target is the first element
- **Worst case:** O(n) → target is at the end or absent
- **Average case:** O(n/2) → simplified as O(n)

### Space Complexity

- O(1) → uses only a fixed amount of extra space (loop counters).
## Resources

