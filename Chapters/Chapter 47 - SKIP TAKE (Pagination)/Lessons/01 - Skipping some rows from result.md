---
lesson_id: C47-L01
chapter: 47
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C47-L01: Skipping some rows from result

## Textbook excerpt

Chapter 47: SKIP TAKE (Pagination)
Examples
Skipping some rows from result

ISO/ANSI SQL:

 SELECT Id, Col1
 FROM TableName
 ORDER BY Id
 OFFSET 20 ROWS


MySQL:

 SELECT * FROM TableName LIMIT 20, 42424242424242;
 -- skips 20 for take use very large number that is more than rows in table


Oracle:

 SELECT Id,
    Col1
 FROM (SELECT Id,
            Col1,
            row_number() over (order by Id) RowNumber
       FROM TableName)
 WHERE RowNumber > 20


PostgreSQL:

 SELECT * FROM TableName OFFSET 20;


SQLite:

 SELECT * FROM TableName LIMIT -1 OFFSET 20;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
