# Chapter 23: Finding Duplicates on a Column

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

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
