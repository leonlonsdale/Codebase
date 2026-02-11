---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Binary Search

## How it works

- Efficient search algorithm for **sorted arrays**.
- Repeatedly divides the search interval in half.
- Compares the target to the middle element:
    - If equal → found
    - If target < middle → search left half
    - If target > middle → search right half
- Stops when the target is found or the interval is empty.

## Pseudocode

1. Set `low = 0` and `high = len(arr) - 1`.
2. While `low <= high`:
    - Compute `mid = (low + high) // 2`.
    - If `arr[mid] == target`, return `mid`.
    - Else if `arr[mid] < target`, set `low = mid + 1`.
    - Else, set `high = mid - 1`.
3. If not found, return -1.

## Examples

```py
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
```

## Complexity

### Time Complexity

- **Best case:** O(1) → target is at the middle
- **Worst case:** O(log n) → repeatedly halves the interval until empty
- **Average case:** O(log n)

### Space Complexity

- O(1) → iterative version uses fixed extra space
- Recursive version would use O(log n) for call stack
## Resources

