# Big-O Complexity & DSA Mindset

Before any data structure, you need to know **how to evaluate code quality**. That's what Big-O measures.

## What Big-O really is

Big-O describes how the **runtime grows** as input size `n` grows. We ignore constants, lower-order terms, and machine details.

```
O(1)       constant      Fastest. Looking up dict[key], arr[i].
O(log n)   logarithmic   Binary search. Halving each step.
O(n)       linear        Single loop over n items.
O(n log n) linearithmic  Efficient sorts (merge, quick avg).
O(n²)      quadratic     Two nested loops over n.
O(n³)      cubic         Three nested loops (Floyd-Warshall).
O(2^n)     exponential   Brute-force subsets. Tower of Hanoi.
O(n!)      factorial     Permutations.
```

## How to estimate complexity

1. **Each loop multiplies.** A loop over n inside a loop over n → O(n²).
2. **Halving each step → log n.** `i = i*2` or `i = i/2`. So binary search is O(log n).
3. **Function calls count.** Recursive Fibonacci without memoisation is O(2^n).
4. **Look at the largest term.** `O(n² + 100n + 5)` → O(n²).
5. **Space complexity** counts extra memory used (excluding input). An array of size n → O(n) space. Recursion uses O(depth) stack space.

## Cheatsheet: which complexity fits what input?

Service MNC coding problems usually give you `n ≤ 10^4` or `10^5`.

| Max n            | Allowed complexity |
| ---------------- | ------------------ |
| 10^8             | O(n)               |
| 10^7 - 10^8      | O(n log n)         |
| 10^4 - 10^5      | O(n²)              |
| 500 - 1000       | O(n³)              |
| ≤ 20             | O(2^n)             |
| ≤ 10             | O(n!)              |

If your solution is *one bracket worse* than allowed, you'll get TLE (Time Limit Exceeded). That's the hint that your algorithm is wrong, not your code.

## Mindset of a problem solver

### 1. Read the problem twice.

Most students fail by missing a tiny constraint ("the array is sorted", "ignore case", "1-indexed"). Slow down on the first read.

### 2. Work an example by hand.

If input = `[3, 1, 4, 1, 5]`, what's the expected output? Trace yours physically. If the expected output is unclear, your understanding is wrong.

### 3. Brute force first. Then optimise.

```
Brute force:    works, slow.  O(n²) or worse.
Better:         apply a pattern (two pointers, hashing).
Optimal:        what an interviewer hopes to see.
```

**Always state the brute force out loud first.** It buys time and shows reasoning.

### 4. Choose your data structure.

Half of DSA is "what structure makes this query fast?":

| Need                                | Data structure       | Time         |
| ----------------------------------- | -------------------- | ------------ |
| Random access by index              | Array / List         | O(1)         |
| Insertion at front/middle           | Linked list / Deque  | O(1) at end  |
| Last-in-first-out                   | Stack                | O(1)         |
| First-in-first-out                  | Queue                | O(1)         |
| Look up by key                      | Hash map / Set       | O(1) avg     |
| Keep elements sorted, frequent inserts | BST / SortedSet   | O(log n)     |
| Find min/max fast, repeatedly       | Heap (priority queue)| O(log n) push/pop, O(1) peek |
| Range queries                       | Segment tree / Fenwick (advanced) | O(log n) |

### 5. Patterns beat memorisation.

There are ~15 common patterns ([`patterns-cheatsheet.md`](patterns-cheatsheet.md)). Recognising "this is a two-pointer problem" is 80% of the work.

### 6. Write code, then test it on paper.

Before clicking "Submit", walk through one example by hand. Caught bugs save 5 minutes of resubmits.

### 7. Handle edge cases.

Standard edge cases to ask yourself:
- Empty input.
- Single-element input.
- All elements equal.
- Negative numbers / zero / very large numbers.
- Sorted vs unsorted vs reverse-sorted.
- Duplicates allowed?

### 8. Tracking progress

Keep a single spreadsheet:

```
| # | Date | Topic | Problem | Difficulty | Time taken | Solved unaided? | Notes |
```

Every Sunday, look at the unsolved ones and re-attempt 3.
