---
lesson_id: C02-L03
chapter: 2
lesson: 3
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C02-L03: Add Constraint

**Chapter:** 2 · **Lesson:** 3 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Add Constraint

 ALTER TABLE Employees
 ADD CONSTRAINT DefaultSalary DEFAULT ((100)) FOR [Salary]


This adds a constraint called DefaultSalary which specifies a default of 100 for the Salary column.



A constraint can be added at the table level.

Types of constraints

   • Primary Key - prevents a duplicate record in the table
   • Foreign Key - points to a primary key from another table
   • Not Null - prevents null values from being entered into a column
   • Unique - uniquely identifies each record in the table
   • Default - specifies a default value
   • Check - limits the ranges of values that can be placed in a column

To learn more about constraints, see the Oracle documentation.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
