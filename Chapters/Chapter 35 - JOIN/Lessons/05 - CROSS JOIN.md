---
lesson_id: C35-L05
chapter: 35
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L05: CROSS JOIN

## Textbook excerpt

CROSS JOIN

Cross join does a Cartesian product of the two members, A Cartesian product means each row of
one table is combined with each row of the second table in the join. For example, if TABLEA has 20
rows and TABLEB has 20 rows, the result would be 20*20 = 400 output rows.

Using example database

 SELECT d.Name, e.FName
 FROM   Departments d
 CROSS JOIN Employees e;


Which returns:

 d.Name      e.FName

 HR          James

 HR          John

 HR          Michael

 HR          Johnathon

 Sales       James

 Sales       John

 Sales       Michael

 Sales       Johnathon


 d.Name      e.FName

 Tech        James

 Tech        John

 Tech        Michael

 Tech        Johnathon

It is recommended to write an explicit CROSS JOIN if you want to do a cartesian join, to highlight
that this is what you want.

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
