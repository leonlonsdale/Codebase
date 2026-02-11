---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Heap Sort

## How It Works

Heap Sort is a **comparison-based sorting algorithm** that uses a **binary heap** data structure to sort elements.

1. The array is first transformed into a **max heap** (for ascending order), where the largest element is at the root.
2. The root element (largest) is swapped with the last element in the heap.
3. The heap size is reduced by one, excluding the sorted element.
4. The heap property is restored by **heapifying** the root.
5. Steps 2–4 are repeated until the heap size is 1, at which point the array is sorted.

## Pseudocode

### build_max_heap(arr)

1. Start from the last non-leaf node and move upwards.
2. For each node, call `heapify()` to ensure the sub-tree satisfies the max heap property.    

### heapify(arr, n, i)

1. Set `largest` = `i`.
2. Let `left` = 2 * `i` + 1, `right` = 2 * `i` + 2.
3. If `left < n` and `arr[left] > arr[largest]`, set `largest = left`.
4. If `right < n` and `arr[right] > arr[largest]`, set `largest = right`.
5. If `largest != i`:
    - Swap `arr[i]` with `arr[largest]`.    
    - Recursively call `heapify(arr, n, largest)`.    

### heap_sort(arr)

1. Build a max heap from the array.
2. For `i` from `len(arr) - 1` down to 1:
    - Swap `arr[0]` (largest) with `arr[i]`.    
    - Heapify the root with reduced heap size (`i`).    
3. Return the sorted array.

## Examples

```py
def heapify(arr, n, i):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    if left < n and arr[left] > arr[largest]:
        largest = left

    if right < n and arr[right] > arr[largest]:
        largest = right

    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heap_sort(arr):
    n = len(arr)

    # Build max heap
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # Extract elements one by one
    for i in range(n - 1, 0, -1):
        arr[0], arr[i] = arr[i], arr[0]  # swap
        heapify(arr, i, 0)

    return arr
```

## Complexity

### Time Complexity

#### Best, Average, and Worst Case

- **Heap Construction:** $O(n)$
- **Heapify per extraction:** $O(\log n)$, repeated $n$ times
- **Overall:** $O(n \log n)$

### Space Complexity

- Heap Sort is **in-place**, only a few variables are used for swapping and indices.

**Overall:** $O(1)$
## Resources

[GeeksforGeeks - Heap Sort](https://www.geeksforgeeks.org/heap-sort/)
[Visualgo - Heap Sort Visualisation](https://visualgo.net/en/sorting)
[Introduction to Algorithms, Cormen et al., Chapter 6](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)