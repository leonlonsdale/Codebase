---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Space Complexity

## Description

Space complexity (auxiliary space complexity) measures how much additional memory an algorithm requires as input size grows.

### Rules of Thumb

- Primitives (boolean, number, null, undefined) → O(1)
- Strings → O(n) where n is string length
- Arrays/objects → O(n) where n is number of elements or keys

## Examples

### Constant Space – O(1)

```js
const sum = (arr) => {
    let total = 0;
    for (let i = 0; i < arr.length; i++) {
        total += arr[i];
    }
    return total;
}
```

Only fixed variables are stored.
Space Complexity: O(1)

### Linear Space – O(n)

```js
const double = (arr) => {
    let newArr = [];
    for (let i = 0; i < arr.length; i++) {
        newArr.push(2 * arr[i]);
    }
    return newArr;
}
```

Output array grows proportionally to input.  
Space Complexity: O(n)
## Resources

