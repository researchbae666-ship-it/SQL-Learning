# Chapter 44: Row number

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

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



Row numbers with partitions

Uses a partition criteria to group the row numbering according to it.

 SELECT
   ROW_NUMBER() OVER(PARTITION BY DepartmentId ORDER BY DepartmentId ASC) AS RowNumber,
   DepartmentId, Fname, LName
 FROM Employees



Delete All But Last Record (1 to Many Table)

 WITH cte AS (
   SELECT ProjectID,
          ROW_NUMBER() OVER (PARTITION BY ProjectID ORDER BY InsertDate DESC) AS rn
   FROM ProjectNotes
 )
 DELETE FROM cte WHERE rn > 1;


Read Row number online: https://riptutorial.com/sql/topic/1977/row-number
