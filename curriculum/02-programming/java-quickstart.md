# Java Quickstart for the Python User

Once Python is comfortable, you can learn enough Java for placements in **3-5 days**. Most service MNCs train you in Java, and a lot of interview questions reference Java OOP.

## What you need to know (and not more)

1. Setup: install **JDK 17+** and **IntelliJ IDEA Community Edition** (free) or VS Code with the Java extension pack.
2. The `Hello World` template:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

3. **Types are explicit:** `int`, `long`, `double`, `boolean`, `char`, `String`. Java is statically typed.
4. **Input** via `Scanner`:

```java
import java.util.Scanner;
Scanner sc = new Scanner(System.in);
int n = sc.nextInt();
String s = sc.next();
```

5. **Arrays:** `int[] a = new int[10];` ; length via `a.length` (no parentheses).
6. **ArrayList, HashMap, HashSet**:

```java
import java.util.*;
ArrayList<Integer> list = new ArrayList<>();
list.add(5); list.get(0); list.size();

HashMap<String, Integer> map = new HashMap<>();
map.put("apple", 3); map.get("apple");

HashSet<Integer> set = new HashSet<>();
set.add(1); set.contains(1);
```

7. **Loops** identical to C: `for (int i=0;i<n;i++)`. Enhanced for: `for (int x : arr)`.
8. **String** is **immutable**; for mutable use `StringBuilder` (`.append`, `.reverse`, `.toString`).
9. **OOP** is real here — single inheritance via `extends`, multiple interfaces via `implements`.

```java
class Animal { void speak() { System.out.println("..."); } }
class Dog extends Animal {
    @Override
    void speak() { System.out.println("Woof"); }
}

interface Drawable { void draw(); }
class Circle implements Drawable {
    public void draw() { System.out.println("●"); }
}
```

10. **Access modifiers:** `public`, `private`, `protected`, *(default)*.
11. **Exception handling:** `try { ... } catch (Exception e) { ... } finally { ... }`. Checked vs unchecked exceptions are a common interview question.

## Equivalents you'll reach for daily

| Python                       | Java                                                            |
| ---------------------------- | --------------------------------------------------------------- |
| `len(s)`                     | `s.length()` (string) / `arr.length` (array)                    |
| `s[::-1]`                    | `new StringBuilder(s).reverse().toString()`                     |
| `s.upper()`                  | `s.toUpperCase()`                                               |
| `s.split(",")`               | `s.split(",")` (returns String[])                               |
| `[0]*n`                      | `int[] a = new int[n];` (defaults to 0)                         |
| `sorted(list)`               | `Collections.sort(list)`                                        |
| `list.append(x)`             | `list.add(x)`                                                   |
| `dict[k] = v`                | `map.put(k, v)`                                                 |
| `for k,v in d.items()`       | `for (Map.Entry<K,V> e : map.entrySet()) { e.getKey(); ... }`  |
| `f"hi {name}"`               | `String.format("hi %s", name)` or `"hi " + name`                |
| Integer parsing              | `Integer.parseInt(s)`                                           |

## Tiny Java programs to write (one per day)

1. Read N integers, print sum.
2. Reverse a String using StringBuilder.
3. Frequency count using HashMap.
4. Sort an ArrayList of Integers descending.
5. Implement a `Stack` using an ArrayList (push/pop/peek).
6. Read marks, classify grades into Pass/Fail with `if/else`.
7. Define `Student` class with constructor + `toString`; create 3 objects.
8. Inheritance: `Animal → Dog/Cat`, override `sound()`.
9. Use `Scanner` to read mixed input (string + int) safely (`sc.next()` vs `sc.nextLine()` gotcha).
10. Exception demo: catch `NumberFormatException` from `Integer.parseInt("abc")`.

## Common Java pitfalls coming from Python

- `==` on strings compares **references**, not contents. Use `s1.equals(s2)`.
- `Scanner.nextInt()` leaves a newline in buffer — call `sc.nextLine()` after if you need a string next.
- Integer overflow at `2_147_483_647` for `int`. For big numbers use `long` or `BigInteger`.
- Generics are erased at runtime; you can't do `new T[]` directly.
- Default `HashMap` has unspecified iteration order (use `LinkedHashMap` for insertion order).

## Resources

- *Head First Java* (book) — great if you have time.
- "Java for Beginners" YouTube playlist by **Bro Code** — fast and free.
- LeetCode "Top Interview 150" filtered to Java — for practice.
