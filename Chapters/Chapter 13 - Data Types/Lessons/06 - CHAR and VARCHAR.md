---
lesson_id: C13-L06
chapter: 13
lesson: 6
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C13-L06: CHAR and VARCHAR

## Textbook excerpt

CHAR and VARCHAR

String data types of either fixed length or variable length.

Syntax:

 CHAR [ ( n_chars ) ]
 VARCHAR [ ( n_chars ) ]


Examples:

 SELECT CAST('ABC' AS CHAR(10)) -- 'ABC       ' (padded with spaces on the right)
 SELECT CAST('ABC' AS VARCHAR(10)) -- 'ABC' (no padding due to variable character)
 SELECT CAST('ABCDEFGHIJKLMNOPQRSTUVWXYZ' AS CHAR(10)) -- 'ABCDEFGHIJ' (truncated to 10
 characters)

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
