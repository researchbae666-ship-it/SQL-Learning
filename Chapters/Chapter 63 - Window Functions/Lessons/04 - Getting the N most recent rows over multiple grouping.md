---
lesson_id: C63-L04
chapter: 63
lesson: 4
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C63-L04: Getting the N most recent rows over multiple grouping

## Textbook excerpt

Getting the N most recent rows over multiple grouping

Given this data

 User_ID      Completion_Date

 1            2016-07-20

 1            2016-07-21

 2            2016-07-20

 2            2016-07-21

 2            2016-07-22

 ;with CTE as
 (SELECT *,
         ROW_NUMBER() OVER (PARTITION BY User_ID
                            ORDER BY Completion_Date DESC) Row_Num
 FROM    Data)
 SELECT * FORM CTE WHERE Row_Num <= n


Using n=1, you'll get the one most recent row per user_id:

 User_ID      Completion_Date     Row_Num

 1            2016-07-21          1

 2            2016-07-22          1

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
