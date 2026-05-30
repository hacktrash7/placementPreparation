# SQL — The Highest-ROI Skill on Your Resume

Every IT services company uses RDBMS (TCS, Infosys, Wipro). SQL questions appear in **technical interviews, coding tests, and on-the-job training**. Goal: become **confident with a JOIN-heavy 2-table query and basic aggregation** in 2 weeks.

## What "good enough" looks like

By the end of this module you can:

- Read a JSON/CSV → load into SQLite / MySQL.
- Write a 30-line SELECT with JOINs, GROUP BY, HAVING, subqueries, ORDER BY.
- Define indexes and explain why.
- Discuss normalization (links back to `04-cs-core/dbms.md`).

## Setup (zero cost)

Easiest path: **SQLite + DB Browser for SQLite** OR **MySQL Community Edition**.

Or skip installation entirely:
- Use **LeetCode SQL** (online judge).
- **HackerRank SQL** (online).
- **db-fiddle.com** / **SQLZoo** (browser sandbox).

## Topic roadmap (14 days, 30 min/day)

### Day 1-2 — Basics
- `CREATE TABLE`, data types (`INT`, `VARCHAR`, `DATE`, `BOOLEAN`).
- `INSERT INTO`, `UPDATE`, `DELETE`.
- `SELECT ... FROM ... WHERE ... ORDER BY ...`.

### Day 3-4 — Filtering & functions
- `LIKE`, `IN`, `BETWEEN`, `IS NULL`.
- String functions: `LOWER`, `UPPER`, `SUBSTR`, `LENGTH`, `CONCAT`.
- Numeric: `ABS`, `ROUND`, `MOD`.
- Date functions (`DATE_FORMAT`, `DATEDIFF`).

### Day 5-6 — Aggregation
- `COUNT, SUM, AVG, MIN, MAX`.
- `GROUP BY` + `HAVING`.
- `DISTINCT`.

### Day 7-8 — Joins
- INNER, LEFT, RIGHT, FULL OUTER, CROSS, SELF.
- Multi-table joins.
- Aliases (`SELECT e.name FROM employees e JOIN departments d ON e.dept_id = d.id`).

### Day 9-10 — Subqueries & set ops
- Scalar, row, table subqueries.
- Correlated vs non-correlated.
- `EXISTS`, `IN`, `NOT IN`.
- `UNION`, `UNION ALL`, `INTERSECT`, `EXCEPT`.

### Day 11-12 — Window functions
- `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`.
- `LAG()`, `LEAD()`.
- `SUM() OVER (PARTITION BY ...)`.

These are **gold** for resume — many interviewers ask "find the 2nd highest salary per department" expecting window functions.

### Day 13 — Constraints, indexes, views
- `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE`, `CHECK`, `NOT NULL`, `DEFAULT`.
- `CREATE INDEX`, when to use.
- `CREATE VIEW`.

### Day 14 — Mini-project
- Build a small DB (5-6 tables) for a domain you like (movies, library, hostel attendance, ecommerce).
- Run 10 "business questions" as SQL queries.
- Push schema + queries + 1-page README to GitHub.

## 25 must-solve SQL problems

> Solve on LeetCode or HackerRank. Time-box each to 15 min.

1. Find duplicate emails.
2. Find customers who never ordered.
3. Find Nth highest salary (2nd, 3rd, generic Nth).
4. Department-wise highest salary.
5. Combine two tables (LEFT JOIN).
6. Employees earning more than their manager.
7. Rank scores (DENSE_RANK).
8. Consecutive days a user logged in (window functions).
9. Department-wise top-3 earners (per-group top-k).
10. Pivot a table (rows → columns).
11. Customers who bought all products (division).
12. Date difference (days between order and shipment).
13. Running total of sales by month.
14. Median salary (no MEDIAN function).
15. Find employees with same join date.
16. Replace NULL with default (`COALESCE`).
17. Group by year and month from a date column.
18. Self-join: employee–manager hierarchy.
19. Find products not sold in last 30 days.
20. Top selling product in each category.
21. Find duplicate transactions.
22. Customers with 3+ consecutive orders.
23. Conversion rate from sign-up to purchase.
24. Count distinct user activity over rolling 7-day window.
25. SQL injection example — *explain* (interview question), don't actually exploit.

## SQL cheatsheet

```sql
-- Basic skeleton
SELECT col1, col2, AGG(col3) AS total
FROM   table1 t1
JOIN   table2 t2 ON t1.id = t2.t1_id
WHERE  t1.col1 IS NOT NULL
GROUP BY col1, col2
HAVING total > 100
ORDER BY total DESC
LIMIT 10;

-- Nth highest salary
SELECT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET N-1;        -- where N is the rank

-- Top-K per group (window)
WITH ranked AS (
  SELECT e.*,
         ROW_NUMBER() OVER (PARTITION BY dept_id ORDER BY salary DESC) AS rn
  FROM employees e
)
SELECT * FROM ranked WHERE rn <= 3;

-- Anti-join (customers with no orders)
SELECT c.id, c.name
FROM   customers c
LEFT JOIN orders o ON o.customer_id = c.id
WHERE  o.id IS NULL;

-- Pivot
SELECT
  product,
  SUM(CASE WHEN region='North' THEN sales END) AS north,
  SUM(CASE WHEN region='South' THEN sales END) AS south
FROM sales
GROUP BY product;
```

## How to put SQL on your resume

```
SQL — Wrote 30+ queries on a custom Library DB (5 tables, ~1,000 rows);
      experience with JOINs, GROUP BY, window functions, subqueries, indexing.
      Solved 50+ problems on HackerRank/LeetCode SQL track.
```

That's a credible resume bullet and survives any follow-up question.
