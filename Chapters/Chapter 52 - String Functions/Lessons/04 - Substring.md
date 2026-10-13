---
lesson_id: C52-L04
chapter: 52
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C52-L04: Substring

## Textbook excerpt

Substring

Syntax is: SUBSTRING ( string_expression, start, length ). Note that SQL strings are 1-indexed.

 SELECT SUBSTRING('Hello', 1, 2) --returns 'He'
 SELECT SUBSTRING('Hello', 3, 3) --returns 'llo'


This is often used in conjunction with the LEN() function to get the last n characters of a string of
unknown length.



 DECLARE @str1 VARCHAR(10) = 'Hello', @str2 VARCHAR(10) = 'FooBarBaz';
 SELECT SUBSTRING(@str1, LEN(@str1) - 2, 3) --returns 'llo'
 SELECT SUBSTRING(@str2, LEN(@str2) - 2, 3) --returns 'Baz'

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
