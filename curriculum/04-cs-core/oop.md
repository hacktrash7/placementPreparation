# OOP — Object-Oriented Programming Concepts

OOP is **the #1 topic in interviews after DSA**. Even non-CS interviewers love it because the questions are short and pattern-matched.

> You'll already have written OOP code in Python (Week 5 of `02-programming/`). This file gives you the **interview vocabulary** to talk about it.

## Concept tree

1. **What OOP is and why**: bundling data + behaviour into objects → modularity, reuse, maintainability.
2. **Four pillars**: Encapsulation, Abstraction, Inheritance, Polymorphism.
3. **Class vs object**.
4. **Constructor and destructor**.
5. **Encapsulation** — access modifiers (`public`, `private`, `protected`), getters/setters.
6. **Inheritance** — single, multilevel, multiple, hierarchical, hybrid; diamond problem.
7. **Polymorphism** — compile-time (overloading) vs runtime (overriding).
8. **Abstraction** — abstract classes and interfaces.
9. **`static` keyword**, **`final`**, **`this`**, **`super`**.
10. **Exception handling**: try/catch/finally, checked vs unchecked.
11. **Object class methods** — `equals`, `hashCode`, `toString` contract (Java) and Python equivalents.

## The four pillars (interview-grade definitions)

### 1. Encapsulation

Wrapping data and the methods that operate on it inside a single class, and restricting direct access to fields via access modifiers. Example: a `BankAccount` class with a private `balance` and public `deposit/withdraw` methods.

**Why**: protects invariants, hides implementation details.

### 2. Abstraction

Exposing only the *essential* behaviour and hiding the implementation. Achieved via abstract classes and interfaces.

**Example**: a `Vehicle` abstract class declares `start()`; `Car` and `Bike` implement it differently.

**Encapsulation vs abstraction (the classic interview question):**
- Encapsulation = *data hiding*; how (via private fields + public methods).
- Abstraction = *implementation hiding*; what is exposed (the interface) vs what is hidden (the body).

### 3. Inheritance

A class derives properties/behaviour from another class (`extends` / `:` syntax). Promotes reuse and an *is-a* relationship.

**Types**:
- Single (B → A)
- Multilevel (C → B → A)
- Hierarchical (B → A and C → A)
- Multiple (D inherits from B and C — supported in Python and C++, not in Java for classes; achieved via interfaces in Java)
- Hybrid — combination

**Diamond problem**: in multiple inheritance, if two parents share a common grandparent, which version is inherited? Python solves with **MRO (C3 linearisation)**; Java avoids by disallowing multiple class inheritance; C++ allows via *virtual inheritance*.

### 4. Polymorphism

"Many forms" — same interface, different behaviour.

- **Compile-time** (a.k.a. static / overloading): same method name, different parameter list. Python doesn't truly overload — only the last definition wins (use default args or `*args`).
- **Runtime** (a.k.a. dynamic / overriding): subclass redefines parent's method. Called the *actual* object's method at runtime.

```python
class Animal:
    def sound(self): return "..."

class Dog(Animal):
    def sound(self): return "Woof"

class Cat(Animal):
    def sound(self): return "Meow"

for a in [Dog(), Cat(), Animal()]:
    print(a.sound())     # Woof / Meow / ...
```

## Top 25 interview questions

**1. Difference between class and object?**
A class is a *blueprint*. An object is a *runtime instance* with its own state. `Dog` is a class, `my_dog = Dog("Bruno")` is an object.

**2. What is a constructor? Types?**
A special method called when an object is created.
- Default constructor (no args).
- Parameterised constructor.
- Copy constructor (C++/Java patterns; Python: implement `copy.copy`).

**3. What is `this` keyword (or `self` in Python)?**
A reference to the current object. Used to disambiguate fields from parameters, or pass the object to other methods.

**4. Difference between method overloading and overriding?**
Overloading = same name, different parameters, in *same class* (compile-time).
Overriding = subclass replaces inherited method (runtime), same signature.

**5. What is an abstract class?**
A class that cannot be instantiated and may contain abstract methods (no body). Other classes inherit and implement.

**6. Abstract class vs interface (Java perspective)?**
- Abstract class: can have fields, partial method implementations, constructors. Single inheritance.
- Interface: only method signatures (and constants in older Java; default methods since Java 8). A class can implement many interfaces.

**7. What is the diamond problem?**
Ambiguity when a class inherits from two classes that share a common ancestor. Python resolves with MRO (`ClassA.__mro__`); C++ via virtual inheritance; Java by disallowing multiple inheritance of classes.

**8. Static vs instance method?**
Static methods belong to the class, not to an instance — they don't access instance state (no `self/this`). Called via class name.

**9. Difference between `==` and `equals()` (Java) — or `is` and `==` (Python)?**
- Java `==` checks references; `equals` checks content (must be overridden for value classes).
- Python `is` checks identity; `==` calls `__eq__` (value equality).

**10. Why must `hashCode` be consistent with `equals` (Java)?**
If two objects are equal, they must have the same hashCode — required for hash-based collections (HashMap, HashSet) to work correctly. Same idea in Python: override `__hash__` whenever `__eq__` is overridden.

**11. What is encapsulation? Give a real-world analogy.**
Bundling state and behaviour and exposing only via a controlled API. Analogy: a TV remote — you press a button; you don't open the remote to short-circuit wires.

**12. What is access modifier? List.**
Controls visibility:
- `public` — everywhere.
- `protected` — same package + subclasses (Java).
- *(default in Java)* — same package.
- `private` — same class only.
In Python, `_name` is a convention for protected, `__name` triggers name mangling.

**13. What is the `final` keyword (Java)?**
- `final` variable: assigned once.
- `final` method: cannot be overridden.
- `final` class: cannot be inherited.

**14. What is the difference between association, aggregation, composition?**
- **Association**: a general relationship (e.g., teacher–student).
- **Aggregation**: weak "has-a"; lifetimes independent (e.g., team has players).
- **Composition**: strong "has-a"; child cannot exist without parent (e.g., house has rooms).

**15. Method overloading in Python?**
Not directly supported (later definitions overwrite earlier). Achieved via default arguments, `*args`/`**kwargs`, or `functools.singledispatch`.

**16. What is dynamic binding (late binding)?**
Choosing the method to invoke based on the *actual object type* at runtime — the core mechanism of runtime polymorphism.

**17. Difference between abstract class and concrete class?**
Abstract has at least one unimplemented (abstract) method and cannot be instantiated. Concrete is fully implemented and can be instantiated.

**18. What is constructor chaining?**
Calling one constructor from another (within the same class — `this(...)`; or to parent — `super(...)`). Avoids duplicate init code.

**19. What is the role of `super`?**
Calls the parent class's method or constructor — used during override to extend rather than replace behaviour.

**20. What is the difference between deep copy and shallow copy?**
Shallow copy copies the top-level object; nested objects are *shared*. Deep copy recursively copies everything. Python: `copy.copy` vs `copy.deepcopy`.

**21. What is an immutable class? How to make one in Java?**
A class whose state cannot change after creation (`String`, `Integer`). To make one: declare class `final`, all fields `private final`, no setters, defensively copy mutable inputs.

**22. SOLID principles?**
- **S**ingle Responsibility — one class, one reason to change.
- **O**pen/Closed — open for extension, closed for modification.
- **L**iskov Substitution — subclass can replace parent without breaking the program.
- **I**nterface Segregation — many small interfaces > one fat interface.
- **D**ependency Inversion — depend on abstractions, not concretions.
(Brief one-liners are enough for service interviews.)

**23. Difference between Inheritance and Composition?**
Inheritance is "is-a" — extends class behaviour. Composition is "has-a" — embeds other objects. Modern guidance: **favour composition over inheritance** to reduce coupling.

**24. What is method hiding (Java)?**
Static methods cannot be overridden — they are *hidden* if the subclass defines a static with the same signature. Resolution is based on the *reference type*, not the object type.

**25. Garbage collection?**
Automatic memory reclamation for objects with no references. Java/Python both have GC. Common algorithms: reference counting (Python's primary mechanism, plus a cycle collector) and mark-and-sweep / generational (JVM).

## A small diagram to be able to draw

```
            +----------------+
            |   <<abstract>>  |
            |     Shape       |
            |  + area(): float|
            +-----------------+
                 ▲      ▲
                 │      │
   +-------------+      +-------------+
   |   Circle    |      |  Rectangle  |
   |  + area()   |      |   + area()  |
   +-------------+      +-------------+
```

You should be able to **code** that hierarchy in Python *and* explain inheritance + polymorphism using it.

## Quick revision card

- 4 pillars: Encapsulation, Abstraction, Inheritance, Polymorphism.
- Class = blueprint; Object = instance.
- Overloading = compile-time; Overriding = runtime.
- Abstract class vs Interface (Java) — fields vs no fields, partial vs all-abstract (pre Java-8).
- Diamond problem in multiple inheritance; Python solves with MRO.
- Composition > Inheritance for flexibility.
- SOLID: S, O, L, I, D.
- `super` for parent access; `this/self` for current object.
- equals + hashCode contract (Java) / `__eq__` + `__hash__` (Python).
- Shallow vs deep copy.
