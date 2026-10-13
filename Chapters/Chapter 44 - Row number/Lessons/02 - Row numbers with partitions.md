---
lesson_id: C44-L02
chapter: 44
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C44-L02: Row numbers with partitions

## Textbook excerpt

Row numbers with partitions

Uses a partition criteria to group the row numbering according to it.

 SELECT
   ROW_NUMBER() OVER(PARTITION BY DepartmentId ORDER BY DepartmentId ASC) AS RowNumber,
   DepartmentId, Fname, LName
 FROM Employees

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
