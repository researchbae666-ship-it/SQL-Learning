---
lesson_id: C06-L02
chapter: 6
lesson: 2
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C06-L02: SELECT *

**Chapter:** 6 · **Lesson:** 2 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

SELECT *

SELECT * returns all columns in the same order as they are defined in the table.


When using SELECT *, the data returned by a query can change whenever the table definition
changes. This increases the risk that different versions of your application or your database are
incompatible with each other.

Furthermore, reading more columns than necessary can increase the amount of disk and network
I/O.


So you should always explicitly specify the column(s) you actually want to retrieve:

 --SELECT *                                  don't
   SELECT ID, FName, LName, PhoneNumber   -- do
   FROM Emplopees;


(When doing interactive queries, these considerations do not apply.)


However, SELECT * does not hurt in the subquery of an EXISTS operator, because EXISTS ignores
the actual data anyway (it checks only if at least one row has been found). For the same reason, it
is not meaningful to list any specific column(s) for EXISTS, so SELECT * actually makes more
sense:

 -- list departments where nobody was hired recently
 SELECT ID,
        Name
 FROM Departments
 WHERE NOT EXISTS (SELECT *
                   FROM Employees
                   WHERE DepartmentID = Departments.ID
                     AND HireDate >= '2015-01-01');

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
