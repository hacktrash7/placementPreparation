# 02 — Programming Fundamentals

This module turns you from "I know loops and if-else" into "I can write a clean 30-line function with confidence". It is a **prerequisite for the DSA module** (`03-dsa/`).

## Which language should you use?

For a beginner targeting service MNCs, the **best primary language is Python**, with **secondary familiarity with Java or C**.

| Goal                                       | Best language  | Why                                                                 |
| ------------------------------------------ | -------------- | ------------------------------------------------------------------- |
| Learn fastest, code most readable          | **Python**     | Clean syntax, great REPL, fewer footguns.                           |
| TCS NQT Programming Logic MCQs             | **C**          | Many MCQs use C-style pointer/output questions.                     |
| Infosys / TCS coding round                 | Python or Java | Both accepted; Python is faster to write.                           |
| Long-term industry (services + product)    | **Java**       | Most service MNC training uses Java; product companies often Java/C++. |

**Recommendation:** Master **Python** first (Weeks 1-6), then learn enough **C** to read pseudocode MCQs (1 week), then optionally pick up **Java OOP syntax** before placements (1 week, since OOP concepts transfer).

## Files in this module

- [`python-track.md`](python-track.md) — Full Python beginner-to-comfortable curriculum.
- [`c-essentials.md`](c-essentials.md) — Just enough C for TCS/Infy pseudocode/output MCQs.
- [`java-quickstart.md`](java-quickstart.md) — Java syntax cheat-sheet for someone who already knows Python.
- [`programming-logic-mcqs.md`](programming-logic-mcqs.md) — How to crack output-prediction and pseudocode MCQs.

## How to install everything

You only need three things:

1. **Python 3.10+** — install from [python.org](https://www.python.org/) (Windows/Mac) or via your package manager.
2. **VS Code** — free editor; install the *Python* extension by Microsoft.
3. **Git** — comes pre-installed on most Linux/Mac; on Windows install [Git for Windows](https://git-scm.com/).

Verify:

```bash
python --version      # should print 3.x
code --version        # opens VS Code
git --version
```

That's the whole setup. No paid IDEs, no fancy plugins.

## Output target by end of Phase 1 (Week 6)

You should be able to, **from scratch, in 25 minutes**, write Python code that:

- Reads N integers from input and prints the sum, average, max, min.
- Reverses a string without using `[::-1]` (loop-based).
- Counts vowels & consonants in a sentence.
- Generates the first N Fibonacci numbers.
- Checks if a number is prime.
- Reads a CSV and prints the row with the maximum value in column "marks".

If you can do those, you're ready for the DSA module.
