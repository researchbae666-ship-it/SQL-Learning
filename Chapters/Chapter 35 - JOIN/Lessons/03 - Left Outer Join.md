---
lesson_id: C35-L03
chapter: 35
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L03: Left Outer Join

## Textbook excerpt

Left Outer Join

A Left Outer Join (also known as a Left Join or Outer Join) is a Join that ensures all rows from the
left table are represented; if no matching row from the right table exists, its corresponding fields
are NULL.

The following example will select all departments and the first name of employees that work in that
department. Departments with no employees are still returned in the results, but will have NULL
for the employee name:

 SELECT          Departments.Name, Employees.FName
 FROM            Departments
 LEFT OUTER JOIN Employees
 ON              Departments.Id = Employees.DepartmentId


This would return the following from the example database:





 Departments.Name          Employees.FName

 HR                        James

 HR                        John

 HR                        Johnathon

 Sales                     Michael

 Tech                      NULL



So how does this work?
There are two tables in the FROM clause:

 Id   FName         LName         PhoneNumber   ManagerId   DepartmentId     Salary      HireDate

                                                                                         01-01-
 1    James         Smith         1234567890    NULL        1                1000
                                                                                         2002

                                                                                         23-03-
 2    John          Johnson       2468101214    1           1                400
                                                                                         2005

                                                                                         12-05-
 3    Michael       Williams      1357911131    1           2                600
                                                                                         2009

                                                                                         24-07-
 4    Johnathon     Smith         1212121212    2           1                500
                                                                                         2016

and

 Id   Name

 1    HR

 2    Sales

 3    Tech

First a Cartesian product is created from the two tables giving an intermediate table.
The records that meet the join criteria (Departments.Id = Employees.DepartmentId) are
highlighted in bold; these are passed to the next stage of the query.

As this is a LEFT OUTER JOIN all records are returned from the LEFT side of the join
(Departments), while any records on the RIGHT side are given a NULL marker if they do not
match the join criteria. In the table below this will return Tech with NULL


 Id   Name     Id   FName            LName      PhoneNumber   ManagerId     DepartmentId        Salary   Hire

                                                                                                         01-
 1    HR       1    James            Smith      1234567890    NULL          1                   1000
                                                                                                         200

                                                                                                         23-
 1    HR       2    John             Johnson    2468101214    1             1                   400
                                                                                                         200

                                                                                                         12-
 1    HR       3    Michael          Williams   1357911131    1             2                   600
                                                                                                         200

                                                                                                         24-
 1    HR       4    Johnathon        Smith      1212121212    2             1                   500
                                                                                                         201

                                                                                                         01-
 2    Sales    1    James            Smith      1234567890    NULL          1                   1000
                                                                                                         200

                                                                                                         23-
 2    Sales    2    John             Johnson    2468101214    1             1                   400
                                                                                                         200

                                                                                                         12-
 2    Sales    3    Michael          Williams   1357911131    1             2                   600
                                                                                                         200

                                                                                                         24-
 2    Sales    4    Johnathon        Smith      1212121212    2             1                   500
                                                                                                         201

                                                                                                         01-
 3    Tech     1    James            Smith      1234567890    NULL          1                   1000
                                                                                                         200

                                                                                                         23-
 3    Tech     2    John             Johnson    2468101214    1             1                   400
                                                                                                         200

                                                                                                         12-
 3    Tech     3    Michael          Williams   1357911131    1             2                   600
                                                                                                         200

                                                                                                         24-
 3    Tech     4    Johnathon        Smith      1212121212    2             1                   500
                                                                                                         201

Finally each expression used within the SELECT clause is evaluated to return our final table:

 Departments.Name          Employees.FName

 HR                        James

 HR                        John

 Sales                     Richard

 Tech                      NULL

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
