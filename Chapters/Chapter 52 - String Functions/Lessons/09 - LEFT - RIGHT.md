---
lesson_id: C52-L09
chapter: 52
lesson: 9
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C52-L09: LEFT - RIGHT

## Textbook excerpt

LEFT - RIGHT

Syntax is:
LEFT ( string-expression , integer )
RIGHT ( string-expression , integer )

 SELECT LEFT('Hello',2) --return He
 SELECT RIGHT('Hello',2) --return lo


Oracle SQL doesn't have LEFT and RIGHT functions. They can be emulated with SUBSTR and
LENGTH.
SUBSTR ( string-expression, 1, integer )



SUBSTR ( string-expression, length(string-expression)-integer+1, integer)

 SELECT SUBSTR('Hello',1,2) --return He
 SELECT SUBSTR('Hello',LENGTH('Hello')-2+1,2) --return lo

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
