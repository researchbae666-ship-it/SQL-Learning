# Chapter 16: DROP Table

> Source: *SQL*, unofficial Stack Overflow Documentation ebook compiled by Steve Nouri; content credited to Stack Overflow Documentation contributors and licensed CC BY-SA as stated in the original PDF. Extracted from the user-provided 221-page PDF. PDF text formatting is normalized; illustrations remain in the original PDF. See the book credits for chapter contributors.

---

Chapter 16: DROP Table
Remarks
DROP TABLE removes the table definition from the schema along with the rows, indexes,
permissions, and triggers.


Examples
Simple drop

 Drop Table MyTable;



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
