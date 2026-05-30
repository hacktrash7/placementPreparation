# DSA Problem-Solving Patterns (the ~15 you must recognise)

If you can recognise *which pattern* a problem belongs to, you've already done 80% of the work. Drill these consciously.

## 1. Two Pointers

Use when: array/string is sorted, or you can sort it, and you need to find pairs / count / shrink a window.

```python
i, j = 0, len(arr) - 1
while i < j:
    s = arr[i] + arr[j]
    if s == target: return (i, j)
    elif s < target: i += 1
    else:            j -= 1
```

Classic problems: pair sum in sorted array, 3-sum, container with most water, remove duplicates from sorted array, valid palindrome.

## 2. Sliding Window

Use when: contiguous subarray / substring of length k (fixed) or satisfying a property (variable).

```python
# Variable window: longest substring with all unique chars
left = 0
seen = {}
best = 0
for right, ch in enumerate(s):
    if ch in seen and seen[ch] >= left:
        left = seen[ch] + 1
    seen[ch] = right
    best = max(best, right - left + 1)
```

Classic problems: longest substring without repeating, max sum subarray of size k, smallest window with all chars, longest substring with k distinct.

## 3. Prefix Sum / Difference Array

Use when: many range-sum queries, or "subarray with sum equals X" type.

```python
prefix = [0]
for x in arr: prefix.append(prefix[-1] + x)
# sum of arr[l..r] = prefix[r+1] - prefix[l]
```

With a hashmap of prefix counts you get **subarray sum equals K in O(n)**.

## 4. Fast & Slow Pointer (Floyd's Tortoise & Hare)

Use when: linked-list cycle, finding middle node, "happy number", duplicate in array of n+1 numbers.

```python
slow = fast = head
while fast and fast.next:
    slow = slow.next
    fast = fast.next.next
    if slow is fast: return True
return False
```

## 5. Binary Search (incl. on Answer)

Use when: input sorted *or* the answer space is monotonic ("can we do it with K?" yes/no).

```python
lo, hi = 0, n - 1
while lo <= hi:
    mid = (lo + hi) // 2
    if arr[mid] == target: return mid
    elif arr[mid] < target: lo = mid + 1
    else: hi = mid - 1
return -1
```

Binary search on answer examples: minimum capacity to ship in D days, allocate books (GFG classic).

## 6. Hash Map for O(1) lookups

Patterns: two-sum, longest consecutive sequence, anagram grouping, subarray sum = k, isomorphic strings.

```python
seen = {}
for i, x in enumerate(arr):
    if target - x in seen: return (seen[target - x], i)
    seen[x] = i
```

## 7. Stack-based Problems

Patterns: valid parentheses, next greater element, daily temperatures, largest rectangle in histogram, evaluate postfix.

```python
stack = []
for ch in s:
    if ch in "([{":
        stack.append(ch)
    else:
        if not stack or matches(stack.pop()) != ch: return False
return not stack
```

## 8. Monotonic Stack / Deque

Use when: next greater/smaller, sliding window maximum.

```python
from collections import deque
dq = deque()
res = []
for i, x in enumerate(arr):
    while dq and arr[dq[-1]] < x: dq.pop()
    dq.append(i)
    if dq[0] <= i - k: dq.popleft()
    if i >= k - 1: res.append(arr[dq[0]])
```

## 9. Recursion + Backtracking

Use when: generate all subsets / permutations / combinations, N-queens, sudoku, word search.

```python
def backtrack(path, choices):
    if condition: result.append(path[:]); return
    for c in choices:
        path.append(c)
        backtrack(path, next_choices)
        path.pop()
```

## 10. Tree Traversal Recipes

```python
def inorder(node):
    if not node: return
    inorder(node.left)
    visit(node)
    inorder(node.right)
```

Iterative level-order with `deque`. Most BST problems reduce to "inorder gives sorted".

## 11. BFS / DFS on Graphs (and grids)

Patterns: number of islands, flood fill, shortest path in unweighted graph, course schedule (topological sort).

```python
from collections import deque
visited = set()
q = deque([start])
visited.add(start)
while q:
    node = q.popleft()
    for nb in graph[node]:
        if nb not in visited:
            visited.add(nb)
            q.append(nb)
```

## 12. Topological Sort

Use when: tasks with prerequisites; detect cycle in directed graph.

```python
# Kahn's algorithm
in_deg = [0]*n
for u in graph:
    for v in graph[u]: in_deg[v] += 1
q = deque(i for i in range(n) if in_deg[i] == 0)
order = []
while q:
    u = q.popleft(); order.append(u)
    for v in graph[u]:
        in_deg[v] -= 1
        if in_deg[v] == 0: q.append(v)
```

## 13. Dijkstra's Shortest Path (heap-based)

```python
import heapq
dist = [inf]*n; dist[src] = 0
pq = [(0, src)]
while pq:
    d, u = heapq.heappop(pq)
    if d > dist[u]: continue
    for v, w in graph[u]:
        if dist[u] + w < dist[v]:
            dist[v] = dist[u] + w
            heapq.heappush(pq, (dist[v], v))
```

## 14. Dynamic Programming Skeleton

```python
# 1. Define state: dp[i] = ...
# 2. Transition: dp[i] = f(dp[i-1], dp[i-2], ...)
# 3. Base case
# 4. Order: bottom-up or top-down

# Example: climbing stairs
dp = [0]*(n+1)
dp[0] = 1; dp[1] = 1
for i in range(2, n+1):
    dp[i] = dp[i-1] + dp[i-2]
```

Key DP families:
- **Linear DP** (climbing stairs, house robber).
- **Grid DP** (min path sum, unique paths).
- **Subsequence / String DP** (LCS, edit distance).
- **Knapsack family** (0/1, unbounded, subset sum).
- **Interval DP** (matrix chain, palindrome partitioning) — *advanced*.

## 15. Greedy Recipes

Always sort by something clever, then iterate:
- Sort intervals by end time → activity selection.
- Sort by weight/value ratio → fractional knapsack.
- Sort by deadlines → job sequencing.

```python
intervals.sort(key=lambda x: x[1])   # by end time
count = 0; last_end = -inf
for s, e in intervals:
    if s >= last_end:
        count += 1; last_end = e
```

## How to use this file

When you see a new problem, **pause for 60 seconds** and ask:
- Is the array sorted? → two pointers / binary search.
- Subarray / substring with property? → sliding window / prefix sum.
- Need pair / fast lookup? → hashing.
- Path / connectivity / grid? → BFS/DFS/graph.
- "Choose / not choose" with overlapping subproblems? → DP.

This pre-thinking is 100× more valuable than starting to code immediately.
