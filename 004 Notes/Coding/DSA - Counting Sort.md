---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Counting Sort

## How It Works

Counting Sort is a **non-comparison-based sorting algorithm** that works well for **integers** or objects that can be mapped to integers within a **known, limited range**.

1. Determine the **maximum value** (`max_val`) in the input array.
2. Create a **count array** of size `max_val + 1`, initialised to zeros.
3. Count the occurrences of each element in the input array and store it in the count array.
4. Transform the count array into a **prefix sum array** to determine the positions of elements in the output array.
5. Iterate through the input array **in reverse order** to place each element in the output array according to the prefix sum.
6. Copy the sorted output array back to the original array (if required).

## Pseudocode

### counting_sort(arr)

1. Find `max_val` in `arr`.
2. Create `count = [0] * (max_val + 1)`.
3. For each element `num` in `arr`, increment `count[num]` by 1.
4. For `i` from 1 to `max_val`, set `count[i] = count[i] + count[i - 1]` (prefix sum).
5. Create an `output` array of the same length as `arr`.
6. For each element `num` in `arr` (traverse in reverse):
    - Set `output[count[num] - 1] = num`.    
    - Decrement `count[num]` by 1.
7. Copy `output` back to `arr`.
8. Return `arr`.

## Examples

```py
def counting_sort(arr):
    if not arr:
        return arr

    max_val = max(arr)
    count = [0] * (max_val + 1)
    output = [0] * len(arr)

    # Count occurrences
    for num in arr:
        count[num] += 1

    # Prefix sum
    for i in range(1, len(count)):
        count[i] += count[i - 1]

    # Build output array (stable sort)
    for num in reversed(arr):
        output[count[num] - 1] = num
        count[num] -= 1

    # Copy to original array
    for i in range(len(arr)):
        arr[i] = output[i]

    return arr
```

## Complexity

### Time Complexity

- **Finding max value:** $O(n)$
- **Counting occurrences:** $O(n)$
- **Prefix sum:** $O(k)$ where $k = max_val$
- **Placing elements into output:** $O(n)$
- **Overall:** $O(n + k)$

### Space Complexity

- **Count array:** size $k+1$
- **Output array:** size $n$
- **Overall:** $O(n + k)$


> [!Note] Counting Sort is most efficient when `k` (range of input) is not significantly larger than `n`.

## Resources

## Resources

- [GeeksforGeeks: Counting Sort](https://www.geeksforgeeks.org/counting-sort/)  
- [Visualgo: Counting Sort Virtualisation](https://visualgo.net/en/sorting)  
- [Introduction to Algorithms, Cormen et al., Chapter 8](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)

