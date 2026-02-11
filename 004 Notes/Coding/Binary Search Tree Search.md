---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Binary Search Tree Search

## How it works

- Searches for a value in a **Binary Search Tree (BST)**.
- Leverages BST property:
    - Left child < parent
    - Right child > parent
- Compares target to current node:
    - If equal → found
    - If target < node → search left subtree
    - If target > node → search right subtree
- Continues recursively (or iteratively) until found or node is `None`.

## Pseudocode

1. Start at the root node.
2. While current node is not `None`:
    - If `node.value == target`, return the node.
    - Else if `target < node.value`, move to `node.left`.
    - Else, move to `node.right`.
3. If node becomes `None`, return not found.

## Examples

```py
class Node:
    def __init__(self, value):
        self.value = value
        self.left = None
        self.right = None

def bst_search(node, target):
    if node is None or node.value == target:
        return node
    elif target < node.value:
        return bst_search(node.left, target)
    else:
        return bst_search(node.right, target)

```

## Complexity

### Time Complexity

- **Best case:** O(1) → target is at the root
- **Average case:** O(log n) → balanced BST
- **Worst case:** O(n) → degenerate (linked-list-like) BST

### Space Complexity

- Iterative version: O(1) → fixed extra space
- Recursive version: O(h) → call stack proportional to tree height `h`
## Resources

