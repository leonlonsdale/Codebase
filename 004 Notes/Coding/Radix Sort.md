---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Radix Sort

## How It Works

- **Radix Sort** is a non-comparative sorting algorithm.
- It sorts numbers digit by digit, starting from the **least significant digit (LSD)** or **most significant digit (MSD)**.
- Numbers are grouped into **buckets** based on the current digit being processed.
- After processing all digits, the numbers are fully sorted.
- It is most efficient when the range of digits (`k`) is not significantly larger than the number of elements (`n`).

## Pseudocode

### LSD Radix Sort Pseudocode

1. Find the maximum number in the list to determine the number of digits `d`.
2. For each digit from least significant to most significant (1 to `d`):
    - Create 10 buckets (0–9).
    - Place each number into the bucket corresponding to the current digit.
    - Flatten the buckets back into the list.
3. After processing all digits, return the sorted list.

## Examples

```py
def counting_sort_for_radix(arr, exp):
    n = len(arr)
    output = [0] * n
    count = [0] * 10

    for i in range(n):
        index = (arr[i] // exp) % 10
        count[index] += 1

    for i in range(1, 10):
        count[i] += count[i - 1]

    i = n - 1
    while i >= 0:
        index = (arr[i] // exp) % 10
        output[count[index] - 1] = arr[i]
        count[index] -= 1
        i -= 1

    for i in range(n):
        arr[i] = output[i]

def radix_sort(arr):
    max_num = max(arr)
    exp = 1
    while max_num // exp > 0:
        counting_sort_for_radix(arr, exp)
        exp *= 10
    return arr
```

## Complexity

### Time Complexity

- **Best, Average, Worst:** `O(d * (n + k))`
    - `n` = number of elements
    - `d` = number of digits in the maximum number
    - `k` = range of each digit (0–9 → k=10)
- Each pass sorts by a digit using Counting Sort, which is `O(n + k)`.

### Space Complexity

- `O(n + k)`
- Requires auxiliary space for **buckets** (or counting array) and output array.
## Resources

- [GeeksforGeeks: Radix Sort](https://www.geeksforgeeks.org/radix-sort/)  
- [Visualgo: Radix Sort Vitalisation](https://visualgo.net/en/sorting)  
- [Introduction to Algorithms, Cormen et al., Chapter 8](https://mitpress.mit.edu/9780262046305/introduction-to-algorithms/)
