---
lesson_id: C32-L08
chapter: 32
lesson: 8
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L08: Rebuild index

## Textbook excerpt

Rebuild index

Over the course of time B-Tree indexes may become fragmented because of
updating/deleting/inserting data. In SQLServer terminology we can have internal (index page
which is half empty ) and external (logical page order doesn't correspond physical order).
Rebuilding index is very similar to dropping and re-creating it.

We can re-build an index with

 ALTER INDEX index_name REBUILD;


By default rebuilding index is offline operation which locks the table and prevents DML against it ,
but many RDBMS allow online rebuilding. Also, some DB vendors offer alternatives to index
rebuilding such as REORGANIZE (SQLServer) or COALESCE/SHRINK SPACE(Oracle).

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
