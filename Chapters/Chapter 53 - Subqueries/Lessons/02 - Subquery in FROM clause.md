---
lesson_id: C53-L02
chapter: 53
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C53-L02: Subquery in FROM clause

## Textbook excerpt

Subquery in FROM clause

A subquery in a FROM clause acts similarly to a temporary table that is generated during the
execution of a query and lost afterwards.

 SELECT Managers.Id, Employees.Salary
 FROM (
   SELECT Id
   FROM Employees
   WHERE ManagerId IS NULL
 ) AS Managers
 JOIN Employees ON Managers.Id = Employees.Id

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
