---
lesson_id: C40-L04
chapter: 40
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C40-L04: Order by Alias

## Textbook excerpt

Order by Alias

Due to logical query processing order, alias can be used in order by.

 SELECT DisplayName, JoinDate as jd, Reputation as rep
 FROM Users
 ORDER BY jd, rep


And can use relative order of the columns in the select statement .Consider the same example as
above and instead of using alias use the relative order like for display name it is 1 , for Jd it is 2
and so on

 SELECT DisplayName, JoinDate as jd, Reputation as rep
 FROM Users
 ORDER BY 2, 3

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
