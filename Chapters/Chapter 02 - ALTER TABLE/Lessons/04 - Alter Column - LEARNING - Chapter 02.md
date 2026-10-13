---
chapter: 2
textbook_lesson: C02-L04
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: awaiting_student_submission
record_fidelity: grounded source summary; instructor-authored SQL Server-specific example; no learner submission yet
---

# Chapter 2 — Lesson 4: ALTER COLUMN

**Status:** In progress; no student answer yet.

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

## Challenge — awaiting student answer

> The DOCTORS table has an existing `SPECIALTY VARCHAR(60) NULL` column. Increase its size to `VARCHAR(100) NULL` without creating a second column or deleting the table. Write one SQL Server 2012 `ALTER TABLE ... ALTER COLUMN` statement. Assume there are no incompatible constraints or indexes on the column.

**Original student SQL:** Pending.

**Grade and feedback:** Pending.

**Coverage caution:** The original Chapter 2 also shows `ADD PRIMARY KEY`, which should be covered before the final Chapter 2 mastery exam. Chapter mastery threshold: 85%.
