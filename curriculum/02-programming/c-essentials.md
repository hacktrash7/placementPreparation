# C Essentials — Just Enough for TCS / Infosys MCQs

You do **not** need to be a C expert. But the **Programming Logic** sections of TCS NQT and similar tests *love* asking output-prediction questions in C-like pseudocode. One focused week is enough.

## Why C still matters for these tests

- Output prediction in TCS NQT is almost always C-flavoured.
- C makes you understand **pointers, memory, and execution order** — useful for technical interviews.
- Infosys "pseudocode" MCQs follow C-like syntax.

## Week-7 mini-syllabus (5 days, ~2 hours/day)

### Day 1 — Syntax + I/O + control flow
- `#include <stdio.h>`, `int main(void)`, `return 0;`.
- `printf` format specifiers: `%d %f %lf %c %s %x %o %u %ld`.
- `scanf` with `&` for addresses.
- `if/else`, `switch/case`, `for/while/do-while`.

### Day 2 — Functions, arrays, strings
- Function declaration vs definition; parameters passed **by value**.
- 1D and 2D arrays, array decay to pointer.
- C strings as null-terminated `char[]`; `strlen`, `strcpy`, `strcmp`, `strcat`.

### Day 3 — Pointers (the most-tested topic)
- `int *p = &x;` ; `*p` to dereference.
- Pointer arithmetic: `p+1` advances by `sizeof(*p)` bytes.
- Array name vs pointer: `arr[i] == *(arr+i)`.
- `&arr[0] == arr`, but `&arr` has type "pointer to array".
- Common output traps: post/pre-increment with `*p`.

### Day 4 — Structures, storage classes, operators
- `struct` declaration + dot vs arrow access (`s.x` vs `p->x`).
- `typedef` for cleaner names.
- Storage classes: `auto`, `register`, `static`, `extern`.
- Bitwise operators: `& | ^ ~ << >>`. Common interview Q: swap two ints without temp using XOR.
- Operator precedence pitfalls: `*p++` vs `(*p)++`.

### Day 5 — Output prediction drills
- 50 MCQs from PrepInsta / IndiaBix C output section.
- 20 pseudocode MCQs Infosys-style.

## The "must-not-miss" C output traps

```c
// 1. Post-increment evaluates AFTER the expression uses the value.
int a = 5;
printf("%d %d\n", a++, ++a);   // undefined behaviour in standard C; tests treat L→R: prints 5 7 commonly

// 2. printf and integer promotion
char c = 'A';        // ASCII 65
printf("%d\n", c);   // 65, not 'A'

// 3. Integer division truncates toward zero
printf("%d\n", 7/2); // 3, not 3.5

// 4. Sizeof tricks
int arr[10];
printf("%lu\n", sizeof(arr));   // 40 (10 * 4 bytes), NOT 10

// 5. String vs char
char a = 'a';        // single char, 1 byte
char *s = "a";       // string, 2 bytes (incl. null terminator)

// 6. Format specifier mismatch
float f = 1.5;
printf("%d\n", f);   // garbage; %d with float = undefined

// 7. Pointer + array
int a[5] = {1,2,3,4,5};
int *p = a;
printf("%d\n", *(p+2));   // 3
printf("%d\n", *p++);     // prints 1, then p points to 2

// 8. Logical short-circuit
int x = 0, y = 0;
if (x++ && ++y) {}        // y stays 0 because x++ is 0 → short-circuit
printf("%d %d\n", x, y);  // 1 0
```

## Operator precedence (top → bottom)

```
() [] -> .                   highest
! ~ ++ -- + - * & sizeof     unary
* / %
+ -
<< >>
< <= > >=
== !=
&
^
|
&&
||
?:                           ternary
= += -= ...                  assignment
,                            lowest
```

In doubt: **add parentheses**. No tests deduct for over-parenthesising.

## Resources

- *Let Us C* by Yashavant Kanetkar — classic Indian beginner book.
- TutorialsPoint C, GeeksforGeeks C tutorial — for quick reference.
- PrepInsta TCS C MCQ section — for drills.

## Done with C when you can…

- Read any 20-line C snippet and predict the output correctly 8/10 times.
- Explain in plain words what `int *p = arr + i;` means.
- Spot the difference between `*p++`, `(*p)++`, and `*++p`.
