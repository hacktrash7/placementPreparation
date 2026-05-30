# TCS / Infosys / Tech M Coding Round — Patterns & Sample Problems

The actual coding rounds for service MNCs are *much easier* than competitive programming. They mostly test whether you can implement a known algorithm cleanly.

## Format quick reference

| Company         | Problems   | Time         | Difficulty                       | Auto-judged? |
| --------------- | ---------- | ------------ | -------------------------------- | ------------ |
| TCS Ninja       | 1-2        | 30-45 min    | 1 easy, 1 easy-medium            | Yes          |
| TCS Digital     | 2          | 60 min       | 1 medium, 1 medium-hard          | Yes          |
| Infosys SP/SE   | 2          | 45 min       | 1 easy, 1 medium                 | Yes          |
| Infosys Power Programmer / DSE | 2-3 | 60-90 min | medium → hard (DSA heavy) | Yes |
| Tech Mahindra   | 1-2        | 30-45 min    | easy                              | Yes          |
| Wipro Elite     | 2          | 60 min       | easy + medium                     | Yes          |
| Cognizant GenC  | 2          | 30-45 min    | easy + medium                     | Yes          |
| Accenture       | 2          | 45 min       | easy + medium                     | Yes          |
| Capgemini       | 1-2        | 30-40 min    | easy                              | Yes          |

## What problems actually look like

These are the **15 question archetypes** that recur 80% of the time:

### Easy bucket (you must solve in ≤ 15 min)

1. **String reverse / palindrome / vowel-consonant count.**
2. **Sum / average / max / min over an array.**
3. **Factorial / Fibonacci / Armstrong / prime check.**
4. **Pattern printing** (right triangle, pyramid, diamond, Floyd's triangle).
5. **Frequency of a digit / character in input.**
6. **Reverse a number / sum of digits / power of two.**
7. **Find the largest / second largest in array.**
8. **Linear search / count of an element.**
9. **GCD / LCM.**
10. **Decimal ↔ binary conversion.**

### Easy-medium bucket (you should solve in ≤ 25 min)

11. **Sort an array** (any standard sort).
12. **Matrix transpose / spiral print / sum of diagonals.**
13. **String anagram check / first non-repeating char.**
14. **Remove duplicates / merge two sorted arrays.**
15. **Subarray with given sum (positive numbers).**
16. **Check Armstrong / perfect / strong number.**

### Medium bucket (TCS Digital, Infy SP+, Wipro Elite)

17. **Two-sum / pair sum count.**
18. **Maximum subarray sum (Kadane's).**
19. **Reverse words in a sentence.**
20. **Count subsequences / longest substring without repeats.**
21. **Matrix rotation / search in matrix.**
22. **Linked list reverse / detect cycle / middle node.**
23. **Stack-based: valid parentheses, next greater element.**
24. **Easy tree: traversals, height, count.**
25. **Simple DP: climbing stairs, knapsack (small N).**

## Sample problems (try in 25 min each)

### Sample 1 — TCS Ninja level

> A string `s` is given. Print the count of each vowel in the string. Output should be five integers separated by spaces in the order `a e i o u`.
>
> Input: `placement preparation`
> Output: `4 2 0 1 0`

A clean Python solution:

```python
s = input().lower()
counts = {v: 0 for v in "aeiou"}
for ch in s:
    if ch in counts: counts[ch] += 1
print(*[counts[v] for v in "aeiou"])
```

### Sample 2 — TCS Digital level

> Given an integer array of size N, find the length of the longest subarray with sum equal to K. Print 0 if none.
>
> Input: `N=6 K=5 arr=[1, 2, 3, -1, 2, 0]`
> Output: `4` (subarray [2, 3, -1, 1] sums to 5; actually [1,2,3,-1] length 4)

Python (prefix sum + dict):

```python
n, k = map(int, input().split())
arr = list(map(int, input().split()))
prefix = 0
first_seen = {0: -1}
best = 0
for i, x in enumerate(arr):
    prefix += x
    if prefix - k in first_seen:
        best = max(best, i - first_seen[prefix - k])
    if prefix not in first_seen:
        first_seen[prefix] = i
print(best)
```

### Sample 3 — Infosys SP level

> Given a binary tree (input as level-order with `-1` for null), print its zigzag level order traversal.

(See Block 7 in `topic-roadmap.md` for the algorithm — alternate stacks or reverse alternate levels.)

### Sample 4 — Tech Mahindra level

> Read an integer N. Print a pyramid pattern of `*` with N rows.

```
Input: N = 4
Output:
   *
  ***
 *****
*******
```

```python
n = int(input())
for i in range(1, n+1):
    print(" "*(n-i) + "*"*(2*i-1))
```

### Sample 5 — Wipro Elite / Cognizant GenC

> Given a string, return the first non-repeating character. If none, return `_`.
>
> Input: `aabccdde`
> Output: `b`

```python
from collections import Counter
s = input()
c = Counter(s)
for ch in s:
    if c[ch] == 1: print(ch); break
else:
    print("_")
```

## Tips for the actual test

1. **Read both problems first.** Pick the easier one. Bank guaranteed marks.
2. **Use `input()` / `print()` only.** Service MNC platforms expect stdin/stdout.
3. **Watch the input format.** Many candidates fail because they read 1 line when 2 are given, or vice versa.
4. **Handle edge cases**: empty input, N = 0, all-equal arrays, single element.
5. **Print exactly what's asked.** Trailing spaces, extra newlines, wrong case = wrong answer.
6. **Test with the given sample first.** If your output mismatches, fix before "Run Test Cases".
7. **Don't over-engineer.** No need to optimise an O(n²) when n ≤ 1000.
8. **Submit before the timer ends.** Even a partial-score submission is better than nothing.

## 14-day pre-test sprint plan

When a placement test is 2 weeks away:

| Days       | Plan                                                              |
| ---------- | ----------------------------------------------------------------- |
| 1-3        | Solve 5 *previous year* problems for that company (PrepInsta has). |
| 4-7        | Mixed bag: 2 easy + 1 medium / day, time-boxed.                   |
| 8-10       | One full mock per day at the actual time of test (e.g., 10 AM).   |
| 11-12      | Revise weak topics + 1 mock.                                      |
| 13         | Light revision. Recheck portal login, ID proof, system requirements. |
| 14 (test day) | Eat well, warm up with 5 easy questions, do the test.          |

Good luck. Coding rounds for these companies are highly **solvable** with consistent practice — far more so than aptitude.
