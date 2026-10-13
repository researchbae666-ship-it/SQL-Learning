---
lesson_id: C45-L08
chapter: 45
lesson: 8
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L08: Selection with sorted Results

## Textbook excerpt

Selection with sorted Results

 SELECT * FROM Employees ORDER BY LName


This statement will return all the columns from the table Employees.

 Id   FName      LName         PhoneNumber

 2    John       Johnson       2468101214

 1    James      Smith         1234567890



 Id   FName      LName      PhoneNumber

 3    Michael    Williams   1357911131

 SELECT * FROM Employees ORDER BY LName DESC


Or

  SELECT * FROM Employees ORDER BY LName ASC


This statement changes the sorting direction.

One may also specify multiple sorting columns. For example:

 SELECT * FROM Employees ORDER BY LName ASC, FName ASC


This example will sort the results first by LName and then, for records that have the same LName, sort
by FName. This will give you a result similar to what you would find in a telephone book.

In order to save retyping the column name in the ORDER BY clause, it is possible to use instead the
column's number. Note that column numbers start from 1.

 SELECT Id, FName, LName, PhoneNumber FROM Employees ORDER BY 3


You may also embed a CASE statement in the ORDER BY clause.

 SELECT Id, FName, LName, PhoneNumber FROM Employees ORDER BY CASE WHEN LName='Jones` THEN 0
 ELSE 1 END ASC


This will sort your results to have all records with the LName of "Jones" at the top.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
