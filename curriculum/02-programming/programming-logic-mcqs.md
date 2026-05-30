# Programming Logic & Pseudocode MCQs

TCS NQT and Infosys both have a section of MCQs **before** the coding round. They test whether you can read code and predict behaviour. This section is **easier** than aptitude if you've practised. Don't skip it.

## What gets asked

1. **Output prediction** — given a C/Java/Python snippet, choose the printed output.
2. **Loop counting** — how many times a loop runs.
3. **Pseudocode evaluation** — Infosys uses a language-neutral pseudocode.
4. **Bug-spotting** — pick the line that has the bug.
5. **Complexity** — "What is the time complexity of this code?"
6. **OOP / DBMS / OS theory MCQs** — small dose of CS theory.

## How to attack these

- **Trace on paper.** Even if it seems easy, write variable values after each line. Mental tracing is the #1 source of mistakes.
- **Watch for `++` placement, integer division, scope, and short-circuiting.**
- **Read the question, not the code first.** Sometimes only one variable's final value is asked — no need to trace the entire snippet.
- **Eliminate impossible options.** If a printf has `%d` and the variable is float, expect garbage — that often eliminates 2 of 4.

## 20 representative MCQs (try before reading answers)

> Answers are in the back. **Don't peek.** Solve on paper.

**1.**
```c
int i = 0;
while (i++ < 5) printf("%d ", i);
```
What is printed?
A. 0 1 2 3 4    B. 1 2 3 4 5    C. 0 1 2 3 4 5    D. 1 2 3 4

**2.**
```c
int a = 10;
printf("%d %d %d\n", a, ++a, a++);
```
(undefined behaviour, but TCS-style answer per left-to-right evaluation) most likely prints:
A. 10 11 11    B. 12 12 10    C. 11 12 10    D. 10 11 12

**3.**
```python
for i in range(1, 10, 2):
    print(i, end=' ')
```
Output?

**4.**
```c
int a[] = {1,2,3,4,5};
printf("%d", *(a + 2));
```
Output?

**5.**
```c
int x = 5;
if (x = 0) printf("zero");
else       printf("nonzero");
```
Output?

**6.**
```python
s = "placement"
print(s[2:7:2])
```
Output?

**7.** What is the time complexity of this snippet?
```c
for (int i = 1; i < n; i *= 2)
    printf("hi");
```
A. O(n)    B. O(n log n)    C. O(log n)    D. O(√n)

**8.** What does this print?
```python
a = [1, 2, 3]
b = a
b.append(4)
print(a)
```

**9.**
```java
String a = "abc";
String b = "abc";
String c = new String("abc");
System.out.println((a == b) + " " + (a == c) + " " + a.equals(c));
```

**10.** Pseudocode (Infosys-style):
```
function f(n):
    if n <= 1: return n
    return f(n-1) + f(n-2)
print f(5)
```
Output?

**11.**
```c
int n = 4, sum = 0;
for (int i = 1; i <= n; i++)
   for (int j = 1; j <= i; j++)
      sum++;
printf("%d", sum);
```
Output?

**12.**
```python
d = {"a": 1, "b": 2}
d["a"] = d.get("a", 0) + 10
print(d)
```
Output?

**13.** What's wrong with this C code?
```c
int *p;
*p = 10;
printf("%d", *p);
```

**14.** What does it print?
```python
lst = [3, 1, 4, 1, 5, 9, 2, 6]
print(sorted(set(lst))[2])
```

**15.**
```c
char s[] = "hello";
printf("%lu", sizeof(s));
```

**16.**
```python
def f(x, lst=[]):
    lst.append(x)
    return lst

print(f(1)); print(f(2)); print(f(3))
```

**17.** Time complexity of binary search on sorted array of size n?

**18.**
```c
int x = 7;
int y = x++ + ++x;
printf("%d %d", x, y);
```

**19.**
```python
def mystery(n):
    res = 0
    while n > 0:
        res = res * 10 + n % 10
        n //= 10
    return res
print(mystery(1234))
```

**20.** Which data structure best suits implementing a *function call stack*?
A. Queue   B. Stack   C. Hash table   D. Linked List

---

### Answers

1. B (post-increment uses 0 first, then increments → loop body sees 1..5).
2. B-style varies by compiler; TCS often marks **12 12 10** (left-to-right with both ++ applied before the printf finishes pushing args). Note: standard says undefined — don't write such code in real life.
3. `1 3 5 7 9`.
4. `3`.
5. `nonzero` (assignment `x = 0` makes condition false → goes to else? Wait — `x=0` evaluates to 0 → falsey → else runs → prints `nonzero`). **Important trap.**
6. `aee` (indices 2, 4, 6 → 'a','e','e').
7. C — log n iterations.
8. `[1, 2, 3, 4]` — `b = a` is a reference copy.
9. `true false true` — string pool gives `a==b`, `new String` is a different object so `a==c` is false, `.equals` compares content.
10. `5` (Fibonacci of 5).
11. `10` (1+2+3+4).
12. `{'a': 11, 'b': 2}`.
13. `p` is uninitialised — dereferencing is undefined behaviour (likely crash).
14. `4` (sorted unique → [1,2,3,4,5,6,9], index 2 → 3). Wait — sorted set gives `[1, 2, 3, 4, 5, 6, 9]`, index 2 is `3`. **Answer: 3.**
15. `6` (5 chars + null terminator).
16. `[1]` then `[1, 2]` then `[1, 2, 3]` — *the default list is shared across calls.* Classic Python gotcha.
17. `O(log n)`.
18. `x = 9, y = 16` (typical gcc behaviour; standard: undefined).
19. `4321`.
20. B — Stack.

## Practice drill plan

- **Week 7:** 30 C/pseudocode MCQs/day for 5 days = 150 MCQs.
- **Week 8 onward:** 20 MCQs/day until placement.
- Maintain an **MCQ error log** — same format as aptitude.

You're now done with the programming fundamentals module. Move to `03-dsa/`.
