---
lesson_id: C53-L05
chapter: 53
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C53-L05: Correlated Subqueries

## Textbook excerpt

Correlated Subqueries

Correlated (also known as Synchronized or Coordinated) Subqueries are nested queries that
make references to the current row of their outer query:

 SELECT EmployeeId
     FROM Employee AS eOuter
     WHERE Salary > (
        SELECT AVG(Salary)
        FROM Employee eInner
        WHERE eInner.DepartmentId = eOuter.DepartmentId
     )


Subquery SELECT AVG(Salary) ... is correlated because it refers to Employee row eOuter from its
outer query.

Read Subqueries online: https://riptutorial.com/sql/topic/1606/subqueries

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
