---
lesson_id: C61-L05
chapter: 61
lesson: 5
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C61-L05: Capturing Updated records

## Textbook excerpt

Capturing Updated records

Sometimes one wants to capture the records that have just been updated.

 CREATE TABLE #TempUpdated(ID INT)

 Update TableName SET Col1 = 42
     OUTPUT inserted.ID INTO #TempUpdated
     WHERE Id > 50


Read UPDATE online: https://riptutorial.com/sql/topic/321/update

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
