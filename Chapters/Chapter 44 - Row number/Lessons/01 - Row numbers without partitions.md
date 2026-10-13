---
lesson_id: C44-L01
chapter: 44
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C44-L01: Row numbers without partitions

## Textbook excerpt

Chapter 44: Row number
Syntax
   • ROW_NUMBER ( )
   • OVER ( [ PARTITION BY value_expression , ... [ n ] ] order_by_clause )


Examples
Row numbers without partitions

Include a row number according to the order specified.

 SELECT
   ROW_NUMBER() OVER(ORDER BY Fname ASC) AS RowNumber,
   Fname,
   LName
 FROM Employees

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
