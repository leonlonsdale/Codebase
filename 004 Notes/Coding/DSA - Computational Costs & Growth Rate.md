---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Computational Costs & Growth Rate

## Description

Computational costs describe how the resources required by an algorithm—time (CPU), memory (RAM), or storage (disk)—increase as the size of the input grows.

Growth rates are commonly expressed using Big-O notation to classify efficiency:

- **Logarithmic** (O(log n)): grows slowly with input
- **Linear** (O(n)): grows proportionally with input
- **Quadratic** / Exponential (O(n²)): grows rapidly, may be impractical for large inputs
- **Factorial** (O(n!)): grows extremely quickly, only feasible for very small inputs

Understanding these rates helps predict performance and choose suitable algorithms.

This note illustrates the impact of growth rates through examples and tables:

- **Compute / Scaling Table:** shows how different growth types scale with input size and why higher-order growth quickly becomes impractical
- **Efficiency Ranking Table:** ranks algorithms by Big-O notation, highlighting which are fast and scalable versus slow and costly
- **Average & Median:** basic mathematical operations that help understand algorithmic computations
- **Exponents:** demonstrates how repeated operations increase computational cost (e.g., O(n²) behaviour)
- **Logarithms:** common in divide-and-conquer algorithms, showing why O(log n) operations scale efficiently
- **Factorials:** illustrates extreme growth, explaining why O(n!) algorithms are generally infeasible

## Examples

### Compute / Scaling Table

|Input Size (n)|Linear (x * 2)|Exponential (x²)|Logarithmic (log2(x))|Factorial (n!)|
|---|---|---|---|---|
|10|20|100|3.32|3,628,800|
|100|200|10,000|6.64|Too large|
|1,000|2,000|1,000,000|9.97|Too large|
|10,000|20,000|100,000,000|13.29|Too large|
|100,000|200,000|10,000,000,000|16.61|Too large|

### Efficiency Ranking

|Function|Big-O Notation|Rank|
|---|---|---|
|Logarithmic (log2(x))|O(log n)|1|
|Linear Doubling (x * 2)|O(n)|2|
|Exponential (x²)|O(n²)|3|
|Factorial (n!)|O(n!)|4|

### Average

```py
numbers = [10, 15, 20, 25]
average = sum(numbers) / len(numbers)
```

### Median

```py
numbers_even = [10, 15, 20, 25]
numbers_odd = [10, 15, 20, 25, 30]

# Even
numbers_even.sort()
median_even = (numbers_even[len(numbers_even)//2 - 1] + numbers_even[len(numbers_even)//2]) / 2
print(median_even)  # 17.5

# Odd
numbers_odd.sort()
median_odd = numbers_odd[len(numbers_odd)//2]
```

### Exponents

```py
# 10^3 = 10 * 10 * 10
result = 10**3 # 1000
```

### Logarithms

```py
import math

base = 10
argument = 1000
result = math.log(argument) / math.log(base) # 3.0
```

### Factorials

```py
# Recursive factorial
def factorial_recursive(n):
    if n == 0 or n == 1:
        return 1
    return n * factorial_recursive(n - 1)

# Iterative factorial
def factorial_iterative(n):
    result = 1
    for i in range(2, n + 1):
        result *= i
    return result

print(factorial_recursive(5))  # 120
print(factorial_iterative(5))  # 120
```

## Resources

- [Big O Notation Explained – GeeksforGeeks](https://www.geeksforgeeks.org/analysis-of-algorithms-set-1-asymptotic-analysis/)  
- [Big O Cheat Sheet](https://www.bigocheatsheet.com/)  
- [Khan Academy: Algorithms and Complexity](https://www.khanacademy.org/computing/computer-science/algorithms)  
- [MIT OpenCourseWare: Introduction to Algorithms](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-fall-2011/)  
- [Wikipedia: Time Complexity](https://en.wikipedia.org/wiki/Time_complexity)  
- [Wikipedia: Space Complexity](https://en.wikipedia.org/wiki/Space_complexity)  
