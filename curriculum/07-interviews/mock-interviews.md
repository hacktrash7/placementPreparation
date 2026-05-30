# Mock Interviews — How to Run Them Yourself

Mock interviews are the single highest-leverage activity in your final 6 weeks. You either practice in safety, or improvise in front of the actual recruiter. Choose safety.

## Two formats — do both

### Format A — Solo mock (3 times/week)

You can do this entirely alone.

```
1. Pick a question type randomly (use a die or random.org):
     1 → DSA easy
     2 → DSA medium
     3 → DBMS rapid-fire (5 Qs)
     4 → OS rapid-fire (5 Qs)
     5 → HR question
     6 → Project deep-dive
2. Set a 5-minute timer.
3. Record yourself answering OUT LOUD on your phone.
4. Stop. Listen to the recording. Note 3 issues:
     - Pauses?
     - Grammar?
     - Did you address all parts of the question?
     - Did you sound confident or apologetic?
5. Do one re-take. Listen again.
```

You'll *cringe* at the first recording. That's the point. By recording #10, your delivery is unrecognisable.

### Format B — Peer mock (1-2 times/week)

Pair with a classmate or senior who is also placement-prepping.

**Roles**:
- **Interviewer** — uses a question list (see below), gives feedback honestly.
- **Candidate** — treats it like the real thing.

**Run-of-show (45 minutes)**:
```
0-5    : "Tell me about yourself." Project intro.
5-15   : 1 coding problem on paper / shared editor.
15-25  : 5-7 rapid-fire CS theory questions.
25-35  : Project deep-dive — at least 3 follow-ups.
35-40  : HR-style: "Why this company?", "Strengths?", "Weakness?".
40-45  : Feedback both ways.
```

**Feedback prompts** (the interviewer should answer these):
1. On a scale of 1-10, how clear was the candidate's communication?
2. Did they think out loud during coding?
3. Did they ask clarifying questions?
4. Were their CS theory answers crisp (≤ 20 sec)?
5. Did they answer "Why this company?" with a specific reason?
6. **One thing to keep doing. One thing to improve.**

Swap roles. Do another 45-minute round. That's a 90-minute high-impact session.

## A bank of 60 mock-interview questions

> Print this. Tear it up. Pick one at random when running a solo mock.

### DSA (mostly easy-medium; aim for ≤ 20 min each)

1. Reverse a linked list (iteratively).
2. Find the middle of a linked list in one pass.
3. Two-sum on an unsorted array.
4. Detect cycle in a linked list.
5. Check if a string is an anagram of another.
6. Find the maximum subarray sum.
7. Find the first non-repeating character.
8. Implement a stack using two queues.
9. Validate parentheses string.
10. Find the kth largest element.
11. Find the longest substring without repeating characters.
12. Implement binary search.
13. Merge two sorted arrays in-place.
14. Move zeros to the end.
15. Inorder traversal of a binary tree (iterative).
16. Find the diameter of a binary tree.
17. Find LCA of two nodes in BST.
18. Number of islands in a grid.
19. Climbing stairs (DP).
20. Coin change minimum coins.

### CS Theory rapid-fire (≤ 20 sec each)

21. Difference between process and thread?
22. What is a deadlock?
23. Explain ACID.
24. Difference between TCP and UDP.
25. What is a B+ tree?
26. What is virtual memory?
27. Difference between primary key and unique key?
28. Difference between abstract class and interface?
29. What is a DNS?
30. What is encapsulation?
31. Difference between SQL and NoSQL?
32. What's a context switch?
33. Page replacement algorithms — name 3.
34. What is normalization? Why?
35. Explain the 3-way handshake.
36. What is polymorphism?
37. Difference between mutex and semaphore?
38. What's a foreign key?
39. What's a thread-safe class?
40. What is the OSI model?

### Project deep-dive prompts

41. Walk me through the architecture of your project.
42. Why did you choose X technology over Y?
43. What was the toughest bug you fixed in this project?
44. How would you scale this to 10× users?
45. What part are you proudest of?
46. What would you change if you started over?
47. How did you test it?
48. How did you handle authentication?
49. Where is it deployed and how?
50. Did you work alone or in a team? What was your specific contribution?

### HR-style

51. Tell me about yourself in 60 seconds.
52. Why <company>?
53. Why service IT and not product?
54. Tell me about a time you handled conflict in a team.
55. Strength + weakness?
56. Where do you see yourself in 5 years?
57. Are you comfortable with relocation and shift work?
58. What's your dream job?
59. Why should we hire you?
60. Do you have any questions for us?

## Free / cheap mock platforms

- **Pramp** (free) — peer-to-peer DSA mocks; matches you with a random partner globally.
- **InterviewBit Mock Interview** — free + paid.
- **PrepInsta Prime** — paid; mocks specifically for TCS / Infy patterns.
- **ChatGPT / Claude in interviewer mode** — surprisingly effective for HR + theory drills. Prompt:
  ```
  "Act as a TCS HR interviewer. Ask me one question at a time and wait
   for my answer before evaluating it. After 8 questions, give me a
   feedback report covering clarity, confidence, content, and STAR usage."
  ```

## Track your mock performance

A small log:

```
| Date | Format (solo/peer) | Type (DSA/CS/HR) | Question | Self-score 1-10 | What to improve |
```

Look at it every Sunday. The pattern of *what keeps coming up as a weakness* is your prep agenda for the next week.

## The biggest mistake students make

Doing 0 mocks. Then walking into the real interview and "discovering" they freeze on "Tell me about yourself."

The fix is **boring** and **effective**: do 2-3 mocks a week starting Week 16, and you will land an offer.
