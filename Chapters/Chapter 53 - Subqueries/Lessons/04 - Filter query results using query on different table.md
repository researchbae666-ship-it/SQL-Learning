---
lesson_id: C53-L04
chapter: 53
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C53-L04: Filter query results using query on different table

## Textbook excerpt

Filter query results using query on different table

This query selects all employees not on the Supervisors table.

 SELECT *
 FROM Employees
 WHERE EmployeeID not in (SELECT EmployeeID
                             FROM Supervisors)


The same results can be achieved using a LEFT JOIN.

 SELECT *
 FROM Employees AS e
 LEFT JOIN Supervisors AS s ON s.EmployeeID=e.EmployeeID
 WHERE s.EmployeeID is NULL

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
