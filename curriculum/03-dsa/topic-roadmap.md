# DSA Topic Roadmap (12 Blocks)

Tackle these in order. Don't jump ahead — each block depends on the previous one.

> Time-estimates are *learning effort*, not calendar days. Beginners typically need ~1 week per block, ~6-7 hours per week.

## Block 1 — Arrays & Strings (foundational)

**Sub-topics**
- 1D array traversal, prefix sums.
- 2D array (matrix) traversal, transpose, rotation.
- Sliding window (fixed size and variable size).
- Two-pointer technique.
- String manipulation, frequency counts, anagrams.

**Must-solve patterns**
- Maximum sub-array sum (Kadane's).
- Two sum / Pair sum.
- Move zeros to the end.
- Find duplicate / missing number.
- Longest substring without repeating characters.
- Anagram grouping.
- Reverse / rotate array in O(1) extra space.

## Block 2 — Recursion & Backtracking

**Sub-topics**
- The recursive mental model (base case + smaller subproblem).
- Recursion tree.
- Backtracking (try, recurse, undo).
- Tail recursion vs general recursion.

**Must-solve patterns**
- Print all subsequences / power set.
- Permutations of a string / array.
- N-queens (classic, smaller boards).
- Sudoku solver (small grids; optional).
- Rat in a maze (paths in a grid).
- Combination sum.

## Block 3 — Searching & Sorting

**Sub-topics**
- Linear search.
- Binary search (and *binary search on answer*).
- Bubble, Insertion, Selection (understand, don't use in real code).
- Merge sort (master this — recursion + arrays).
- Quick sort (partitioning idea).
- Counting / Radix sort (when applicable).

**Must-solve patterns**
- First/last occurrence of a target.
- Search in rotated sorted array.
- Square root using binary search.
- Median of two sorted arrays (medium).
- Custom sort by frequency.

## Block 4 — Hashing (Hash Maps & Sets)

**Sub-topics**
- Hash table internals — collisions, load factor (concept only).
- Using dict / HashMap / unordered_map effectively.
- Frequency maps, set operations.

**Must-solve patterns**
- Subarray sum equals k (prefix sum + hash).
- Group anagrams.
- Longest consecutive sequence.
- Count distinct elements in window.
- 4-sum / 3-sum (with hashing or two-pointer).

## Block 5 — Linked Lists

**Sub-topics**
- Singly linked list — insertion, deletion, traversal.
- Doubly linked list.
- Dummy head / tail patterns.
- Slow & fast pointer (Floyd's algorithm).

**Must-solve patterns**
- Reverse a linked list (iterative + recursive).
- Detect cycle in a linked list (and find start of cycle).
- Find middle of a linked list.
- Merge two sorted linked lists.
- Remove n-th node from end.
- Check palindrome linked list.

## Block 6 — Stacks & Queues

**Sub-topics**
- Stack via array / linked list / built-in.
- Queue via array / linked list / `collections.deque`.
- Monotonic stack / queue.
- Implement a stack using two queues (interview classic).

**Must-solve patterns**
- Valid parentheses.
- Next greater element / previous smaller element.
- Stock span problem.
- Min stack (push/pop/min all O(1)).
- Sliding window maximum (deque).
- Evaluate postfix / infix to postfix.

## Block 7 — Trees (Binary Trees & BST)

**Sub-topics**
- Tree representation.
- Traversals: inorder, preorder, postorder (recursive + iterative), level order (BFS).
- BST property and operations: insert, delete, search.
- Height, diameter, lowest common ancestor (LCA).
- Balanced vs unbalanced; idea of AVL/Red-Black (concept only).

**Must-solve patterns**
- Inorder/preorder/postorder traversals.
- Level-order traversal & zigzag.
- Height, diameter, balanced check.
- LCA in binary tree and BST.
- Validate BST.
- Convert sorted array to balanced BST.
- Kth smallest in BST.

## Block 8 — Heaps & Priority Queue

**Sub-topics**
- Heap as a binary tree using an array.
- Min-heap vs max-heap.
- `heapq` in Python, `PriorityQueue` in Java.
- Heapify and build-heap.

**Must-solve patterns**
- Kth largest element in array.
- Top K frequent elements.
- Merge K sorted lists.
- Median in a stream.
- Connect ropes / minimum cost.

## Block 9 — Graphs

**Sub-topics**
- Graph representation: adjacency list vs matrix.
- BFS, DFS (recursive + iterative).
- Connected components.
- Cycle detection (directed + undirected).
- Topological sort (Kahn / DFS).
- Shortest path: BFS (unweighted), Dijkstra (weighted, positive).
- MST: Prim or Kruskal (one suffices).

**Must-solve patterns**
- Number of islands (grid DFS/BFS).
- Clone graph.
- Course schedule (topological sort).
- Shortest path in a binary matrix.
- Word ladder (BFS on strings).

> Graph problems are common in **Infosys SP / DSE** and TCS Digital, less in TCS Ninja.

## Block 10 — Dynamic Programming (DP)

**Sub-topics**
- Memoisation (top-down) vs tabulation (bottom-up).
- Identifying overlapping subproblems and optimal substructure.
- 1-D DP, 2-D DP.
- Common patterns: knapsack, LCS family, grid DP, partition DP.

**Must-solve patterns**
- Fibonacci with memoisation.
- Climbing stairs / decode ways.
- 0/1 knapsack.
- Unbounded knapsack / coin change.
- Longest common subsequence (LCS).
- Longest increasing subsequence (LIS).
- Edit distance (medium-hard).
- Min path sum in grid.

> For TCS Ninja / Infy SP, only **basic DP** (climb stairs, coin change, knapsack) is asked. For Digital / Power Programmer / DSE, deeper DP is needed.

## Block 11 — Greedy Algorithms

**Sub-topics**
- Greedy choice property + exchange argument intuition.
- Sorting-based greedy.
- Interval problems.

**Must-solve patterns**
- Activity selection / meeting rooms.
- Fractional knapsack.
- Job sequencing with deadlines.
- Minimum platforms.
- Jump game I & II.
- Huffman coding (idea level).

## Block 12 — Bit Manipulation (light)

**Sub-topics**
- Bitwise AND, OR, XOR, NOT, shifts.
- Set, clear, toggle, check the k-th bit.
- Count set bits (Brian Kernighan).
- XOR tricks.

**Must-solve patterns**
- Single number (XOR).
- Number of 1 bits.
- Power of two check.
- Subsets using bitmask.
- Missing number using XOR.

---

## Recommended sequence with weeks

| Weeks  | Topic blocks                                  |
| ------ | --------------------------------------------- |
| 1-4    | Block 1 (Arrays/Strings) + intro to recursion |
| 5-6    | Blocks 2, 3 (Recursion, Searching/Sorting)    |
| 7-8    | Block 4 (Hashing)                             |
| 9-10   | Blocks 5, 6 (Linked List, Stack/Queue)        |
| 11-13  | Block 7 (Trees)                               |
| 14     | Block 8 (Heaps)                               |
| 15-16  | Block 9 (Graphs)                              |
| 17-18  | Blocks 10, 11 (DP basics, Greedy)             |
| 19     | Block 12 (Bit manipulation) + revisit weak    |
| 20-24  | Mixed company-tagged sets + mocks             |

If you fall behind, drop **Block 11/12 advanced parts** before dropping Trees or Graphs. Trees + Hashing + Two-pointer + Recursion form 60-70% of interview questions for these companies.
