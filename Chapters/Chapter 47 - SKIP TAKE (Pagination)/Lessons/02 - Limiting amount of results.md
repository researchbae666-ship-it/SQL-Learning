---
lesson_id: C47-L02
chapter: 47
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C47-L02: Limiting amount of results

## Textbook excerpt

Limiting amount of results

ISO/ANSI SQL:

 SELECT * FROM TableName FETCH FIRST 20 ROWS ONLY;


MySQL; PostgreSQL; SQLite:

 SELECT * FROM TableName LIMIT 20;


Oracle:



 SELECT Id,
    Col1
 FROM (SELECT Id,
            Col1,
            row_number() over (order by Id) RowNumber
       FROM TableName)
 WHERE RowNumber <= 20


SQL Server:

 SELECT TOP 20 *
 FROM dbo.[Sale]

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
