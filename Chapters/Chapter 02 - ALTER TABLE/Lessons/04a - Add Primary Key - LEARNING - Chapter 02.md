---
chapter: 2
textbook_lesson: C02-L04a
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: awaiting_student_submission
record_fidelity: faithful textbook excerpt with explicit SQL Server 2012 syntax adaptation and teaching summary
---

# Chapter 2 — Add Primary Key: Learning Record

**Status: IN PROGRESS** — first coding challenge not yet submitted.

## Textbook basis

The original Chapter 2 ends with Add Primary Key, giving:
```sql
ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID)
```
It also explains that multiple comma-separated columns inside parentheses give a **composite primary key**. See [source excerpt](04a%20-%20Add%20Primary%20Key.md) and the unchanged [Chapter 2 text](../CHAPTER.md).

**Important SQL Server adaptation:** The original named-key syntax needs `CONSTRAINT` in Microsoft's T-SQL. In SQL Server 2012:

```sql
ALTER TABLE EMPLOYEES
ADD CONSTRAINT pk_EmployeeID PRIMARY KEY (ID);
```

## Teaching concept

A primary key identifies each row, requires unique values, and cannot contain NULL. A table has at most one PRIMARY KEY constraint, but this one key may span multiple columns (composite key).

To add an existing column as a primary key, the column must contain unique, non-NULL values and there must not already be a primary key. The command does **not** create a new column.

Instructor-written demonstration:

```sql
ALTER TABLE DOCTORS
ADD CONSTRAINT PK_DOCTORS PRIMARY KEY (DOCTORID);
```

This supposes `DOCTORS` has `DOCTORID INT NOT NULL`, all existing values are unique, and no primary key exists yet.

## Coding challenge — awaiting learner answer

> Assume `PATIENTS` is an existing table with `PATIENTID INT NOT NULL`. All PATIENTID values are unique, and the table has no primary key yet. Add a named primary key constraint `PK_PATIENTS` on `PATIENTID` using a single SQL Server 2012 `ALTER TABLE` statement. Do not create a new table or column.

**Student SQL:** Pending.

**Grade:** Pending.

**Next:** If passed, practice composite keys and check any remaining Chapter 2 source topics before the 85%-threshold chapter mastery exam.
