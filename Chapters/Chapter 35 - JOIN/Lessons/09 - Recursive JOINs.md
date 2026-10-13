---
lesson_id: C35-L09
chapter: 35
lesson: 9
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L09: Recursive JOINs

## Textbook excerpt

Recursive JOINs

Recursive joins are often used to obtain parent-child data. In SQL, they are implemented with
recursive common table expressions, for example:

 WITH RECURSIVE MyDescendants AS (
     SELECT Name
     FROM People
     WHERE Name = 'John Doe'

     UNION ALL

     SELECT People.Name
     FROM People
     JOIN MyDescendants ON People.Name = MyDescendants.Parent
 )
 SELECT * FROM MyDescendants;

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
