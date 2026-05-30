# Python Track — From Beginner to Comfortable (6 Weeks)

Goal: by the end of Week 6 you can solve **TCS NQT-level coding problems** in Python without help.

## Week 1 — Setup and the absolute basics

Topics:
- Installing Python + VS Code.
- Running a `.py` file vs the interactive REPL.
- `print()`, `input()`, comments.
- Variables, types: `int`, `float`, `str`, `bool`.
- Arithmetic operators (`+ - * / // % **`).
- Comparison + logical operators.
- `if / elif / else`.
- `while` and `for` loops, `range()`, `break`, `continue`.

Practice (Week 1 — 25 problems):
- Print "Hello, World!" + your name.
- Read two numbers, print sum/diff/prod/div.
- Print all even numbers between 1 and 100.
- Check if a number is positive/negative/zero.
- Check if a number is odd or even.
- Sum of first N natural numbers.
- Factorial of N using a loop.
- Multiplication table of N.
- Reverse digits of an integer (e.g., 1234 → 4321).
- Check if a number is a palindrome.
- Count digits of a number.
- Check if a number is prime.
- Print first N Fibonacci numbers.
- Sum of digits of a number.
- GCD of two numbers (Euclid's algorithm).
- LCM of two numbers.
- Power without `**`: a^b using a loop.
- Armstrong number check.
- Print a right-angled triangle pattern of `*`.
- Print Pascal's triangle (10 rows).
- Print a diamond of stars.
- Find largest of 3 numbers without using `max()`.
- Convert Celsius ↔ Fahrenheit.
- Convert decimal to binary (using a loop).
- Convert binary to decimal.

Where to solve: **HackerRank → Python (Basic)** track. Free, structured, auto-judged.

## Week 2 — Strings, lists, tuples

Topics:
- Strings: indexing, slicing `s[a:b:c]`, common methods (`.upper`, `.lower`, `.split`, `.strip`, `.replace`, `.find`, `.count`, `.startswith`, `.endswith`).
- Immutability of strings.
- f-strings: `f"Hello {name}, age {age+1}"`.
- Lists: creation, indexing, slicing, `.append`, `.pop`, `.insert`, `.remove`, `.sort`, `.reverse`, `len`, `in`.
- Iterating with `for`, `enumerate`, `zip`.
- List comprehensions: `[x*x for x in range(10) if x%2==0]`.
- Tuples: immutable, packing/unpacking.

Practice (Week 2 — 25 problems):
- Reverse a string (loop + slicing both ways).
- Count vowels & consonants.
- Check palindrome string.
- Find frequency of each character (use dict).
- Find the longest word in a sentence.
- Count words in a sentence.
- Capitalise first letter of each word.
- Remove all spaces from a string.
- Check if two strings are anagrams.
- Convert "snake_case" to "camelCase".
- Find the largest, smallest in a list.
- Sum / average of a list.
- Find second largest in a list (without sorting).
- Remove duplicates while preserving order.
- Rotate a list by k positions (right rotation).
- Merge two sorted lists into a sorted list.
- Find common elements between two lists.
- Find missing number in 1..N where one is missing.
- Move all zeros to the end of a list.
- Find pair in list with given sum.
- Matrix: read NxM, print row & column sums.
- Transpose an MxN matrix.
- Print matrix in spiral order.
- Search element in a 2D matrix.
- Count occurrence of a substring in a string.

## Week 3 — Dicts, sets, functions

Topics:
- Dictionaries: `d[key]`, `.keys`, `.values`, `.items`, `.get`, default values, iteration.
- Sets: `{}` vs `dict`, union/intersect/difference, fast lookup.
- Functions: `def`, parameters, default args, `*args`, `**kwargs`, return values.
- Variable scope: local vs global.
- Recursion basics: factorial, Fibonacci recursive, recursion stack visualisation.

Practice (Week 3 — 25 problems):
- Word frequency counter (dict).
- Character frequency in a string.
- Find duplicates in a list (using set).
- First non-repeating character in a string.
- Two sum (return indices) using dict.
- Group anagrams from a list of words.
- Sort dict by value.
- Merge two dicts.
- Count vowels recursively.
- Factorial recursively.
- Fibonacci recursively (with memoisation as a dict).
- Power(a, b) recursively.
- Sum of digits recursively.
- Reverse a string recursively.
- Check palindrome recursively.
- GCD recursively.
- Tower of Hanoi (print moves).
- Generate all permutations of a string (recursion).
- Generate all subsets of a list.
- Convert decimal to binary recursively.
- Binary search recursively.
- Find max of a list recursively.
- Count number of paths in an MxN grid (recursion).
- Print n-th term of "Look-and-say" sequence.
- Implement a simple calculator using functions for + - * /.

## Week 4 — File I/O, error handling, modules

Topics:
- Reading and writing text files: `open`, `with`, `.read()`, `.readlines()`, `.write()`.
- CSV files using the `csv` module.
- Exception handling: `try/except/else/finally`, common exceptions.
- Importing modules: `math`, `random`, `datetime`, `os`, `sys`.
- Writing your own module (`mymath.py` and `import mymath`).
- The `if __name__ == "__main__":` idiom.

Mini projects (pick at least 2):
- **Marks management CLI**: store students + marks in a CSV, compute averages, list toppers.
- **Word frequency tool**: read a text file, output top-N words.
- **Number guessing game** with `random` + score tracking saved to a file.
- **Simple expense tracker** (CSV-backed).
- **Library book CLI** (add, remove, search by title).

## Week 5 — Object-oriented programming in Python

Topics:
- `class`, `__init__`, attributes vs methods, `self`.
- Encapsulation (`_protected`, `__private` naming convention).
- Inheritance: single, multi-level, multiple.
- Polymorphism: method overriding, `super()`.
- Abstraction: `ABC` from `abc` module.
- Special methods: `__str__`, `__repr__`, `__len__`, `__eq__`.

Practice:
- Build a `Student` class with name, roll, marks, grade method.
- Build a `BankAccount` class with deposit, withdraw, balance check.
- Build a `Shape` base class and `Circle`, `Rectangle`, `Triangle` subclasses with `area()` method (polymorphism).
- Build a small **Library** system: `Book`, `Member`, `Library` classes.

Why this matters: **OOPs is a major HR/technical interview topic**. Concepts learned here are reused in `04-cs-core/oop.md`.

## Week 6 — Standard library, putting it together, mini-project

Topics:
- `collections`: `Counter`, `defaultdict`, `deque`.
- `itertools`: `combinations`, `permutations`, `product`.
- `functools`: `lru_cache`, `reduce`.
- List/dict/set comprehensions deeper.
- Lambda functions, `map`, `filter`, `sorted` with `key=`.

Mini-project (pick one, push to GitHub, README it):
- **Console To-Do app** with JSON persistence.
- **Quiz CLI**: load Qs from a CSV, score the user.
- **Personal Finance tracker**: log income/expenses, monthly summary.
- **URL shortener** (using a Python dict + Flask) — slightly stretch goal but great resume add.

## Python-specific things you must internalise

```python
# Read N integers on one line
n, *arr = map(int, input().split())   # idiomatic

# Read N integers across N lines
arr = [int(input()) for _ in range(n)]

# Sort with custom key
people.sort(key=lambda p: (p.age, p.name))

# Frequency in one line
from collections import Counter
freq = Counter(s)

# Default value for dict
freq = {}
freq[ch] = freq.get(ch, 0) + 1

# Avoid this trap with default mutable args:
def bad(x, items=[]):   # BAD — list is shared across calls
    items.append(x)
    return items

def good(x, items=None):
    if items is None:
        items = []
    items.append(x)
    return items
```

## Common beginner mistakes to fix early

- **Re-reading input inside a loop** when you should read once into a list.
- **Integer division `/` vs `//`** — `/` always gives float in Python 3.
- **`==` vs `is`** — `is` checks identity, not equality. Use `==`.
- **Modifying a list while iterating it.** Iterate over a copy: `for x in lst[:]:`.
- **Off-by-one in `range(a, b)`** — remember it's `[a, b)`.
- **Forgetting `int()` after `input()`** — `input()` always returns a string.

## How to know you're done with the Python track

Take this self-test (50 min, alone, no internet):

1. Read N integers, print the second largest. (5 min)
2. Read a string, count frequency of each char, print sorted by freq desc. (10 min)
3. Read a list of (name, marks) tuples, print top 3 by marks. (10 min)
4. Implement a `Stack` class with push/pop/peek/empty. (10 min)
5. Given an integer, print its prime factorisation. (15 min)

If you complete 4 out of 5 cleanly → move to `03-dsa/`. Otherwise spend one more week on Week-4 + Week-5 topics.
