---
lesson_id: C22-L03
chapter: 22
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L03: Use LIKE to find matching strings and substrings

## Textbook excerpt

Use LIKE to find matching strings and substrings

See full documentation on LIKE operator.

This example uses the Employees Table from the Example Databases.




 SELECT *
 FROM Employees
 WHERE FName LIKE 'John'


This query will only return Employee #1 whose first name matches 'John' exactly.

 SELECT *
 FROM Employees
 WHERE FName like 'John%'


Adding % allows you to search for a substring:

      • John% - will return any Employee whose name begins with 'John', followed by any amount of
        characters
      • %John - will return any Employee whose name ends with 'John', proceeded by any amount of
        characters
      • %John% - will return any Employee whose name contains 'John' anywhere within the value

In this case, the query will return Employee #2 whose name is 'John' as well as Employee #4
whose name is 'Johnathon'.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
