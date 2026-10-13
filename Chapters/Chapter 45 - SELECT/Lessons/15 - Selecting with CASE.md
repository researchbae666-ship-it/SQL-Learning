---
lesson_id: C45-L15
chapter: 45
lesson: 15
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L15: Selecting with CASE

## Textbook excerpt

Selecting with CASE

When results need to have some logic applied 'on the fly' one can use CASE statement to
implement it.

 SELECT CASE WHEN Col1 < 50 THEN 'under' ELSE 'over' END threshold
 FROM TableName


also can be chained

 SELECT
     CASE WHEN Col1 < 50 THEN 'under'
          WHEN Col1 > 50 AND Col1 <100 THEN 'between'
          ELSE 'over'
     END threshold
 FROM TableName


one also can have CASE inside another CASE statement

 SELECT
     CASE WHEN Col1 < 50 THEN 'under'
          ELSE
             CASE WHEN Col1 > 50 AND Col1 <100 THEN Col1
             ELSE 'over' END
     END threshold
 FROM TableName

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
