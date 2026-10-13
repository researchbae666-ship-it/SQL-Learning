---
lesson_id: C11-L02
chapter: 11
lesson: 2
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C11-L02: Create Table From Select

**Chapter:** 11 · **Lesson:** 2 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Create Table From Select

You may want to create a duplicate of a table:

 CREATE TABLE ClonedEmployees AS SELECT * FROM Employees;


You can use any of the other features of a SELECT statement to modify the data before passing it
to the new table. The columns of the new table are automatically created according to the selected
rows.

 CREATE TABLE ModifiedEmployees AS
 SELECT Id, CONCAT(FName," ",LName) AS FullName FROM Employees
 WHERE Id > 10;



Duplicate a table

To duplicate a table, simply do the following:

 CREATE TABLE newtable LIKE oldtable;
 INSERT newtable SELECT * FROM oldtable;

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
