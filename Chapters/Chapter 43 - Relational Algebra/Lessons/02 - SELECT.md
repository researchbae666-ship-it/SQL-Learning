---
lesson_id: C43-L02
chapter: 43
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C43-L02: SELECT

## Textbook excerpt

SELECT
The select operator returns a subset of the main table.
select < table > where < condition >

For example, examine the expression:

select People where DepartmentID = 2

This can be written as:




This will result in table whose records comprises of all records in the People table where the
DepartmentID value is equal to 2:





Conditions can also be joined to restrict the expression further:

select People where StartYear > 2005 and DepartmentID = 2

will result in the following table:

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
