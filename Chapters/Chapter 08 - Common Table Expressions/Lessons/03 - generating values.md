---
lesson_id: C08-L03
chapter: 8
lesson: 3
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C08-L03: generating values

**Chapter:** 8 · **Lesson:** 3 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

generating values

Most databases do not have a native way of generating a series of numbers for ad-hoc use;



however, common table expressions can be used with recursion to emulate that type of function.

The following example generates a common table expression called Numbers with a column i which
has a row for numbers 1-5:

 --Give a table name `Numbers" and a column `i` to hold the numbers
 WITH Numbers(i) AS (
     --Starting number/index
     SELECT 1
     --Top-level UNION ALL operator required for recursion
     UNION ALL
     --Iteration expression:
     SELECT i + 1
     --Table expression we first declared used as source for recursion
     FROM Numbers
     --Clause to define the end of the recursion
     WHERE i < 5
 )
 --Use the generated table expression like a regular table
 SELECT i FROM Numbers;



 i

 1

 2

 3

 4

 5

This method can be used with any number interval, as well as other types of data.

recursively enumerating a subtree

 WITH RECURSIVE ManagedByJames(Level, ID, FName, LName) AS (
     -- start with this row
     SELECT 1, ID, FName, LName
     FROM Employees
     WHERE ID = 1

     UNION ALL

     -- get employees that have any of the previously selected rows as manager
     SELECT ManagedByJames.Level + 1,
            Employees.ID,
            Employees.FName,
            Employees.LName
     FROM Employees
     JOIN ManagedByJames
         ON Employees.ManagerID = ManagedByJames.ID

     ORDER BY 1 DESC       -- depth-first search




 )
 SELECT * FROM ManagedByJames;



 Level    ID   FName       LName

 1        1    James       Smith

 2        2    John        Johnson

 3        4    Johnathon   Smith

 2        3    Michael     Williams

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
