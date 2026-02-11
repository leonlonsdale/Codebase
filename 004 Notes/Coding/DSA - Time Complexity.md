---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Time Complexity

## Description

Time complexity measures how an algorithm’s execution time scales as input size increases.

### Common Big O Notations

|Big O|Name|Growth Behaviour|Example|
|---|---|---|---|
|O(1)|Constant|Does not change with input size|Array indexing|
|O(log n)|Logarithmic|Grows slowly|Binary search|
|O(n)|Linear|Grows proportionally|Single loop|
|O(n log n)|Linearithmic|Between linear and quadratic|Merge sort|
|O(n²)|Quadratic|Nested iteration|Double loop|
|O(2ⁿ)|Exponential|Very rapid growth|Recursive Fibonacci|
|O(n!)|Factorial|Extremely rapid growth|Permutations|

### How to Read Big O

- O(1): Input size does not affect runtime.
- O(n): Doubling input doubles runtime.
- O(n²): Doubling input quadruples runtime.
- O(2ⁿ): Small increases in input cause dramatic growth.
- O(n!): Impractical even for small inputs.

### Types of Operations Considered

When analysing complexity, we consider:

- Assignments → O(1)
- Comparisons → O(1) per comparison
- Arithmetic operations → O(1)
- Increments/decrements → O(1)
- Function calls → Depends on implementation
- Loop iterations → O(n) per loop over input
- Array indexing → O(1)
- Memory allocations → O(n) if proportional to input size

## Examples

### Linear Example – O(n)

```py
def add_up_to(n):
	total = 0
	for i in range(1, n + 1):         
		total += i     
	return total
```

Operations grow proportionally with n.  
Time Complexity: O(n)

### Constant Example – O(1)

```py
def add_up_to(n):
	return (n * (n + 1)) // 2
```

Fixed number of operations regardless of n.  
Time Complexity: O(1)

### Quadratic Example – O(n²)

```py
def print_all_pairs(n):
	for i in range(n):
		for j in range(n):
			print(i, j)
```

Nested loops multiply growth.  
Time Complexity: O(n²)

## Resources

