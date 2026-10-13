---
chapter: 2
textbook_lesson: C02-L02a
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: awaiting_student_submission
record_fidelity: source-grounded teaching summary; student response pending
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

## Coding challenge — awaiting learner response

> The `DOCTORS` table contains an `AGE` column. It also has a CHECK constraint named `CK_DOCTORS_AGE` that restricts the allowed values of AGE. Remove **only the constraint**, keeping the `AGE` column and all doctors' records. Write a single SQL Server 2012 statement using `ALTER TABLE` and `DROP CONSTRAINT`.

**Submitted SQL:** Pending.

**Feedback and grade:** Pending.

**Chapter status:** In progress. Chapter mastery threshold = 85%.
