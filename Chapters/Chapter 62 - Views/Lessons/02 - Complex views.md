---
lesson_id: C62-L02
chapter: 62
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C62-L02: Complex views

## Textbook excerpt

Complex views

A view can be a really complex query(aggregations, joins, subqueries, etc). Just be sure you add
column names for everything you select:

 Create VIEW dept_income AS
 SELECT d.Name as DepartmentName, sum(e.salary) as TotalSalary
 FROM Employees e
 JOIN Departments d on e.DepartmentId = d.id
 GROUP BY d.Name;


Now you can select from it as from any table:

 SELECT *
 FROM dept_income;



 DepartmentName            TotalSalary

 HR                        1900

 Sales                     600

Read Views online: https://riptutorial.com/sql/topic/766/views

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
