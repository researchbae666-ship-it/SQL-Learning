---
lesson_id: C16-L02
chapter: 16
lesson: 2
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C16-L02: Check for existence before dropping

## Textbook excerpt

Check for existence before dropping

MySQL3.19

 DROP TABLE IF EXISTS MyTable;


PostgreSQL8.x

 DROP TABLE IF EXISTS MyTable;


SQL Server2005

 If Exists(Select * From Information_Schema.Tables
           Where Table_Schema = 'dbo'
             And Table_Name = 'MyTable')
   Drop Table dbo.MyTable


SQLite3.0

 DROP TABLE IF EXISTS MyTable;


Read DROP Table online: https://riptutorial.com/sql/topic/1832/drop-table

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
