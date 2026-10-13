---
lesson_id: C40-L01
chapter: 40
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C40-L01: Use ORDER BY with TOP to return the top x rows based on a column's value

## Textbook excerpt

Chapter 40: ORDER BY
Examples
Use ORDER BY with TOP to return the top x rows based on a column's value

In this example, we can use GROUP BY not only determined the sort of the rows returned, but
also what rows are returned, since we're using TOP to limit the result set.

Let's say we want to return the top 5 highest reputation users from an unnamed popular Q&A site.

Without ORDER BY

This query returns the Top 5 rows ordered by the default, which in this case is "Id", the first column
in the table (even though it's not a column shown in the results).

 SELECT TOP 5 DisplayName, Reputation
 FROM Users


returns...

 DisplayName       Reputation

 Community         1

 Geoff Dalgas      12567

 Jarrod Dixon      11739

 Jeff Atwood       37628

 Joel Spolsky      25784

With ORDER BY

 SELECT TOP 5 DisplayName, Reputation
 FROM Users
 ORDER BY Reputation desc


returns...

 DisplayName       Reputation

 JonSkeet          865023

 Darin Dimitrov    661741




 DisplayName       Reputation

 BalusC            650237

 Hans Passant      625870

 Marc Gravell      601636

Remarks

Some versions of SQL (such as MySQL) use a LIMIT clause at the end of a SELECT, instead of TOP
at the beginning, for example:

 SELECT DisplayName, Reputation
 FROM Users
 ORDER BY Reputation DESC
 LIMIT 5

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
