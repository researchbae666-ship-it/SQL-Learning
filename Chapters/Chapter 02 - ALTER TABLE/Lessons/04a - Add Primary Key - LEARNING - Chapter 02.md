---
chapter: 2
textbook_lesson: C02-L04a
status: in_progress
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: single_column_pk_10_of_10_composite_pending
record_fidelity: faithful textbook excerpt with explicit SQL Server 2012 syntax adaptation and teaching summary
---

# Chapter 2 — Add Primary Key: Learning Record

**Status: Single-column PRIMARY KEY challenge PASSED (10/10); composite primary key exercise pending.**

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

## Coding challenge — PASSED (10/10)

> Assume `PATIENTS` is an existing table with `PATIENTID INT NOT NULL`. All PATIENTID values are unique, and the table has no primary key yet. Add a named primary key constraint `PK_PATIENTS` on `PATIENTID` using a single SQL Server 2012 `ALTER TABLE` statement. Do not create a new table or column.

### Verbatim learner submission (2026-10-13)

```sql
ALTER TABLE PATIENTS
ADD CONSTRAINT PK_PATIENTS
PRIMARY KEY (PATIENTID);
```

### Grading: **10/10 — PASS**

| Submitted SQL | Feedback |
|---|---|
| `ALTER TABLE PATIENTS` | Correct target table. |
| `ADD CONSTRAINT PK_PATIENTS` | Valid named-constraint syntax for SQL Server 2012. |
| `PRIMARY KEY (PATIENTID)` | Correct constraint type and existing key column. |
| `;` | Correct terminator. |

The query has valid SQL Server 2012 syntax provided the existing `PATIENTID` values are unique, not null, and the table has no primary key yet. **No SQL Server database was accessed or modified:** this was graded by inspection.

**Result:** Single-column primary key passed with 10/10 on first attempt. The Chapter 2 mastery exam has not yet occurred. The next practice addresses a multi-column *composite* primary key, explicitly mentioned in the book.
