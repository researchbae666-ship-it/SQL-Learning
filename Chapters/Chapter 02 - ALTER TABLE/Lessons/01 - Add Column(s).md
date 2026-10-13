---
lesson_id: C02-L01
chapter: 2
lesson: 1
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C02-L01: Add Column(s)

**Chapter:** 2 · **Lesson:** 1 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Chapter 2: ALTER TABLE
Introduction
ALTER command in SQL is used to modify column/constraint in a table


Syntax
   • ALTER TABLE [table_name] ADD [column_name] [datatype]


Examples
Add Column(s)

 ALTER TABLE Employees
 ADD StartingDate date NOT NULL DEFAULT GetDate(),
     DateOfBirth date NULL


The above statement would add columns named StartingDate which cannot be NULL with default
value as current date and DateOfBirth which can be NULL in Employees table.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
