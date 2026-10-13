---
lesson_id: C35-L02
chapter: 35
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C35-L02: Implicit Join

## Textbook excerpt

Implicit Join

Joins can also be performed by having several tables in the from clause, separated with commas ,
and defining the relationship between them in the where clause. This technique is called an Implicit
Join (since it doesn't actually contain a join clause).

All RDBMSs support it, but the syntax is usually advised against. The reasons why it is a bad idea
to use this syntax are:

   • It is possible to get accidental cross joins which then return incorrect results, especially if you
     have a lot of joins in the query.
   • If you intended a cross join, then it is not clear from the syntax (write out CROSS JOIN
     instead), and someone is likely to change it during maintenance.

The following example will select employee's first names and the name of the departments they
work for:

 SELECT e.FName, d.Name
 FROM   Employee e, Departments d
 WHERE e.DeptartmentId = d.Id


This would return the following from the example database:

 e.FName      d.Name

 James        HR

 John         HR

 Richard      Sales

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
