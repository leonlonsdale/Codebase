---
type: note
tags:
  - type/note
  - dom/code
  - cat/logic
---
# Graph Search Algorithms

## How it works

- Algorithms to **traverse or search graphs** for nodes or paths.
- Two common methods:
    - **Breadth-First Search (BFS):** explores neighbors level by level.
    - **Depth-First Search (DFS):** explores as deep as possible before backtracking.
- Can be applied to **directed or undirected graphs**.
- Can find **shortest paths**, detect **cycles**, or traverse all nodes.

## Pseudocode

### BFS

1. Initialise `visited` set.
2. Initialise `queue` with the start node.
3. While `queue` is not empty:
    - Remove node from queue.
    - If node not in `visited`, add to `visited`.
    - Add all unvisited neighbors to `queue`.

### DFS

1. Initialise `visited` set.
2. Visit the start node:
    - Mark node as visited.
    - Recursively visit all unvisited neighbors.

## Examples

BFS:

```py
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    while queue:
        node = queue.popleft()
        if node not in visited:
            visited.add(node)
            queue.extend(graph[node] - visited)
    return visited
```

DSF:

```py
def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()
    visited.add(start)
    for neighbour in graph[start]:
        if neighbour not in visited:
            dfs(graph, neighbour, visited)
    return visited
```

### Time Complexity

- O(V + E), where V = vertices, E = edges

### Space Complexity

- O(V) → to store the visited set
- Additional O(V) for recursion stack in DFS (recursive version)
## Resources

