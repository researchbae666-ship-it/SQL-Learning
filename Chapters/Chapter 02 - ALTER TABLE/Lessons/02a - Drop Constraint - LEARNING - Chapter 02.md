---
chapter: 2
textbook_lesson: C02-L02a
status: completed
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: passed_10_of_10
record_fidelity: source-grounded teaching summary; exact user SQL and grading
---

# Chapter 2 — Drop Constraint: Learning Record

## Textbook context

After `DROP COLUMN`, the textbook teaches `DROP CONSTRAINT` with the example `ALTER TABLE Employees DROP CONSTRAINT DefaultSalary`.

The source also cautions about constraints attached to columns before deleting columns.

## Teaching in this conversation

A **constraint** is a rule associated with a table, such as a requirement that an age be at least 18. A `DROP COLUMN` removes the column and the data in it; `DROP CONSTRAINT` removes the named rule but keeps the column and its existing data.

Example from the book (with optional statement terminator for SQL Server 2012):

```sql
ALTER TABLE Employees
DROP CONSTRAINT DefaultSalary;
```

In Microsoft SQL Server 2012 the constraint must exist under the specified name, and permissions/dependencies can affect success. Dropping a constraint changes schema validation, not values stored in the column.

## Coding challenge — PASSED, 10/10

> The `DOCTORS` table contains an `AGE` column. It also has a CHECK constraint named `CK_DOCTORS_AGE` that restricts the allowed values of AGE. Remove **only the constraint**, keeping the `AGE` column and all doctors' records. Write a single SQL Server 2012 statement using `ALTER TABLE` and `DROP CONSTRAINT`.

### Exact submitted SQL — 2026-10-13

```sql
ALTER TABLE DOCTORS
DROP CONSTRAINT CK_DOCTORS_AGE;
```

### Assistant's line-by-line assessment

**Final grade: 10/10 — fully correct for Microsoft SQL Server 2012.**

| SQL portion | Outcome | Reason |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Targets the requested existing table. |
| `DROP CONSTRAINT` | Correct | Removes a named rule, not a column. |
| `CK_DOCTORS_AGE` | Correct | Exact named CHECK constraint from the prompt. |
| `;` | Correct | Ends the statement. |

**Outcome:** The command would remove the named constraint while preserving the `AGE` column and existing data, assuming that the constraint exists and the operation succeeds. This was graded by reviewing SQL; it was **not actually executed** in SQL Server.

**Next concept:** `ADD CONSTRAINT`, specifically adding a named DEFAULT constraint, as demonstrated in Chapter 2 of the ebook.

**Chapter status:** In progress. Chapter mastery threshold = 85%.
