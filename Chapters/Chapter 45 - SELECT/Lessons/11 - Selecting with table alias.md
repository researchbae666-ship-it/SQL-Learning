---
lesson_id: C45-L11
chapter: 45
lesson: 11
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L11: Selecting with table alias

## Textbook excerpt

Selecting with table alias

 SELECT e.Fname, e.LName
 FROM Employees e


The Employees table is given the alias 'e' directly after the table name. This helps remove
ambiguity in scenarios where multiple tables have the same field name and you need to be
specific as to which table you want to return data from.

 SELECT e.Fname, e.LName, m.Fname AS ManagerFirstName
 FROM Employees e
     JOIN Managers m ON e.ManagerId = m.Id


Note that once you define an alias, you can't use the canonical table name anymore. i.e.,

 SELECT e.Fname, Employees.LName, m.Fname AS ManagerFirstName
 FROM Employees e
 JOIN Managers m ON e.ManagerId = m.Id


would throw an error.

It is worth noting table aliases -- more formally 'range variables' -- were introduced into the SQL
language to solve the problem of duplicate columns caused by INNER JOIN. The 1992 SQL
standard corrected this earlier design flaw by introducing NATURAL JOIN (implemented in mySQL,
PostgreSQL and Oracle but not yet in SQL Server), the result of which never has duplicate column
names. The above example is interesting in that the tables are joined on columns with different
names (Id and ManagerId) but are not supposed to be joined on the columns with the same name (
LName, FName), requiring the renaming of the columns to be performed before the join:





 SELECT Fname, LName, ManagerFirstName
 FROM Employees
      NATURAL JOIN
      ( SELECT Id AS ManagerId, Fname AS ManagerFirstName
        FROM Managers ) m;


Note that although an alias/range variable must be declared for the dervied table (otherwise SQL
will throw an error), it never makes sense to actually use it in the query.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
