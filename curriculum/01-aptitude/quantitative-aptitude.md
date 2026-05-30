# Quantitative Aptitude

The "math" section of every placement test. Don't be intimidated — it's all class 8-10 math, just under time pressure. Aim for **~80% accuracy at 60-75 sec/question**.

## Master topic list (in suggested learning order)

Group A and B are *highest priority* — appear in almost every test. Group C are common but lighter.

### Group A — Arithmetic foundations (Weeks 1-3)

1. **Number System** — divisibility, HCF/LCM, remainders, prime factorisation, last digit cyclicity.
2. **Percentages** — base conversions, successive %, percentage change.
3. **Profit, Loss & Discount** — CP/SP/MP, marked-up & discounted prices, dishonest dealer.
4. **Simple Interest & Compound Interest** — annual/half-yearly, CI vs SI difference formula.
5. **Ratio & Proportion** — splitting amounts, mixing ratios, componendo-dividendo (rare).
6. **Averages** — including weighted averages and effect of adding/removing items.
7. **Ages** — present/past/future age word problems.

### Group B — Word problems (Weeks 3-5)

8. **Time, Speed & Distance** — relative speed, trains, boats & streams.
9. **Time & Work** — combined work, pipes & cisterns, efficiency.
10. **Mixtures & Alligations** — replacement, mixing two liquids, alligation rule.
11. **Partnership** — capital × time = profit share.
12. **Permutation & Combination** — arranging, choosing, repetition, circular arrangements.
13. **Probability** — coins, dice, cards, balls in bags, conditional basics.

### Group C — Math you'll see less often (Weeks 5-7)

14. **Mensuration / Geometry basics** — area, perimeter, surface area, volume, Pythagoras.
15. **Algebra** — linear equations, quadratic equations, identities.
16. **Progressions** — AP, GP, sum formulas.
17. **Logarithms** — log rules, simple evaluation.
18. **Data Interpretation (DI)** — tables, bar/line/pie charts, multi-graph sets. *(Very common in Infosys/TCS.)*
19. **Clocks & Calendars** — angle between hands, leap year, day of week.
20. **Heights & Distances** — basic trigonometry word problems. *(Rare for service MNCs.)*
21. **Stocks & Shares / Banker's Discount** — occasional, light coverage is enough.
22. **Surds & Indices** — simplification, comparison.

## Formula cheat-sheet (memorise cold)

> Write these in your own notebook. Re-derive them once each, then commit to memory.

```
% change            : (new - old) / old × 100
Successive %        : a + b + (a·b)/100        (when a, b are signed)
Profit %            : (SP - CP) / CP × 100
Discount %          : (MP - SP) / MP × 100
SI                  : P·R·T / 100
CI                  : P·(1 + R/100)^T − P
CI − SI (2 years)   : P·(R/100)^2
Speed conversion    : km/h × 5/18 = m/s
Relative speed     : same dir → |a − b| ; opposite → a + b
Average             : Sum / Count
Weighted avg        : Σ(w·x) / Σw
Work               : 1/a + 1/b combined ; total work = LCM trick
nPr                 : n! / (n−r)!
nCr                 : n! / (r!·(n−r)!)
P(event)            : favourable / total
AP nth term         : a + (n−1)·d
AP sum              : n/2 · (2a + (n−1)d)
GP nth term         : a · r^(n−1)
GP sum              : a · (r^n − 1)/(r − 1)        for r ≠ 1
Circle              : area = πr²    ; circumference = 2πr
Triangle area       : ½ · b · h     ; equilateral = (√3/4)a²
Cuboid              : V = lwh       ; TSA = 2(lw+wh+wl)
Sphere              : V = 4/3·πr³   ; SA = 4πr²
Cylinder            : V = πr²h      ; CSA = 2πrh   ; TSA = 2πr(r+h)
Cone               : V = 1/3·πr²h  ; CSA = πrl    ; TSA = πr(r+l)
log(ab) = loga+logb   log(a/b)=loga−logb     log(a^n) = n·loga
```

## Speed tricks worth practising

- **Multiplying by 5, 25, 125**: divide by 2, 4, 8 then move decimal.
- **Squares ending in 5**: (n5)² = n(n+1) followed by 25. E.g., 35² = 3·4 || 25 = 1225.
- **% to fraction memory** — these save *enormous* time:

  | %        | Fraction |
  | -------- | -------- |
  | 12.5%    | 1/8      |
  | 16.66%   | 1/6      |
  | 20%      | 1/5      |
  | 25%      | 1/4      |
  | 33.33%   | 1/3      |
  | 37.5%    | 3/8      |
  | 41.66%   | 5/12     |
  | 50%      | 1/2      |
  | 62.5%    | 5/8      |
  | 66.66%   | 2/3      |
  | 75%      | 3/4      |
  | 83.33%   | 5/6      |

- **Last digit of a^n** — find cyclicity of last digit (cycle length 1, 2, or 4). E.g., 7's cycle = 7,9,3,1.
- **Divisibility rules** — by 3 (digit sum), 4 (last two), 8 (last three), 9 (digit sum), 11 (alternating sum).
- **Use approximation in DI.** Don't compute 47.83% of 1284 exactly — round to 48% × 1280 ≈ 614.

## 3-day mini-plan template (apply to every topic)

```
Day 1: Read concept (20 min) → Solve 10 easy questions (30 min).
Day 2: Solve 15 medium questions (45 min), under time. Log mistakes.
Day 3: 10 mixed questions (30 min) + revise yesterday's wrong ones.
```

## How to attempt a real test (TCS NQT style)

- **Read all questions in a section once, mark the long ones for later.**
- **Easy first, hard last.** Never spend > 2 min on a single question on first pass.
- **In DI, scan the question before reading the data.** Saves 50% reading time.
- **Eliminate options**: in MCQs with 4 choices, plugging the option in is often faster than solving algebraically.
- **Never leave blank if there's no negative marking.** For TCS NQT there is no negative marking on most sections — *attempt everything*.

## Practice volume per topic

A safe rule: **≥ 60 questions per topic across all 3 difficulty levels** before you call it "done". Track this in your spreadsheet.

Onward → [`logical-reasoning.md`](logical-reasoning.md).
