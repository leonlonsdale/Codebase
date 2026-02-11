---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Hash Table Search

## How it works

- Searches for a value using a **key** in a hash table (dictionary).
- Computes the hash of the key to find the correct bucket.
- Direct access is possible if no collisions occur.
- Handles collisions by chaining or open addressing.
    

## Pseudocode

1. Compute `hash = hash_function(key)`.
2. Check bucket at `hash`:
    - If key exists, return the associated value.
    - Else, handle collision (check linked entries or probe next index).
3. If key is not found, return `None`.

## Examples

```py
hash_table = { "a": 1, "b": 2, "c": 3 }

def search(key):
    return hash_table.get(key, None)
```

## Complexity

### Time Complexity

- **Best case:** O(1) → direct access, no collisions
- **Average case:** O(1) → assuming good hash function and low load factor
- **Worst case:** O(n) → all keys in one bucket (hash collisions)

### Space Complexity

- O(n) → proportional to number of entries in the hash table
## Resources

