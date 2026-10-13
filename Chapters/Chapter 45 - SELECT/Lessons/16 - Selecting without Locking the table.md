---
lesson_id: C45-L16
chapter: 45
lesson: 16
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L16: Selecting without Locking the table

## Textbook excerpt

Selecting without Locking the table

Sometimes when tables are used mostly (or only) for reads, indexing does not help anymore and
every little bit counts, one might use selects without LOCK to improve performance.


SQL Server

 SELECT * FROM TableName WITH (nolock)



MySQL

 SET SESSION TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;
 SELECT * FROM TableName;
 SET SESSION TRANSACTION ISOLATION LEVEL REPEATABLE READ;



Oracle

 SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;
 SELECT * FROM TableName;




DB2

 SELECT * FROM TableName WITH UR;


where UR stands for "uncommitted read".


If used on table that has record modifications going on might have unpredictable results.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
