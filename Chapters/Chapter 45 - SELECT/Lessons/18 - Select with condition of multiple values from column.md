---
lesson_id: C45-L18
chapter: 45
lesson: 18
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C45-L18: Select with condition of multiple values from column

## Textbook excerpt

Select with condition of multiple values from column

 SELECT * FROM Cars    WHERE status IN ( 'Waiting', 'Working' )


This is semantically equivalent to

 SELECT * FROM Cars    WHERE ( status = 'Waiting' OR status = 'Working' )


i.e. value IN ( <value list> ) is a shorthand for disjunction (logical OR).

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
