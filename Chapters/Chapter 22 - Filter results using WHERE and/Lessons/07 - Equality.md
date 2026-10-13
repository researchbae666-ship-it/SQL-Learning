---
lesson_id: C22-L07
chapter: 22
lesson: 7
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L07: Equality

## Textbook excerpt

Equality

 SELECT * FROM Employees


This statement will return all the rows from the table Employees.

 Id   FName     LName    PhoneNumber      ManagerId    DepartmentId     Salary   Hire_date
 CreatedDate   ModifiedDate
 1    James     Smith    1234567890       NULL         1                1000     01-01-2002     01-01-
 2002    01-01-2002




 2    John      Johnson 2468101214       1           1               400      23-03-2005       23-03-
 2005    01-01-2002
 3    Michael   Williams 1357911131      1           2               600      12-05-2009       12-05-
 2009    NULL
 4    Johnathon Smith    1212121212      2           1               500      24-07-2016       24-07-
 2016    01-01-2002


Using a WHERE at the end of your SELECT statement allows you to limit the returned rows to a
condition. In this case, where there is an exact match using the = sign:

 SELECT * FROM Employees WHERE DepartmentId = 1


Will only return the rows where the DepartmentId is equal to 1:

 Id   FName     LName    PhoneNumber     ManagerId   DepartmentId    Salary   Hire_date
 CreatedDate   ModifiedDate
 1    James     Smith    1234567890      NULL        1               1000     01-01-2002       01-01-
 2002    01-01-2002
 2    John      Johnson 2468101214       1           1               400      23-03-2005       23-03-
 2005    01-01-2002
 4    Johnathon Smith    1212121212      2           1               500      24-07-2016       24-07-
 2016    01-01-2002

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
