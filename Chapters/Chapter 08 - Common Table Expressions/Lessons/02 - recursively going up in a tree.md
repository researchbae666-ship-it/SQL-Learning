---
lesson_id: C08-L02
chapter: 8
lesson: 2
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C08-L02: recursively going up in a tree

**Chapter:** 8 · **Lesson:** 2 of 6 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

recursively going up in a tree

 WITH RECURSIVE ManagersOfJonathon AS (
     -- start with this row
     SELECT *
     FROM Employees
     WHERE ID = 4

      UNION ALL

      -- get manager(s) of all previously selected rows
      SELECT Employees.*
      FROM Employees
      JOIN ManagersOfJonathon
          ON Employees.ID = ManagersOfJonathon.ManagerID
 )
 SELECT * FROM ManagersOfJonathon;



 Id    FName        LName      PhoneNumber     ManagerId   DepartmentId

 4     Johnathon    Smith      1212121212      2           1

 2     John         Johnson    2468101214      1           1

 1     James        Smith      1234567890      NULL        1

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
