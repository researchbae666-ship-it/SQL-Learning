---
lesson_id: C45-L13
chapter: 45
lesson: 13
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L13: Selecting with Aggregate functions

## Textbook excerpt

Selecting with Aggregate functions


Average
The AVG() aggregate function will return the average of values selected.

 SELECT AVG(Salary) FROM Employees


Aggregate functions can also be combined with the where clause.

 SELECT AVG(Salary) FROM Employees where DepartmentId = 1


Aggregate functions can also be combined with group by clause.

If employee is categorized with multiple department and we want to find avg salary for every
department then we can use following query.

 SELECT AVG(Salary) FROM Employees GROUP BY DepartmentId





Minimum
The MIN() aggregate function will return the minimum of values selected.

 SELECT MIN(Salary) FROM Employees




Maximum
The MAX() aggregate function will return the maximum of values selected.

 SELECT MAX(Salary) FROM Employees




Count
The COUNT() aggregate function will return the count of values selected.

 SELECT Count(*) FROM Employees


It can also be combined with where conditions to get the count of rows that satisfy specific
conditions.

 SELECT Count(*) FROM Employees where ManagerId IS NOT NULL


Specific columns can also be specified to get the number of values in the column. Note that NULL
values are not counted.

 Select Count(ManagerId) from Employees


Count can also be combined with the distinct keyword for a distinct count.

 Select Count(DISTINCT DepartmentId) from Employees




Sum
The SUM() aggregate function returns the sum of the values selected for all rows.

 SELECT SUM(Salary) FROM Employees

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
