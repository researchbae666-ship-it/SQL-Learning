---
lesson_id: C18-L01
chapter: 18
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C18-L01: Select dataset except where values are in this other dataset

## Textbook excerpt

Chapter 18: EXCEPT
Remarks
EXCEPT returns any distinct values from the dataset to the left of the EXCEPT operator that are not
also returned from the right dataset.


Examples
Select dataset except where values are in this other dataset

 --dataset schemas must be identical
 SELECT 'Data1' as 'Column' UNION ALL
 SELECT 'Data2' as 'Column' UNION ALL
 SELECT 'Data3' as 'Column' UNION ALL
 SELECT 'Data4' as 'Column' UNION ALL
 SELECT 'Data5' as 'Column'
 EXCEPT
 SELECT 'Data3' as 'Column'
 --Returns Data1, Data2, Data4, and Data5


Read EXCEPT online: https://riptutorial.com/sql/topic/4082/except

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
