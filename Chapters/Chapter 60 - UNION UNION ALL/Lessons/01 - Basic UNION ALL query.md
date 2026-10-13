---
lesson_id: C60-L01
chapter: 60
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C60-L01: Basic UNION ALL query

## Textbook excerpt

Chapter 60: UNION / UNION ALL
Introduction
UNION keyword in SQL is used to combine to SELECT statement results with out any duplicate.
In order to use UNION and combine results both SELECT statement should have same number of
column with same data type in same order, but the length of column can be different.


Syntax
   • SELECT column_1 [, column_2 ] FROM table_1 [, table_2 ] [WHERE condition]
     UNION | UNION ALL
     SELECT column_1 [, column_2 ] FROM table_1 [, table_2 ] [WHERE condition]


Remarks
UNION and UNION ALL clauses combine the result-set of two or more identically structured SELECT
statements into a single result / table.

Both the column count and column types for each query have to match in order for a UNION / UNION
ALL to work.


The difference between a UNION and a UNION ALL query is that the UNION clause will remove any
duplicate rows in the result where the UNION ALL will not.

This distinct removal of records can significantly slow queries even if there are no distinct rows to
be removed because of this if you know there wont be any duplicates (or don't care) always
default to UNION ALL for a more optimised query.


Examples
Basic UNION ALL query

 CREATE TABLE HR_EMPLOYEES
 (
     PersonID int,
     LastName VARCHAR(30),
     FirstName VARCHAR(30),
     Position VARCHAR(30)
 );

 CREATE TABLE FINANCE_EMPLOYEES
 (
     PersonID INT,
     LastName VARCHAR(30),
     FirstName VARCHAR(30),
     Position VARCHAR(30)




 );


Let's say we want to extract the names of all the managers from our departments.

Using a UNION we can get all the employees from both HR and Finance departments, which hold
the position of a manager

 SELECT
      FirstName, LastName
 FROM
      HR_EMPLOYEES
 WHERE
      Position = 'manager'
 UNION ALL
 SELECT
      FirstName, LastName
 FROM
      FINANCE_EMPLOYEES
 WHERE
      Position = 'manager'


The UNION statement removes duplicate rows from the query results. Since it is possible to have
people having the same Name and position in both departments we are using UNION ALL, in order
not to remove duplicates.

If you want to use an alias for each output column, you can just put them in the first select
statement, as follows:

 SELECT
      FirstName as 'First Name', LastName as 'Last Name'
 FROM
      HR_EMPLOYEES
 WHERE
      Position = 'manager'
 UNION ALL
 SELECT
      FirstName, LastName
 FROM
      FINANCE_EMPLOYEES
 WHERE
      Position = 'manager'

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
