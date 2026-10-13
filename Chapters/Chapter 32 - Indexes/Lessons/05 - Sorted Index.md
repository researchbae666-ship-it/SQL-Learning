---
lesson_id: C32-L05
chapter: 32
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C32-L05: Sorted Index

## Textbook excerpt

Sorted Index

If you use an index that is sorted the way you would retrieve it, the SELECT statement would not do
additional sorting when in retrieval.

 CREATE INDEX ix_scoreboard_score ON scoreboard (score DESC);


When you execute the query

 SELECT * FROM scoreboard ORDER BY score DESC;


The database system would not do additional sorting, since it can do an index-lookup in that order.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
