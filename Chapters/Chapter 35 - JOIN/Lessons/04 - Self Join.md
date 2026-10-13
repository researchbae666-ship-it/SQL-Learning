---
lesson_id: C35-L04
chapter: 35
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L04: Self Join

## Textbook excerpt

Self Join

A table may be joined to itself, with different rows matching each other by some condition. In this
use case, aliases must be used in order to distinguish the two occurrences of the table.

In the below example, for each Employee in the example database Employees table, a record is
returned containing the employee's first name together with the corresponding first name of the
employee's manager. Since managers are also employees, the table is joined with itself:

 SELECT
      e.FName AS "Employee",
      m.FName AS "Manager"
 FROM
      Employees e
 JOIN
      Employees m
      ON e.ManagerId = m.Id


This query will return the following data:

 Employee       Manager

 John           James

 Michael        James

 Johnathon      John



So how does this work?
The original table contains these records:

 Id   FName         LName      PhoneNumber      ManagerId     DepartmentId      Salary   HireDate

                                                                                         01-01-
 1    James         Smith      1234567890       NULL          1                 1000
                                                                                         2002

                                                                                         23-03-
 2    John          Johnson    2468101214       1             1                 400
                                                                                         2005

                                                                                         12-05-
 3    Michael       Williams   1357911131       1             2                 600
                                                                                         2009

                                                                                         24-07-
 4    Johnathon     Smith      1212121212       2             1                 500
                                                                                         2016

The first action is to create a Cartesian product of all records in the tables used in the FROM



clause. In this case it's the Employees table twice, so the intermediate table will look like this (I've
removed any fields not used in this example):

 e.Id   e.FName       e.ManagerId     m.Id    m.FName       m.ManagerId

 1      James         NULL            1       James         NULL

 1      James         NULL            2       John          1

 1      James         NULL            3       Michael       1

 1      James         NULL            4       Johnathon     2

 2      John          1               1       James         NULL

 2      John          1               2       John          1

 2      John          1               3       Michael       1

 2      John          1               4       Johnathon     2

 3      Michael       1               1       James         NULL

 3      Michael       1               2       John          1

 3      Michael       1               3       Michael       1

 3      Michael       1               4       Johnathon     2

 4      Johnathon     2               1       James         NULL

 4      Johnathon     2               2       John          1

 4      Johnathon     2               3       Michael       1

 4      Johnathon     2               4       Johnathon     2

The next action is to only keep the records that meet the JOIN criteria, so any records where the
aliased e table ManagerId equals the aliased m table Id:

 e.Id   e.FName       e.ManagerId     m.Id    m.FName      m.ManagerId

 2      John          1               1       James        NULL

 3      Michael       1               1       James        NULL

 4      Johnathon     2               2       John         1

Then, each expression used within the SELECT clause is evaluated to return this table:



 e.FName       m.FName

 John          James

 Michael       James

 Johnathon     John

Finally, column names e.FName and m.FName are replaced by their alias column names, assigned
with the AS operator:

 Employee      Manager

 John          James

 Michael       James

 Johnathon     John

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
