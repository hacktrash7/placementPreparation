# Technical Interview Playbook

Most candidates lose technical interviews not on knowledge but on **process**. Master the process; the knowledge you already have works.

## The 5-step DSA interview process

When given a coding question, follow these *steps out loud*:

### 1. Clarify

```
"Let me make sure I understand:
 - The input is X.
 - The output should be Y.
 - Can the array be empty? Are negatives allowed? What about duplicates?
 - Is the input sorted? Roughly how large is n?
 - Should I optimise for time or space?"
```

This buys you ~60 seconds of thinking, signals seniority, and *often* the interviewer hints at constraints.

### 2. Work an example

Take the example given (or invent one). Trace what the answer should be **by hand**. If you can't produce the expected output manually, you don't understand the problem yet.

### 3. Brute force first

```
"The brute force is to do X. That's O(n²) time, O(1) space.
 Let me see if we can do better."
```

Stating brute force explicitly:
- Shows you understand the problem.
- Gives you a fallback if you can't find optimal.
- Builds rapport — the interviewer knows you can produce *something*.

### 4. Optimise

Identify the inefficiency in brute force. Pattern-match to your patterns cheatsheet ([`../03-dsa/patterns-cheatsheet.md`](../03-dsa/patterns-cheatsheet.md)):

```
"Each pair (i,j) is being recomputed. If I store running sums in a
hashmap, I can check membership in O(1) instead of O(n)."
```

### 5. Code, test, edge cases

```
"I'll code it up now."
[write code]
"Let me trace through example 1 — yes, it produces 3.
 Edge cases: empty array → return 0. Single element → return that element.
 All negatives → ... works because of the inner check."
```

## A real interview transcript template

```
Interviewer: "Given a sorted array of integers, find two numbers that
              sum to a target. Return their indices."

You:  "Let me re-state: a sorted array of ints, plus a target int, and
       I should return the indices of two elements that sum to target.
       Are there always two such elements? Should I assume uniqueness?
       Should the result be 0-indexed?"

Interviewer: "Assume exactly one solution exists. 0-indexed."

You:  "Brute force would be two nested loops, O(n²). But the array is
       sorted, so I can use two pointers — left at the start, right at
       the end. If sum is too small, move left right; too big, move
       right left. O(n) time, O(1) space."

       [writes code]

       def two_sum_sorted(arr, target):
           l, r = 0, len(arr) - 1
           while l < r:
               s = arr[l] + arr[r]
               if s == target:
                   return [l, r]
               elif s < target:
                   l += 1
               else:
                   r -= 1
           return [-1, -1]

You:  "Let me test on [2, 7, 11, 15], target = 9:
       l=0,r=3 → 2+15=17 > 9, r=2;
       l=0,r=2 → 2+11=13 > 9, r=1;
       l=0,r=1 → 2+7=9 → return [0, 1]. ✓"
```

Notice: you talked the whole time. You clarified. You stated brute force. You optimised. You tested.

## CS theory in interviews (the rapid-fire round)

Many interviewers will fire **8-12 short questions** in a row to see how steady you are. Practise answering each in ≤ 20 seconds.

Examples (try answering aloud right now):

- Difference between mutex and semaphore?
- What's a deadlock?
- Difference between TCP and UDP?
- What's the time complexity of binary search?
- 3 differences between SQL and NoSQL.
- What's a stack? Give 2 real-world uses.
- What's the JVM?
- What is an index in DBMS?
- Difference between an interface and an abstract class?
- Explain Polymorphism.
- Explain the OSI model in one breath.

If you stumble on any → re-read the corresponding quick-revision card in [`../04-cs-core/`](../04-cs-core/) tonight.

## Project deep-dive — the questions you'll get

Pick *one* of your projects. Be ready to answer:

1. **What did you build and why?** (60 seconds)
2. **What's the architecture?** (draw blocks on the whiteboard)
3. **What tech did you choose and why?** ("Why Flask and not Django?")
4. **What was the hardest bug or design problem?**
5. **If you had to scale this to 10× users, what would you change?**
6. **What would you do differently if you started over?**
7. **What did you learn from this project?**

**Anti-pattern**: claiming a project where you can't answer Q5 and Q6 truthfully. Rehearse with a friend.

## Common technical-interview mistakes

- **Coding silently.** Recruiter has no idea what you're doing. Talk.
- **Jumping to code without a plan.** Always pseudocode first.
- **Refusing to consider hints.** When the interviewer says "what if you sorted first?", *take the hint immediately*.
- **Giving up after one wrong attempt.** "Let me try another angle…" buys you respect.
- **Looking unprepared on your own resume.** If "AWS" is on your resume, you better know what an S3 bucket is.

## Whiteboard / paper coding tips

- Write **bigger** than you think. Leave space between lines for edits.
- Use **comments** liberally — they show structure.
- Don't worry about perfect syntax; intent > syntax.
- If you make a mistake, **strike it through cleanly** and continue. Don't erase frantically.

## Body language

- Sit up straight, lean *slightly* forward. Curiosity, not slouch.
- **Eye contact**: with one eye of the camera (for online) or with the interviewer.
- **Pause before answering**: 2 seconds of thinking is far better than 5 seconds of "um, like, so basically…".
- **Smile**: at the greeting and the goodbye.

## After the interview

- Note down what was asked — feeds your error log for next interview.
- **Don't discuss specific questions on social media** (against most companies' policies).
- A simple "Thank you for your time" email is appreciated but not mandatory.

You'll be fine. Service-MNC interviews are *not* the FAANG-level grilling — they're polite, pattern-driven conversations.
