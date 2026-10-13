---
lesson_id: C44-L03
chapter: 44
lesson: 3
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C44-L03: Delete All But Last Record (1 to Many Table)

## Textbook excerpt

Delete All But Last Record (1 to Many Table)

 WITH cte AS (
   SELECT ProjectID,
          ROW_NUMBER() OVER (PARTITION BY ProjectID ORDER BY InsertDate DESC) AS rn
   FROM ProjectNotes
 )
 DELETE FROM cte WHERE rn > 1;


Read Row number online: https://riptutorial.com/sql/topic/1977/row-number

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
