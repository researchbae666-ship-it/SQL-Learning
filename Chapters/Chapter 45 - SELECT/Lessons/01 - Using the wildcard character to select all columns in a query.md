---
lesson_id: C45-L01
chapter: 45
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L01: Using the wildcard character to select all columns in a query.

## Textbook excerpt

Chapter 45: SELECT
Introduction
The SELECT statement is at the heart of most SQL queries. It defines what result set should be
returned by the query, and is almost always used in conjunction with the FROM clause, which
defines what part(s) of the database should be queried.


Syntax
   • SELECT [DISTINCT] [column1] [, [column2] ... ]
     FROM [table]
     [ WHERE condition ]
     [ GROUP BY [column1] [, [column2] ... ]

      [ HAVING [column1] [, [column2] ... ]

      [ ORDER BY ASC | DESC ]


Remarks
SELECT determines which columns' data to return and in which order FROM a given table
(given that they match the other requirements in your query specifically - where and having filters
and joins).

 SELECT Name, SerialNumber
 FROM ArmyInfo


will only return results from the Name and Serial Number columns, but not from the column called
Rank, for example


 SELECT *
 FROM ArmyInfo


indicates that all columns will be returned. However, please note that it is poor practice to SELECT *
as you are literally returning all columns of a table.


Examples
Using the wildcard character to select all columns in a query.

Consider a database with the following two tables.

Employees table:




 Id   FName       LName       DeptId

 1    James       Smith       3

 2    John        Johnson     4

Departments table:

 Id   Name

 1    Sales

 2    Marketing

 3    Finance

 4    IT

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
