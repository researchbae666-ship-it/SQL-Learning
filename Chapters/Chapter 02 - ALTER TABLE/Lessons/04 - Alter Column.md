---
lesson_id: C02-L04
chapter: 2
lesson: 4
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C02-L04: Alter Column

**Chapter:** 2 · **Lesson:** 4 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Alter Column

 ALTER TABLE Employees
 ALTER COLUMN StartingDate DATETIME NOT NULL DEFAULT (GETDATE())


This query will alter the column datatype of StartingDate and change it from simple date to datetime
and set default to current date.

Add Primary Key

 ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID)


This will add a Primary key to the table Employees on the field ID. Including more than one column
name in the parentheses along with ID will create a Composite Primary Key. When adding more
than one column, the column names must be separated by commas.

 ALTER TABLE EMPLOYEES ADD pk_EmployeeID PRIMARY KEY (ID, FName)


Read ALTER TABLE online: https://riptutorial.com/sql/topic/356/alter-table

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
