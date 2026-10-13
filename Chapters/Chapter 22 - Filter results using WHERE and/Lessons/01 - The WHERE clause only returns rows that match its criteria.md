---
lesson_id: C22-L01
chapter: 22
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C22-L01: The WHERE clause only returns rows that match its criteria

## Textbook excerpt

Chapter 22: Filter results using WHERE and
HAVING
Syntax
   • SELECT column_name
     FROM table_name
     WHERE column_name operator value
   • SELECT column_name, aggregate_function(column_name)
     FROM table_name
     GROUP BY column_name
     HAVING aggregate_function(column_name) operator value


Examples
The WHERE clause only returns rows that match its criteria

Steam has a games under $10 section of their store page. Somewhere deep in the heart of their
systems, there's probably a query that looks something like:

 SELECT *
 FROM Items
 WHERE Price < 10

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
