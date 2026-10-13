---
lesson_id: C52-L13
chapter: 52
lesson: 13
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C52-L13: Replace function in sql Select and Update query

## Textbook excerpt

Replace function in sql Select and Update query

The Replace function in SQL is used to update the content of a string. The function call is
REPLACE( ) for MySQL, Oracle, and SQL Server.

The syntax of the Replace function is:

 REPLACE (str, find, repl)


The following example replaces occurrences of South with Southern in Employees table:

 FirstName      Address

 James          South New York

 John           South Boston

 Michael        South San Diego



Select Statement :

If we apply the following Replace function:

 SELECT
     FirstName,
     REPLACE (Address, 'South', 'Southern') Address
 FROM Employees
 ORDER BY FirstName


Result:

 FirstName      Address

 James          Southern New York

 John           Southern Boston

 Michael        Southern San Diego

Update Statement :

We can use a replace function to make permanent changes in our table through following
approach.

 Update Employees
 Set city = (Address, 'South', 'Southern');


A more common approach is to use this in conjunction with a WHERE clause like this:

 Update Employees
 Set Address = (Address, 'South', 'Southern')
 Where Address LIKE 'South%';

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
