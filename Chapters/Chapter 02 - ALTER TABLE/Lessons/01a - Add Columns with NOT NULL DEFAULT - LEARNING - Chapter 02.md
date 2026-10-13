---
chapter: 2
textbook_lesson: C02-L01
topic: add_columns_with_not_null_default_and_date_null
status: completed
date_started: 2026-10-13
sql_target: Microsoft SQL Server 2012
assessment_status: passed_10_of_10
record_fidelity: actual textbook example, instructor explanation, verbatim student code and grading
---

# Chapter 2 — Add Column(s): NOT NULL, DEFAULT GETDATE(), DATE NULL

**Status: COMPLETED — coding challenge PASSED 10/10.** The earlier one-column and two-nullable-column coding challenges in C02-L01 are already passed at 10/10 each.

## Actual textbook example

The original Chapter 2 *Add Column(s)* section provides:

```sql
ALTER TABLE Employees
ADD StartingDate date NOT NULL DEFAULT GetDate(),
    DateOfBirth date NULL
```

Textbook explanation: the statement adds `StartingDate` that is non-null with the current date as its default and `DateOfBirth`, which allows nulls. See the unchanged [Chapter 2 text](../CHAPTER.md).

## Instructor explanation for Microsoft SQL Server 2012

- `ALTER TABLE Employees`: modify an existing table.
- `ADD`: introduce more than one new column in one statement.
- `StartingDate DATE`: store a date (not time-of-day).
- `NOT NULL`: StartingDate cannot be NULL.
- `DEFAULT GETDATE()`: supply today's date when a row is inserted with no StartingDate; GETDATE() returns current date/time, which is converted to the DATE datatype.
- On a populated SQL Server 2012 table, when this non-null column is added with a valid default, SQL Server also populates the existing rows with the default evaluated as part of the ALTER operation. This is a SQL Server behavior clarification beyond the book's short explanation.
- `, DateOfBirth DATE NULL`: add a second date column and permit NULL. Existing rows receive NULL for DateOfBirth.
- These are column definitions within ADD, not `ALTER COLUMN ... DEFAULT` (which is invalid SQL Server 2012 syntax).

For conventional SQL Server 2012 formatting, a terminating semicolon is acceptable.

## Practice challenge — graded and passed

> Assume `DOCTORS` exists, and the columns `JOINEDDATE` and `RESIGNDATE` do not yet exist. In one `ALTER TABLE ... ADD` command, add `JOINEDDATE DATE NOT NULL DEFAULT GETDATE()` and `RESIGNDATE DATE NULL`. Do not recreate the table.

### Original learner submission (verbatim, 2026-10-13)

```sql
ALTER TABLE DOCTORS
ADD JOINEDDATE DATE NOT NULL DEFAULT GetDate(),
    RESIGNDATE date NULL;
```

### Grade: **10/10 — PASS**

| Submitted fragment | Assessment | Explanation |
|---|---|---|
| `ALTER TABLE DOCTORS` | Correct | Targets existing DOCTORS table. |
| `ADD JOINEDDATE DATE` | Correct | Adds first DATE column. |
| `NOT NULL` | Correct | Non-null requirement for joined date. |
| `DEFAULT GetDate()` | Correct | Uses SQL Server GETDATE() for omitted values; conversion to DATE keeps date only. |
| `, RESIGNDATE date NULL` | Correct | Comma-separated second DATE column permitting NULL. SQL keywords and datatype casing are not significant in this syntax. |
| `;` | Correct | Statement terminator. |

The answer matches the original Chapter 2 *Add Column(s)* structure with the exercise's table and column names. It is valid T-SQL for SQL Server 2012 assuming the table exists and the column names are available, with appropriate permissions and no blockers. **It was reviewed, not executed on a SQL Server instance.**

**Outcome:** This last outstanding *Add Column(s)* variation passed 10/10. The Chapter 2 textbook still lists six constraint types; teach and check these definitions before the chapter mastery exam.

## Pending chapter coverage

After the practical exercise, teach/check the six constraint-type definitions listed in Chapter 2 (PRIMARY KEY, FOREIGN KEY, NOT NULL, UNIQUE, DEFAULT, CHECK). Only then issue the cumulative 85%-pass Chapter 2 exam.
