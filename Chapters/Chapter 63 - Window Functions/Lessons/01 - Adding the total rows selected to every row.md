---
lesson_id: C63-L01
chapter: 63
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C63-L01: Adding the total rows selected to every row

## Textbook excerpt

Chapter 63: Window Functions
Examples
Adding the total rows selected to every row

 SELECT your_columns, COUNT(*) OVER() as Ttl_Rows FROM your_data_set



 id   name        Ttl_Rows

 1    example     5

 2    foo         5

 3    bar         5

 4    baz         5

 5    quux        5

Instead of using two queries to get a count then the line, you can use an aggregate as a window
function and use the full result set as the window.
This can be used as a base for further calculation without the complexity of extra self joins.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
