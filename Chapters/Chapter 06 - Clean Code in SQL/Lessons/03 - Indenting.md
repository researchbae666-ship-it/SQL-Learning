---
lesson_id: C06-L03
chapter: 6
lesson: 3
status: planned
source: ../CHAPTER.md
sql_target: Microsoft SQL Server 2012 (compatibility not yet reviewed)
---

# C06-L03: Indenting

**Chapter:** 6 · **Lesson:** 3 of 4 · **Status:** Planned (historical progress not yet reconciled)

## Textbook material

The following excerpt is preserved from this chapter's archived textbook text. The source uses multiple SQL dialects; validate syntax for SQL Server 2012 before exercises.

Indenting

There is no widely accepted standard. What everyone agrees on is that squeezing everything into
a single line is bad:

 SELECT d.Name, COUNT(*) AS Employees FROM Departments AS d JOIN Employees AS e ON d.ID =
 e.DepartmentID WHERE d.Name != 'HR' HAVING COUNT(*) > 10 ORDER BY COUNT(*) DESC;


At the minimum, put every clause into a new line, and split lines if they would become too long
otherwise:

 SELECT d.Name,
        COUNT(*) AS Employees
 FROM Departments AS d
 JOIN Employees AS e ON d.ID = e.DepartmentID
 WHERE d.Name != 'HR'
 HAVING COUNT(*) > 10
 ORDER BY COUNT(*) DESC;


Sometimes, everything after the SQL keyword introducing a clause is indented to the same
column:

 SELECT   d.Name,
          COUNT(*) AS Employees
 FROM     Departments AS d
 JOIN     Employees AS e ON d.ID = e.DepartmentID
 WHERE    d.Name != 'HR'
 HAVING   COUNT(*) > 10
 ORDER BY COUNT(*) DESC;




(This can also be done while aligning the SQL keywords right.)

Another common style is to put important keywords on their own lines:

 SELECT
      d.Name,
      COUNT(*) AS Employees
 FROM
      Departments AS d
 JOIN
      Employees AS e
      ON d.ID = e.DepartmentID
 WHERE
      d.Name != 'HR'
 HAVING
      COUNT(*) > 10
 ORDER BY
      COUNT(*) DESC;



Vertically aligning multiple similar expressions improves readability:

 SELECT Model,
        EmployeeID
 FROM Cars
 WHERE CustomerID = 42
   AND Status      = 'READY';



Using multiple lines makes it harder to embed SQL commands into other programming languages.
However, many languages have a mechanism for multi-line strings, e.g., @"..." in C#, """...""" in
Python, or R"(...)" in C++.

## Tutoring session record

*Pending. When this lesson is taught or its past conversation is imported, append the actual exchange, learner's SQL submissions, corrections, feedback, and assessment results faithfully. Do not invent chat content.*
