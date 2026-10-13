---
lesson_id: C02-L02
chapter: 2
lesson: 2
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C02-L02: Drop Column

**Chapter:** 2 · **Lesson:** 2 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Drop Column

 ALTER TABLE Employees
 DROP COLUMN salary;


This will not only delete information from that column, but will drop the column salary from table
employees(the column will no more exist).

Drop Constraint

 ALTER TABLE Employees
 DROP CONSTRAINT DefaultSalary


This Drops a constraint called DefaultSalary from the employees table definition.

Note:- Ensure that constraints of the column are dropped before dropping a column.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
