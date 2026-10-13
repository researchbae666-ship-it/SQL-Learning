---
lesson_id: C45-L03
chapter: 45
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L03: Dot notation

## Textbook excerpt

Dot notation

To select all values from a specific table, the wildcard character can be applied to the table with
dot notation.

Consider the following query:

 SELECT
     Employees.*,
     Departments.Name




 FROM
       Employees
 JOIN
       Departments
       ON Departments.Id = Employees.DeptId


This will return a data set with all fields on the Employee table, followed by just the Name field in the
Departments table:


 Id     FName      LName     DeptId    Name

 1      James      Smith     3         Finance

 2      John       Johnson   4         IT

Warnings Against Use

It is generally advised that using * is avoided in production code where possible, as it can cause a
number of potential problems including:

     1. Excess IO, network load, memory use, and so on, due to the database engine reading data
        that is not needed and transmitting it to the front-end code. This is particularly a concern
        where there might be large fields such as those used to store long notes or attached files.
     2. Further excess IO load if the database needs to spool internal results to disk as part of the
        processing for a query more complex than SELECT <columns> FROM <table>.
     3. Extra processing (and/or even more IO) if some of the unneeded columns are:
            • computed columns in databases that support them
            • in the case of selecting from a view, columns from a table/view that the query optimiser
               could otherwise optimise out
     4. The potential for unexpected errors if columns are added to tables and views later that
        results ambiguous column names. For example SELECT * FROM orders JOIN people ON
        people.id = orders.personid ORDER BY displayname - if a column column called displayname is
        added to the orders table to allow users to give their orders meaningful names for future
        reference then the column name will appear twice in the output so the ORDER BY clause will be
        ambiguous which may cause errors ("ambiguous column name" in recent MS SQL Server
        versions), and if not in this example your application code might start displaying the order
        name where the person name is intended because the new column is the first of that name
        returned, and so on.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
