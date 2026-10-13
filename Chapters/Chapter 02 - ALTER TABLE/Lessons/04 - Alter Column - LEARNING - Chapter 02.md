---
chapter: 2
textbook_lesson: C02-L04
status: completed
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: first_attempt_3_of_10_corrected_10_of_10_passed
record_fidelity: grounded source summary, instructor-authored example, verbatim learner submission and grade
---

# Chapter 2 — Lesson 4: ALTER COLUMN

**Status:** COMPLETED — first attempt **3/10**, corrected attempt **10/10**.

## Original textbook

The chapter's ALTER COLUMN subsection gives this example:

```sql
ALTER TABLE Employees
ALTER COLUMN StartingDate DATETIME NOT NULL DEFAULT (GETDATE())
```

The textbook describes converting `StartingDate` from DATE to DATETIME and specifying a current-date default. This is **not valid as written for Microsoft SQL Server 2012**: the ALTER COLUMN command cannot include the DEFAULT clause in the same syntax. The chapter excerpt is faithfully retained above; the learner should use a separate DEFAULT constraint when needed.

## SQL Server 2012 lesson

`ALTER TABLE ... ALTER COLUMN` changes the definition of an **existing** column (for example increasing its maximum VARCHAR length). This does not create a new column, nor rename it.

Instructor example (assuming an existing nullable `SPECIALTY VARCHAR(60)`):

```sql
ALTER TABLE DOCTORS
ALTER COLUMN SPECIALTY VARCHAR(100) NULL;
```

It allows longer values in the same column while retaining data if the change succeeds. In SQL Server, explicitly state `NULL` or `NOT NULL` as desired. Some type conversions, narrowing changes, and dependent indexes/constraints may prevent an ALTER COLUMN operation.

If adding a default is also required, it is a **separate** `ALTER TABLE ... ADD CONSTRAINT ... DEFAULT ... FOR ...` operation, learned earlier.

## Challenge — first attempt assessed

> The DOCTORS table has an existing `SPECIALTY VARCHAR(60) NULL` column. Increase its size to `VARCHAR(100) NULL` without creating a second column or deleting the table. Write one SQL Server 2012 `ALTER TABLE ... ALTER COLUMN` statement. Assume there are no incompatible constraints or indexes on the column.

### Actual learner SQL submitted on 2026-10-13 (verbatim)

```sql
ALTER TABLE DOCTORS
ALTER SPECIALTY VARCHAR(60) NULL,
UPDATE PECIALTY VARCHAR(100) NULL;
```

### Assistant's line-by-line grade: **3/10 — correction required**

| Submitted fragment | Assessment | Explanation |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Existing target table identified. |
| `ALTER SPECIALTY VARCHAR(60) NULL` | Incorrect | SQL Server requires `ALTER COLUMN SPECIALTY`; retaining `VARCHAR(60)` would not meet the size increase to 100. |
| Comma after `NULL` | Incorrect | This task is one `ALTER COLUMN` definition, not comma-separated DDL/DML operations. |
| `UPDATE PECIALTY` | Incorrect | `UPDATE` modifies row data, not datatype; and `PECIALTY` is missing the initial S. |
| `VARCHAR(100) NULL` | Partially correct | Required new type and nullability identified, but not in a valid column alteration. |
| `;` | Correct | Statement ends with a semicolon but overall SQL is not valid T-SQL. |

**Grade rationale:** Partial credit for identifying the correct table and desired final datatype/nullability; substantial deduction for missing `COLUMN`, inappropriate `UPDATE`, invalid comma, wrong old length, and column-name typo. **3/10**, below the lesson's pass requirement.

**Correct syntax shown by assistant (not yet a new student submission):**

```sql
ALTER TABLE DOCTORS
ALTER COLUMN SPECIALTY VARCHAR(100) NULL;
```

The SQL has only been reviewed, not run against a real SQL Server 2012 instance.

## Corrected attempt — 2026-10-13 (user's actual SQL, verbatim)

```sql
ALTER TABLE DOCTORS
ALTER COLUMN SPECIALTY VARCHAR(100) NULL;
```

### Grade: **10/10 — PASS**

| Submitted SQL | Assessment |
|---|---|
| `ALTER TABLE DOCTORS` | Correct existing table. |
| `ALTER COLUMN SPECIALTY` | Correctly targets the existing column for a definition change, not data updates. |
| `VARCHAR(100)` | Correctly expands declared maximum length from 60 to 100. |
| `NULL;` | Keeps the column nullable and correctly ends the statement. |

**Outcome:** The user corrected all first-attempt issues; C02-L04 ALTER COLUMN exercise is complete, with 10/10 on the correction. The corrected statement has been reviewed for Microsoft SQL Server 2012 syntax only; it has **not** been executed on an actual database. It assumes the column exists, current data is compatible, and no constraints/indexes block the change.

**Next concept:** Adding a PRIMARY KEY to an existing table as in the closing section of the original Chapter 2. The reference book's named-key syntax is not valid verbatim for SQL Server 2012, so the next lesson explicitly distinguishes source text from SQL Server syntax.

**Coverage caution:** The original Chapter 2 also shows `ADD PRIMARY KEY`, which should be covered before the final Chapter 2 mastery exam. Chapter mastery threshold: 85%.
