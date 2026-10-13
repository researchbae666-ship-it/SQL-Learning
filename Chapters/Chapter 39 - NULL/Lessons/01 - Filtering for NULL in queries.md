---
lesson_id: C39-L01
chapter: 39
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C39-L01: Filtering for NULL in queries

## Textbook excerpt

Chapter 39: NULL
Introduction
NULL in SQL, as well as programming in general, means literally "nothing". In SQL, it is easier to
understand as "the absence of any value".

It is important to distinguish it from seemingly empty values, such as the empty string '' or the
number 0, neither of which are actually NULL.

It is also important to be careful not to enclose NULL in quotes, like 'NULL', which is allowed in
columns that accept text, but is not NULL and can cause errors and incorrect data sets.


Examples
Filtering for NULL in queries

The syntax for filtering for NULL (i.e. the absence of a value) in WHERE blocks is slightly different than
filtering for specific values.

 SELECT * FROM Employees WHERE ManagerId IS NULL ;
 SELECT * FROM Employees WHERE ManagerId IS NOT NULL ;


Note that because NULL is not equal to anything, not even to itself, using equality operators = NULL
or <> NULL (or != NULL) will always yield the truth value of UNKNOWN which will be rejected by WHERE.

WHERE filters all rows that the condition is FALSE or UKNOWN and keeps only rows that the condition is
TRUE.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
