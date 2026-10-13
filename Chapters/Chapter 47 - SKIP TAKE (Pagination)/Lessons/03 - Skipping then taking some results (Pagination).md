---
lesson_id: C47-L03
chapter: 47
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C47-L03: Skipping then taking some results (Pagination)

## Textbook excerpt

Skipping then taking some results (Pagination)

ISO/ANSI SQL:

 SELECT Id, Col1
 FROM TableName
 ORDER BY Id
 OFFSET 20 ROWS FETCH NEXT 20 ROWS ONLY;


MySQL:

 SELECT * FROM TableName LIMIT 20, 20; -- offset, limit


Oracle; SQL Server:

 SELECT Id,
    Col1
  FROM (SELECT Id,
            Col1,
            row_number() over (order by Id) RowNumber
       FROM TableName)
 WHERE RowNumber BETWEEN 21 AND 40


PostgreSQL; SQLite:

 SELECT * FROM TableName LIMIT 20 OFFSET 20;


Read SKIP TAKE (Pagination) online: https://riptutorial.com/sql/topic/2927/skip-take--pagination-

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
