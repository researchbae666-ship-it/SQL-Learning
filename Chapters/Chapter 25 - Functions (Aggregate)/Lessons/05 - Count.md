---
lesson_id: C25-L05
chapter: 25
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C25-L05: Count

## Textbook excerpt

Count




You can count the number of rows:

 SELECT count(*) TotalRows
 FROM employees;



 TotalRows

 4

Or count the employees per department:

 SELECT DepartmentId, count(*) NumEmployees
 FROM employees
 GROUP BY DepartmentId;



 DepartmentId       NumEmployees

 1                  3

 2                  1

You can count over a column/expression with the effect that will not count the NULL values:

 SELECT count(ManagerId) mgr
 FROM EMPLOYEES;



 mgr

 3

(There is one null value managerID column)

You can also use DISTINCT inside of another function such as COUNT to only find the DISTINCT
members of the set to perform the operation on.

For example:

  SELECT COUNT(ContinentCode) AllCount
  ,      COUNT(DISTINCT ContinentCode) SingleCount
  FROM Countries;


Will return different values. The SingleCount will only Count individual Continents once, while the
AllCount will include duplicates.

 ContinentCode

 OC




 ContinentCode

 EU

 AS

 NA

 NA

 AF

 AF

AllCount: 7 SingleCount: 5

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
