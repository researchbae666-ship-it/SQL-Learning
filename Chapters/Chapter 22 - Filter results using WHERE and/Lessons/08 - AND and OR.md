---
lesson_id: C22-L08
chapter: 22
lesson: 8
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L08: AND and OR

## Textbook excerpt

AND and OR

You can also combine several operators together to create more complex WHERE conditions. The
following examples use the Employees table:

 Id   FName     LName    PhoneNumber     ManagerId   DepartmentId    Salary   Hire_date
 CreatedDate   ModifiedDate
 1    James     Smith    1234567890      NULL        1               1000     01-01-2002       01-01-
 2002    01-01-2002
 2    John      Johnson 2468101214       1           1               400      23-03-2005       23-03-
 2005    01-01-2002
 3    Michael   Williams 1357911131      1           2               600      12-05-2009       12-05-
 2009    NULL
 4    Johnathon Smith    1212121212      2           1               500      24-07-2016       24-07-
 2016    01-01-2002



AND

 SELECT * FROM Employees WHERE DepartmentId = 1 AND ManagerId = 1


Will return:

 Id   FName     LName    PhoneNumber     ManagerId   DepartmentId    Salary   Hire_date
 CreatedDate   ModifiedDate
 2    John      Johnson 2468101214       1           1               400      23-03-2005       23-03-
 2005    01-01-2002



OR


 SELECT * FROM Employees WHERE DepartmentId = 2 OR ManagerId = 2


Will return:

 Id   FName     LName    PhoneNumber      ManagerId   DepartmentId   Salary   Hire_date
 CreatedDate   ModifiedDate
 3    Michael   Williams 1357911131       1           2              600      12-05-2009   12-05-
 2009    NULL
 4    Johnathon Smith    1212121212       2           1              500      24-07-2016   24-07-
 2016    01-01-2002

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
