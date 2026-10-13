---
lesson_id: C35-L01
chapter: 35
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L01: Basic explicit inner join

## Textbook excerpt

Chapter 35: JOIN
Introduction
JOIN is a method of combining (joining) information from two tables. The result is a stitched set of
columns from both tables, defined by the join type (INNER/OUTER/CROSS and
LEFT/RIGHT/FULL, explained below) and join criteria (how rows from both tables relate).

A table may be joined to itself or to any other table. If information from more than two tables needs
to be accessed, multiple joins can be specified in a FROM clause.


Syntax
   • [ { INNER | { { LEFT | RIGHT | FULL } [ OUTER ] } } ] JOIN


Remarks
Joins, as their name suggests, are a way of querying data from several tables in a joint fashion,
with the rows displaying columns taken from more than one table.


Examples
Basic explicit inner join

A basic join (also called "inner join") queries data from two tables, with their relationship defined in
a join clause.

The following example will select employees' first names (FName) from the Employees table and
the name of the department they work for (Name) from the Departments table:

 SELECT Employees.FName, Departments.Name
 FROM   Employees
 JOIN   Departments
 ON Employees.DepartmentId = Departments.Id


This would return the following from the example database:

 Employees.FName           Departments.Name

 James                     HR

 John                      HR

 Richard                   Sales

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
