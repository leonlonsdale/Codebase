---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Selection Sort

## How It Works

- **Selection Sort** is a simple comparison-based sorting algorithm.
- It works by repeatedly finding the **minimum (or maximum) element** from the unsorted portion of the list and placing it at the correct position.
- The algorithm divides the list into two sub-arrays:
    - **Left sub-array:** Sorted portion (starts empty).
    - **Right sub-array:** Unsorted portion (starts as the full list).
- On each iteration:
    1. Find the smallest element in the unsorted portion.
    2. Swap it with the first element of the unsorted portion.
- Repeat until the entire list is sorted.

## Pseudocode

1. For `i` from 0 to `len(arr) - 1`:
    - Set `min_index` to `i`.
    - For `j` from `i + 1` to `len(arr) - 1`:
        - If `arr[j] < arr[min_index]`:
            - Set `min_index = j`.    
    - Swap `arr[i]` with `arr[min_index]`.
2. Return the sorted array.

## Example Code

```py
def selection_sort(arr):
    n = len(arr)
    
    for i in range(n):
        min_index = i
        
        for j in range(i + 1, n):
            if arr[j] < arr[min_index]:
                min_index = j
                
        arr[i], arr[min_index] = arr[min_index], arr[i]
        
    return arr

```

## Complexity

### Time Complexity

#### Best Case

- Occurs when the pivot consistently splits the array into two roughly equal halves.
- **Partitioning ($O(n)$):** Each level processes all elements.
- **Recursion Depth ($O(\log n)$):** Array is halved each time.
- **Overall:** $O(n \log n)$

#### Average Case

- Pivot selection is reasonably balanced.
- Work per level is $O(n)$, depth is $\log n$.
- **Overall:** $O(n \log n)$

#### Worst Case

- Occurs when the pivot is always the smallest or largest element (e.g., already sorted array with last-element pivot).
- **Partitioning ($O(n)$):** Each level still processes all elements.
- **Recursion Depth ($O(n)$):** Array is reduced by only one element per recursion.
- **Overall:** $O(n^2)$
- **Mitigation:** Use randomized pivot or median-of-three selection to avoid unbalanced partitions.

### Space Complexity

- **In-place Sorting:** No extra arrays needed; swaps are done within the original array.
- **Recursive Call Stack:**
    - Best and average case: $O(\log n)$
    - Worst case (highly unbalanced partitions): $O(n)$

**Overall:** Typically $O(\log n)$

## Resources

[Wikipedia - Selection Sort](https://en.wikipedia.org/wiki/Selection_sort)
[GeeksforGeeks - Selection Sort](https://www.geeksforgeeks.org/selection-sort/)
