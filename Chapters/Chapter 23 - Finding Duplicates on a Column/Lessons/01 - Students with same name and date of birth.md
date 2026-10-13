---
lesson_id: C23-L01
chapter: 23
lesson: 1
status: planned
sql_target: SQL Server 2012 (compatibility not verified)
---

# C23-L01: Students with same name and date of birth

## Textbook excerpt

Chapter 23: Finding Duplicates on a Column
Subset with Detail
Remarks
   • To select rows with out duplicates change the WHERE clause to "RowCnt = 1"

   • To select one row from each set use Rank() instead of Sum() and change the outer WHERE
     clause to select rows with Rank() = 1


Examples
Students with same name and date of birth

 WITH CTE (StudentId, Fname, LName, DOB, RowCnt)
 as (
 SELECT StudentId, FirstName, LastName, DateOfBirth as DOB, SUM(1) OVER (Partition By
 FirstName, LastName, DateOfBirth) as RowCnt
 FROM tblStudent
 )
 SELECT * from CTE where RowCnt > 1
 ORDER BY DOB, LName


This example uses a Common Table Expression and a Window Function to show all duplicate
rows (on a subset of columns) side by side.

Read Finding Duplicates on a Column Subset with Detail online:
https://riptutorial.com/sql/topic/1585/finding-duplicates-on-a-column-subset-with-detail

## Lesson conversation and assessment

*Pending faithful import of teaching dialogue, submitted SQL, feedback, and grades.*
