---
lesson_id: C53-L01
chapter: 53
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C53-L01: Subquery in WHERE clause

## Textbook excerpt

Chapter 53: Subqueries
Remarks
Subqueries can appear in different clauses of an outer query, or in the set operation.

They must be enclosed in parentheses (). If the result of the subquery is compared to something
else, the number of columns must match. Table aliases are required for subqueries in the FROM
clause to name the temporary table.


Examples
Subquery in WHERE clause

Use a subquery to filter the result set. For example this will return all employees with a salary
equal to the highest paid employee.

 SELECT *
 FROM Employees
 WHERE Salary = (SELECT MAX(Salary) FROM Employees)

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
