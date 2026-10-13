---
assessment_id: CH01-MASTERY-2026-10-13
chapter: 1
date: 2026-10-13
maximum_points: 20
earned_points: 19.5
percent: 97.5
pass_threshold_percent: 85
status: passed
sql_target: Microsoft SQL Server 2012
---

# Chapter 1 — Mastery Examination (2026-10-13)

**Result: PASS — 19.5 / 20 (97.5%).** Passing threshold: 17/20 = 85%.

**Scope from the original chapter:** SQL versus SQL Server, ISO/ANSI SQL standards and versions, DDL/DML/DCL, CRUD, and the three possible write actions of MERGE.

## Questions, original learner answers, and grading

### Q1. What is the difference between SQL and Microsoft SQL Server?

**Verbatim learner answer:**

> The fundamental difference is that SQL is a programming language, whereas Microsoft SQL Server is the software application that executes that language

**Grade: 4 / 4.** Correct. SQL is the query language; Microsoft SQL Server is an RDBMS product implementing a SQL dialect.

### Q2. What is the difference between SQL:2011 and SQL Server 2012?

**Verbatim learner answer:**

> SQL:2011 is an international ANSI/ISO database query language standard, whereas SQL Server 2012 is a specific relational database management system (RDBMS) product built and sold by Microsoft.

**Grade: 4 / 4.** Correct distinction: language standard versus product version.

### Q3. What do DDL, DML and DCL do? Give one example of a command for each.

**Original learner response (text retained, with table columns formatted as Markdown):**

| Category | What it Does | Common Example |
|---|---|---|
| DDL (Data Definition Language) | Defines and modifies the physical structure (schema, tables, indexes) of the database. Changes are typically permanent and auto-committed. | CREATE (e.g., creating a new database table) |
| DML (Data Manipulation Language) | Manages and modifies the actual data stored inside those database tables. Changes can usually be rolled back before they are permanently saved. | INSERT (e.g., adding a new row of data) |
| DCL (Data Control Language) | Controls security, permissions, and access rights for database users. It dictates who can read or alter database objects. | GRANT (e.g., giving a user permission to read a table) |

**Grade: 3.5 / 4.** All three categories and example commands are correct as defined in the textbook. A minor technical qualification applies to "DDL changes are typically permanent and auto-committed": in SQL Server 2012, many DDL operations can be included in explicit transactions and rolled back. **This transaction nuance is outside Chapter 1's coverage**, but matters for precision when learning SQL Server.

### Q4. Match the four CRUD operations to their SQL commands.

**Verbatim learner answer:**

```text
Create __insert
Read __ Select
Update __ Update
Delete __ Delete
```

**Grade: 4 / 4.** Correct mappings: Create → INSERT; Read → SELECT; Update → UPDATE; Delete → DELETE.

### Q5. What are the three data-changing operations that MERGE can combine?

**Verbatim learner answer:**

> insert update delete

**Grade: 4 / 4.** Correct: INSERT, UPDATE, DELETE.

## Final rubric

| Question | Points | Earned |
|---|---:|---:|
| SQL vs SQL Server | 4 | 4 |
| SQL:2011 vs SQL Server 2012 | 4 | 4 |
| DDL/DML/DCL with examples | 4 | 3.5 |
| CRUD and SQL commands | 4 | 4 |
| MERGE operations | 4 | 4 |
| **TOTAL** | **20** | **19.5** |

**Final percentage:** 97.5%. **Decision:** PASS (≥85%).

## Next chapter

**Chapter 2: ALTER TABLE**, not yet tested for chapter mastery.

## Provenance

Questions and learner answers are from the actual Chapter 1 exam submitted in this conversation. The score and feedback are from the immediately ensuing assistant grading. The original SQL textbook Chapter 1 confirms the general concepts; the SQL Server 2012 DDL transaction nuance is a clarification from outside that chapter. This document is a real assessment record, not a reconstruction of an unavailable historical lesson.
