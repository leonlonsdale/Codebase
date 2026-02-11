---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# What Is an Algorithm

## Description

An algorithm is a finite, well-defined sequence of instructions used to solve a problem or perform a computation.

An algorithm:

- Accepts input
- Produces output
- Follows clearly defined steps
- Terminates after a finite number of operations
- Is **unambiguous**: there is a "correct" and "incorrect" interpretation of the steps
- Is **implementable**: can be executed using software or hardware

Algorithms describe _logic_, not implementation details. The same algorithm can be implemented in multiple programming languages.

This note also introduces **efficiency and computational cost** concepts (time, memory, storage), which are essential before studying specific algorithms like sorting or searching.

## Examples

### Summing numbers from 1 to n

Step-based description:

1. Start with `total = 0`
2. For each number from 1 to n
3. Add the number to `total`
4. Return `total`

### Mathematical operations relevant to algorithms

- **Average**: sum of numbers ÷ count
- **Median**: middle number in sorted list
- **Exponents**: repeated multiplication, e.g., `10^3 = 10 * 10 * 10`
- **Logarithms**: inverse of exponents, e.g., `log2(8) = 3`
- **Factorials**: product of all integers from n down to 1, e.g., `5! = 120`

### Scaling & Efficiency

|Function|Big-O Notation|Efficiency Ranking|
|---|---|---|
|Logarithmic (`log2(x)`)|`O(log n)`|1st (Fastest)|
|Linear Doubling (`x * 2`)|`O(n)`|2nd|
|Exponential (`x ** 2`)|`O(n²)`|3rd|
|Factorial (`n!`)|`O(n!)`|4th (Slowest)|

## Resources

- [Wikipedia: Algorithm](https://en.wikipedia.org/wiki/Algorithm)
- [Big O Cheat Sheet](https://www.bigocheatsheet.com/)
- [Khan Academy: Algorithms](https://www.khanacademy.org/computing/computer-science/algorithms)
- [GeeksforGeeks: Introduction to Algorithms](https://www.geeksforgeeks.org/fundamentals-of-algorithms/)
- [MIT OpenCourseWare: Introduction to Algorithms](https://ocw.mit.edu/courses/6-006-introduction-to-algorithms-fall-2011/)
