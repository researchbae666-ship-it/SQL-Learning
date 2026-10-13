---
lesson_id: C36-L03
chapter: 36
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C36-L03: Match by range or set

## Textbook excerpt

Match by range or set

Match any single character within the specified range (e.g.: [a-f]) or set (e.g.: [abcdef]).

This range pattern would match "gary" but not "mary":

 SELECT * FROM Employees WHERE FName LIKE '[a-g]ary'


This set pattern would match "mary" but not "gary":





 SELECT * FROM Employees WHERE Fname LIKE '[lmnop]ary'


The range or set can also be negated by appending the ^ caret before the range or set:

This range pattern would not match "gary" but will match "mary":

 SELECT * FROM Employees WHERE FName LIKE '[^a-g]ary'


This set pattern would not match "mary" but will match"gary":

 SELECT * FROM Employees WHERE Fname LIKE '[^lmnop]ary'

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
