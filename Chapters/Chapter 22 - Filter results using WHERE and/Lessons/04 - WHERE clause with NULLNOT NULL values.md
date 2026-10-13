---
lesson_id: C22-L04
chapter: 22
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L04: WHERE clause with NULL/NOT NULL values

## Textbook excerpt

WHERE clause with NULL/NOT NULL values

 SELECT *
 FROM Employees
 WHERE ManagerId IS NULL


This statement will return all Employee records where the value of the ManagerId column is NULL.

The result will be:

 Id      FName    LName     PhoneNumber     ManagerId    DepartmentId
 1       James    Smith     1234567890      NULL         1



 SELECT *
 FROM Employees
 WHERE ManagerId IS NOT NULL


This statement will return all Employee records where the value of the ManagerId is not NULL.

The result will be:

 Id      FName        LName      PhoneNumber    ManagerId    DepartmentId
 2       John         Johnson    2468101214     1            1
 3       Michael      Williams   1357911131     1            2
 4       Johnathon    Smith      1212121212     2            1



Note: The same query will not return results if you change the WHERE clause to WHERE ManagerId
= NULL or WHERE ManagerId <> NULL.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
