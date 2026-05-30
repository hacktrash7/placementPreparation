# DBMS — Database Management Systems

The single most-asked CS subject in service-MNC interviews. Spend serious time here.

## Concept tree (study in this order)

1. **What a DBMS is and why it exists** — files vs DB, data redundancy, integrity.
2. **DBMS architecture** — 1-tier, 2-tier, 3-tier; client–server.
3. **Schema vs instance**, **three-schema architecture** (external / conceptual / internal).
4. **Data models** — relational, ER, hierarchical, network, NoSQL (just be aware of these).
5. **ER model** — entities, attributes, relationships, cardinality, weak entities.
6. **Relational model** — relation, tuple, attribute, domain, keys.
7. **Keys** — super, candidate, primary, alternate, composite, foreign.
8. **Relational algebra** — σ (select), π (project), ⨯, ⨝, ∪, ∩, −, ÷.
9. **SQL** — DDL / DML / DCL / TCL; SELECT, JOIN, GROUP BY, HAVING, subqueries, views, indexes.
10. **Normalization** — 1NF, 2NF, 3NF, BCNF; functional dependencies, decomposition.
11. **Transactions & ACID** — atomicity, consistency, isolation, durability.
12. **Concurrency control** — locking (shared/exclusive), 2PL, deadlocks, timestamp ordering.
13. **Isolation levels** — read uncommitted, read committed, repeatable read, serializable; dirty/non-repeatable/phantom reads.
14. **Indexing** — primary, secondary, clustered vs non-clustered; B+ tree (conceptually).
15. **Recovery** — log-based, checkpoints (concept only).
16. **NoSQL vs SQL** — when to use each.

## Must-know definitions (1-line each)

- **DBMS**: software that manages a database, providing storage, retrieval, security, and concurrency.
- **Primary key**: a chosen candidate key that uniquely identifies a tuple; cannot be NULL.
- **Foreign key**: an attribute in one table that references the primary key of another — enforces referential integrity.
- **Candidate key**: any minimal set of attributes that uniquely identifies a row.
- **Super key**: any set of attributes that uniquely identifies a row (may be non-minimal).
- **Index**: a data structure (usually B+ tree) that speeds up lookups on a column at the cost of write speed and storage.
- **Normalization**: process of decomposing tables to remove redundancy and update anomalies.
- **Functional dependency (FD)**: X → Y means knowing X determines Y.
- **1NF**: only atomic values (no repeating groups or multi-valued attributes).
- **2NF**: 1NF + no partial dependency on a part of the composite primary key.
- **3NF**: 2NF + no transitive dependency (non-key → non-key).
- **BCNF**: every determinant (left side of FD) is a super key.
- **Transaction**: a logical unit of work that must be ACID.
- **ACID**:
  - **Atomicity** — all or nothing.
  - **Consistency** — DB moves from one valid state to another.
  - **Isolation** — concurrent transactions appear serial.
  - **Durability** — once committed, persists despite crashes.
- **Deadlock**: two or more transactions waiting on each other's locks forever.

## Top 40 interview questions with model answers

> Answers are written as you'd *speak* them in 30-60 seconds. Adapt with your own examples.

**1. What is a DBMS? How is it different from a file system?**
A DBMS is software that stores, retrieves, and manages data with features like concurrent access, integrity constraints, security, transactions, and crash recovery. A file system just stores files — it doesn't handle multi-user concurrency, doesn't enforce relationships, and has heavy data redundancy.

**2. Difference between DBMS and RDBMS?**
RDBMS stores data in *tables* with rows and columns and enforces relationships via foreign keys, normalization, and the relational algebra. DBMS is a broader term — it can be hierarchical, network, or relational. Examples: MySQL, PostgreSQL are RDBMS; older systems like IMS are DBMS but not relational.

**3. What are the different types of keys?**
Candidate, primary, alternate, super, composite, and foreign. Primary uniquely identifies a row, foreign references another table's primary key, candidate is any minimal unique set, alternate is a candidate that wasn't chosen as primary, super is any unique set, composite has multiple attributes together.

**4. What are constraints in SQL?**
`NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `DEFAULT`. They enforce data integrity at the table level.

**5. Difference between DELETE, TRUNCATE, and DROP.**
DELETE is DML — removes rows (can have WHERE), logs each delete, can be rolled back, slow.
TRUNCATE is DDL — removes all rows quickly, deallocates pages, generally can't roll back.
DROP is DDL — removes the entire table structure and data.

**6. What is a JOIN? Types of joins?**
Combines rows from two or more tables based on a related column.
- **INNER JOIN** — rows that match in both.
- **LEFT (OUTER) JOIN** — all rows from left + matched right (NULL if no match).
- **RIGHT JOIN** — mirror of LEFT.
- **FULL OUTER JOIN** — all rows from both, NULL where no match.
- **CROSS JOIN** — Cartesian product.
- **SELF JOIN** — table joined with itself.

**7. What is normalization? Why do we need it?**
Decomposing tables to reduce redundancy and avoid update, insert, and delete anomalies. We move stepwise through 1NF → 2NF → 3NF → BCNF, each removing a specific type of anomaly.

**8. Explain 1NF, 2NF, 3NF, BCNF in one line each.**
- **1NF**: each cell holds a single atomic value, no repeating groups.
- **2NF**: 1NF + every non-key attribute fully depends on the *whole* composite primary key.
- **3NF**: 2NF + no non-key attribute depends on another non-key attribute (no transitive dependency).
- **BCNF**: every determinant is a super key — stricter version of 3NF.

**9. What is denormalization?**
Intentionally adding redundancy to a normalized DB to improve read performance, typically for analytical / reporting workloads.

**10. What are ACID properties?** (covered above — repeat in interview using a bank-transfer example).

**11. What is a transaction? Give its states.**
A logical unit of work. States: *Active → Partially Committed → Committed* (success path) or *Active → Failed → Aborted → Terminated* (failure path).

**12. What is concurrency control?**
Mechanisms (locking, timestamp ordering, MVCC) that allow multiple transactions to run simultaneously while preserving ACID.

**13. What is a deadlock? How is it handled?**
Two transactions each hold a lock the other needs. Handle via:
- Prevention (resource ordering, no-wait, wait-die).
- Detection + recovery (wait-for graph; kill the youngest).
- Avoidance (Banker's algorithm — OS-style).

**14. Difference between shared and exclusive locks.**
Shared (S) allows multiple readers; Exclusive (X) allows one writer and blocks everyone else.

**15. What are the isolation levels?**
- **Read Uncommitted** — allows dirty reads.
- **Read Committed** — no dirty, but non-repeatable reads possible.
- **Repeatable Read** — no dirty / non-repeatable, but phantom reads possible.
- **Serializable** — full isolation, lowest performance.

**16. What are dirty, non-repeatable, and phantom reads?**
- **Dirty read**: read of uncommitted data that may be rolled back.
- **Non-repeatable read**: same query returns different *values* in same transaction due to other commits.
- **Phantom read**: same query returns different *rows* (count) due to inserts/deletes by others.

**17. What is an index? Pros and cons?**
A B+ tree (usually) on a column that speeds up lookups from O(n) to O(log n). Cons: extra space, slower inserts/updates/deletes because the index must be maintained.

**18. Clustered vs non-clustered index.**
- **Clustered**: the table's rows are physically stored in the order of this index — only one per table.
- **Non-clustered**: separate structure pointing to rows — can have many.

**19. What is a view?**
A virtual table defined by a SELECT query. Improves abstraction and security (hide columns from users). May or may not be updatable.

**20. Difference between WHERE and HAVING.**
`WHERE` filters rows *before* grouping; `HAVING` filters groups *after* `GROUP BY`. Aggregates can be used in HAVING, not in WHERE.

**21. Difference between UNION and UNION ALL.**
`UNION` removes duplicates (slower); `UNION ALL` keeps them.

**22. What is a stored procedure?**
A reusable SQL routine stored in the DB; can take parameters and reduces network round-trips. Often used to encapsulate business logic.

**23. What is a trigger?**
A procedure that runs automatically in response to INSERT/UPDATE/DELETE events on a table.

**24. What is a subquery? Correlated vs non-correlated.**
A query inside another query. Non-correlated: independent of outer. Correlated: depends on the outer query's row — runs once per outer row.

**25. What's the difference between `IN` and `EXISTS`?**
`IN` checks if a value is in a returned list (slower for huge sub-lists). `EXISTS` checks if a row exists (often faster because it can stop at the first match).

**26. What is referential integrity?**
Foreign keys must reference existing primary keys — you can't have an orphan child row.

**27. Difference between SQL and NoSQL.**
- **SQL**: relational, schema-fixed, ACID, vertical scaling, structured.
- **NoSQL**: schema-flexible, often BASE (eventual consistency), horizontal scaling, key-value/document/columnar/graph stores. Good for huge unstructured data.

**28. What is OLTP vs OLAP?**
- **OLTP**: transactional, small writes/reads, normalised (e.g., banking).
- **OLAP**: analytical, large reads, denormalised, star/snowflake schemas (e.g., data warehouse).

**29. What is functional dependency?**
X → Y means whenever two rows have the same X, they must have the same Y.

**30. What is a B+ tree?**
A balanced multi-way search tree where all data lives at leaves linked in a sorted linked list — used for indexes because it supports range queries in O(log n).

**31. What is a primary key vs a unique key?**
Both must be unique. PK is one per table, cannot be NULL. UNIQUE allows multiple constraints per table and may allow one NULL (DB-dependent).

**32. What is ER diagram? What are its components?**
A diagram modelling data using *entities* (rectangles), *attributes* (ovals), *relationships* (diamonds), and *cardinality* (1:1, 1:N, M:N).

**33. Difference between a weak entity and a strong entity.**
A strong entity has its own primary key. A weak entity depends on a *strong* parent entity for identification and is connected via an identifying relationship.

**34. What is denormalisation and when is it used?**
Adding back redundancy (joining tables) to optimise read-heavy systems (reports, analytics), at the cost of update complexity.

**35. What's the difference between primary and secondary memory storage from a DBMS perspective?**
Primary (RAM) for buffer pools; secondary (disk/SSD) for persistent data. DBs page in/out of buffer pool; disk I/O dominates cost.

**36. What is a deadlock detection wait-for graph?**
A directed graph where T1→T2 means T1 is waiting on T2. A cycle ⇒ deadlock.

**37. What is two-phase locking (2PL)?**
A transaction acquires locks in a *growing phase* then releases in a *shrinking phase* — guarantees serialisability. Strict 2PL releases all locks at commit/abort.

**38. What is a database view vs a materialized view?**
A view is virtual (re-runs the query). A materialized view stores the result physically and is refreshed periodically — much faster reads.

**39. What is sharding?**
Horizontally partitioning a large table across multiple physical machines based on a shard key.

**40. What is replication?**
Maintaining copies of data on multiple machines for fault tolerance and read scaling (master-slave, multi-master).

## Diagrams you should be able to draw

1. **ER diagram** — for a Library system (Book, Member, Loan).
2. **Normalisation example** — start with a denormalised order table, decompose into Orders / Customers / Products.
3. **Transaction state diagram.**
4. **B+ tree** for an index on `age`.
5. **Isolation levels vs anomalies** matrix:

```
                    Dirty  NonRep  Phantom
Read Uncommitted     ✓       ✓       ✓
Read Committed       ✗       ✓       ✓
Repeatable Read      ✗       ✗       ✓
Serializable         ✗       ✗       ✗
```

## SQL drills

Solve **40-60 SQL problems** before placements. These are also asked directly in many interviews.

- LeetCode SQL Easy + Medium (free).
- HackerRank SQL track (free).
- Sample queries to practise:

```sql
-- 1. Find the 2nd highest salary
SELECT MAX(salary) FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);

-- Or:
SELECT salary FROM employees ORDER BY salary DESC LIMIT 1 OFFSET 1;

-- 2. Employees earning more than their manager
SELECT e.name FROM employees e
JOIN employees m ON e.manager_id = m.id
WHERE e.salary > m.salary;

-- 3. Find duplicate emails
SELECT email FROM users GROUP BY email HAVING COUNT(*) > 1;

-- 4. Department-wise highest paid employee
SELECT d.name AS dept, e.name AS emp, e.salary
FROM employees e
JOIN departments d ON e.dept_id = d.id
WHERE e.salary = (
  SELECT MAX(salary) FROM employees WHERE dept_id = e.dept_id
);

-- 5. Customers who never ordered (anti-join)
SELECT c.name FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id
WHERE o.id IS NULL;
```

## Quick revision card (read the night before)

- DBMS = software for managing data; provides ACID, integrity, multi-user.
- Keys: super → candidate → (primary | alternate) ; foreign references PK.
- Normalisation: 1NF (atomic), 2NF (no partial), 3NF (no transitive), BCNF (every determinant is super key).
- ACID: Atomicity, Consistency, Isolation, Durability.
- 4 isolation levels and 3 anomalies — memorise the matrix.
- Joins: INNER, LEFT, RIGHT, FULL OUTER, CROSS, SELF.
- WHERE filters rows; HAVING filters groups.
- Index = B+ tree; clustered (1 per table, ordered) vs non-clustered (many).
- Transaction lifecycle: Active → Partially Committed → Committed; or Failed → Aborted.
- NoSQL: key-value, document, columnar, graph; BASE vs ACID.
