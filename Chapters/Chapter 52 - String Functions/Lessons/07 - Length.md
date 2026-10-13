---
lesson_id: C52-L07
chapter: 52
lesson: 7
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C52-L07: Length

## Textbook excerpt

Length

SQL Server


The LEN doesn't count the trailing space.

 SELECT LEN('Hello') -- returns 5

 SELECT LEN('Hello '); -- returns 5


The DATALENGTH counts the trailing space.

 SELECT DATALENGTH('Hello') -- returns 5




 SELECT DATALENGTH('Hello '); -- returns 6


It should be noted though, that DATALENGTH returns the length of the underlying byte
representation of the string, which depends, i.a., on the charset used to store the string.

 DECLARE @str varchar(100) = 'Hello ' --varchar is usually an ASCII string, occupying 1 byte
 per char
 SELECT DATALENGTH(@str) -- returns 6

 DECLARE @nstr nvarchar(100) = 'Hello ' --nvarchar is a unicode string, occupying 2 bytes per
 char
 SELECT DATALENGTH(@nstr) -- returns 12


Oracle


Syntax: Length ( char )

Examples:

 SELECT Length('Bible') FROM dual; --Returns 5
 SELECT Length('righteousness') FROM dual; --Returns 13
 SELECT Length(NULL) FROM dual; --Returns NULL


See Also: LengthB, LengthC, Length2, Length4

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
